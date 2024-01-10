# ✅ Day 21: Continuous Image Repository Scan

Di hari ke-13 kita sudah tau apa itu container image scanning dan mengapa itu sangat penting. Kita juga berkenalan dengan beberapa tools seperti Clair, Trivy / Aqua Security, Snyk dan Sysdig Secure.

Hari ini kita akan belajar bagaimana image scanning ini di konfigurasi sebagai bagian dari CI/CD pipeline. Dengan cara ini, kita dapat memastikan bahwa image ter-build oleh pipeline dan kemudian di scan oleh image scanner. Hasil dari scan ini akan ditampilkan ke sistem lain, yang di mana DevSecOps engineer bisa melihat itu dan melakukan aksi tergantung dari hasil scannya.

## Setting up GitHub Action (Workflows)

Mari kita coba Trivy dan GitHub Action untuk percobaan pertama ini. Trivy ini open-source scanner yang dibuat oleh Aqua Security yang di mana kalian bisa lihat pada [repository ini](https://github.com/aquasecurity/trivy).



Contoh GitHub Action

{% code title=".github/workflows/deployment.yml" lineNumbers="true" %}
```yaml
  build_image:
    runs-on: ubuntu-latest
    needs: lint_code
    steps:
      - uses: actions/checkout@v4
      - name: Docker login
        env:
          DOCKER_USER: ${{secrets.DOCKER_USER}}
          DOCKER_PASSWORD: ${{secrets.DOCKER_PASSWORD}}
        run: |
          docker login -u $DOCKER_USER -p $DOCKER_PASSWORD
      - name: Get repository release tag
        id: timeseries
        uses: pozetroninc/github-action-get-latest-release@master
        with:
          excludes: prerelease, draft
          repository: ${{ github.repository }}
      - name: Build Docker image
        run: |
          docker build --network=host -t ${{secrets.DOCKER_USER}}/erp:latest -t ${{secrets.DOCKER_USER}}/erp:${{ steps.timeseries.outputs.release }} .
      - name: Docker push image
        run: |
          docker push ${{secrets.DOCKER_USER}}/erp
          docker push ${{secrets.DOCKER_USER}}/erp:${{ steps.timeseries.outputs.release }}
  scan_image:
    runs-on: ubuntu-latest
    needs: build_image
    steps:
      - name: Get repository release tag
        id: timeseries
        uses: pozetroninc/github-action-get-latest-release@master
        with:
          excludes: prerelease, draft
          repository: ${{ github.repository }}
      - name: Run Trivy vulnerability scanner
        uses: aquasecurity/trivy-action@master
        with:
          image-ref: 'docker.io/${{secrets.DOCKER_USER}}/erp:${{ steps.timeseries.outputs.release }}'
          format: 'table'
          exit-code: '1'
          ignore-unfixed: true
          vuln-type: 'os,library'
          severity: 'CRITICAL,HIGH'
```
{% endcode %}

Code di atas adalah contoh build image dan push ke docker hub jika berhasil di build lalu di upload ke docker hub maka proses selanjutnya melakukan scan image menggunakan trivy yang di mana report akan di tampilkan pada workflow atau di kirimkan ke panel secuity github. D ibawah ini adalah contoh hasil scan trivy.

```
===========================================
Total: 4 (HIGH: 4, CRITICAL: 0)

┌────────────────┬───────────────┬──────────┬────────┬───────────────────┬───────────────┬──────────────────────────────────────────────────────────────┐
│    Library     │ Vulnerability │ Severity │ Status │ Installed Version │ Fixed Version │                            Title                             │
├────────────────┼───────────────┼──────────┼────────┼───────────────────┼───────────────┼──────────────────────────────────────────────────────────────┤
│ linux-libc-dev │ CVE-2023-6531 │ HIGH     │ fixed  │ 6.1.67-1          │ 6.1.69-1      │ kernel: GC's deletion of an SKB races with                   │
│                │               │          │        │                   │               │ unix_stream_read_generic() leading to...                     │
│                │               │          │        │                   │               │ https://avd.aquasec.com/nvd/cve-2023-6531                    │
│                ├───────────────┤          │        │                   │               ├──────────────────────────────────────────────────────────────┤
│                │ CVE-2023-6817 │          │        │                   │               │ kernel: inactive elements in nft_pipapo_walk                 │
│                │               │          │        │                   │               │ https://avd.aquasec.com/nvd/cve-2023-6817                    │
│                ├───────────────┤          │        │                   │               ├──────────────────────────────────────────────────────────────┤
│                │ CVE-2023-6931 │          │        │                   │               │ kernel: Out of boundary write in perf_read_group() as result │
│                │               │          │        │                   │               │ of overflow a...                                             │
│                │               │          │        │                   │               │ https://avd.aquasec.com/nvd/cve-2023-6931                    │
│                ├───────────────┤          │        │                   │               ├──────────────────────────────────────────────────────────────┤
│                │ CVE-2024-0193 │          │        │                   │               │ kernel: netfilter: use-after-free in                         │
│                │               │          │        │                   │               │ nft_trans_gc_catchall_sync leads to privilege escalation     │
│                │               │          │        │                   │               │ https://avd.aquasec.com/nvd/cve-2024-0193                    │
└────────────────┴───────────────┴──────────┴────────┴───────────────────┴───────────────┴──────────────────────────────────────────────────────────────┘
```

Pada report di atas menampilkan SBOM yang memiliki kerentanan keamanan. Dari sini DevSecOps engineer bisa melakukan aksi yang terbaik untuk mengatasi masalah yang ada.

<mark style="color:red;">**To Be Continue**</mark>
