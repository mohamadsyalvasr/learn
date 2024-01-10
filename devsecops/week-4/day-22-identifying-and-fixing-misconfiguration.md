# ✅ Day 22: Identifying and Fixing Misconfiguration

Konfigurasi memainkan peran sentral dalam manajemen infrastruktur dan aplikasi modern, terutama dalam ekosistem Kubernetes, Helm, dan Terraform. Hari ini kita akan membahas arti konfigurasi dalam konteks ini, menyoroti pentingnya konfigurasi yang benar dalam menjaga kesehatan dan kinerja infrastruktur serta aplikasi.

## Kubernetes Manifest

### Apa itu Kubernetes Manifests?

Kubernetes Manifests adalah deskripsi YAML atau JSON yang mendefinisikan sumber daya yang dikelola oleh Kubernetes. Ini bisa berupa pod, layanan, atau sumber daya lainnya.

### Umumnya Terjadi Kesalahan

Beberapa kesalahan konfigurasi umum pada Kubernetes Manifests melibatkan format YAML yang salah, parameter yang tidak valid, atau kebijakan keamanan yang tidak terdefinisi dengan jelas. Mendeteksi kesalahan ini memerlukan pemahaman yang baik tentang struktur manifest dan alat bantu yang tepat.

### Penanganan Kesalahan

Untuk memperbaiki kesalahan konfigurasi, diperlukan langkah-langkah pencegahan seperti validasi menggunakan alat bantu atau penggunaan best practices dalam penulisan dan pengelolaan manifests.

Salah satu tool open-source yang populer adalah [KubeSec](https://kubesec.io/). Contoh manifest

```yaml
$ cat <<EOF > kubesec-test.yaml
apiVersion: v1
kind: Pod
metadata:
  name: kubesec-demo
spec:
  containers:
  - name: kubesec-demo
    image: gcr.io/google-samples/node-hello:1.0
    securityContext:
      readOnlyRootFilesystem: true
EOF
$ kubesec scan kubesec-test.yaml
```

Coba scan dan lihat hasilnya

```json
[
  {
    "object": "Pod/kubesec-demo.default",
    "valid": true,
    "message": "Passed with a score of 0 points",
    "score": 0,
    "scoring": {
      "advise": [
        {
          "selector": ".metadata .annotations .\"container.seccomp.security.alpha.kubernetes.io/pod\"",
          "reason": "Seccomp profiles set minimum privilege and secure against unknown threats"
        },
        {
          "selector": ".spec .serviceAccountName",
          "reason": "Service accounts restrict Kubernetes API access and should be configured with least privilege"
        },
        {
          "selector": "containers[] .securityContext .runAsNonRoot == true",
          "reason": "Force the running image to run as a non-root user to ensure least privilege"
        },
        {
          "selector": ".metadata .annotations .\"container.apparmor.security.beta.kubernetes.io/nginx\"",
          "reason": "Well defined AppArmor policies may provide greater protection from unknown threats. WARNING: NOT PRODUCTION READY"
        },
        {
          "selector": "containers[] .resources .requests .memory",
          "reason": "Enforcing memory requests aids a fair balancing of resources across the cluster"
        },
        {
          "selector": "containers[] .securityContext .runAsUser -gt 10000",
          "reason": "Run as a high-UID user to avoid conflicts with the host's user table"
        },
        {
          "selector": "containers[] .resources .limits .cpu",
          "reason": "Enforcing CPU limits prevents DOS via resource exhaustion"
        },
        {
          "selector": "containers[] .resources .requests .cpu",
          "reason": "Enforcing CPU requests aids a fair balancing of resources across the cluster"
        },
        {
          "selector": "containers[] .securityContext .readOnlyRootFilesystem == true",
          "reason": "An immutable root filesystem can prevent malicious binaries being added to PATH and increase attack cost"
        },
        {
          "selector": "containers[] .securityContext .capabilities .drop",
          "reason": "Reducing kernel capabilities available to a container limits its attack surface"
        },
        {
          "selector": "containers[] .resources .limits .memory",
          "reason": "Enforcing memory limits prevents DOS via resource exhaustion"
        },
        {
          "selector": "containers[] .securityContext .capabilities .drop | index(\"ALL\")",
          "reason": "Drop all capabilities and add only those required to reduce syscall attack surface"
        }
      ]
    }
  }
```

Dari hasil scan kita bisa tau apa saja yang harus diubah dan juga dijelaskan alasan mengapa kita harus mengubah konfigurasi kita.

Selain menggunakan KubeSec, kita juga bisa menggunakan tools lainnya seperti [kube-bench](https://github.com/aquasecurity/kube-bench), [kubeaudit](https://github.com/Shopify/kubeaudit) and [kube-score](https://github.com/zegl/kube-score) ataupun bisa menggunakan [Synk](https://docs.snyk.io/scan-using-snyk/scan-infrastructure/scan-your-iac-source-code/scan-kubernetes-configuration-files/configure-integration-to-find-security-issues-in-kubernetes-configuration-files-current-iac).

## Helm Charts

Helm adalah alat manajemen paket untuk Kubernetes, dan Helm Templates digunakan untuk membuat konfigurasi aplikasi.

### Umumnya Terjadi Kesalahan

Kesalahan pada Helm Templates dapat mencakup parameter yang tidak sesuai, masalah pada fungsi template, atau ketidaksesuaian versi Helm. Identifikasi kesalahan memerlukan pemahaman mendalam tentang struktur template Helm.

### Penanganan Kesalahan

Salah satu tools yang bisa digunakan adalah [Snyk](https://docs.snyk.io/scan-using-snyk/scan-infrastructure/scan-your-iac-source-code/scan-kubernetes-configuration-files/scan-and-fix-security-issues-in-helm-charts-current-iac). Contoh hasil scan&#x20;

<figure><img src="../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

## Terraform

Terraform adalah sebuah alat open-source yang digunakan untuk membuat, mengubah, dan mengelola infrastruktur cloud. Terraform menggunakan bahasa konfigurasi deklaratif untuk mendefinisikan infrastruktur yang diinginkan (HCL). Terraform kemudian akan menggunakan penyedia cloud untuk membuat atau mengubah infrastruktur sesuai dengan konfigurasi yang ditentukan.

### Umumnya Terjadi Kesalahan

Kesalahan pada Terraform Code bisa melibatkan konfigurasi sumber daya yang tidak valid, kurangnya dependensi, atau masalah pada variabel. Terraform menyediakan mekanisme pengecekan kesalahan bawaan.

### Penanganan Kesalahan

Salah satu tools paling popular adalah [tfsec](https://github.com/aquasecurity/tfsec). Kita juga bisa menggunakan tools [Snyk](https://docs.snyk.io/scan-using-snyk/scan-infrastructure/scan-your-iac-source-code/scan-terraform-files/scan-and-fix-security-issues-in-terraform-files-current-iac) untuk scanning Terraform Files.

Contoh hasil scanning dari tfsec

<figure><img src="../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

Contoh hasil scanning Snyk

<figure><img src="../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>
