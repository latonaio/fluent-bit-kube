# fluent-bit-kube
fluent-bit-kube は kubernetes pod が吐き出すログデータを収集するマイクロサービス です。
本リポジトリには、必要なマニフェストファイル等が入っています。

## 動作環境
- Kubernetes: v1.24.4

## 設定
### namespace の作成
```
kubectl create namespace logging
```

### fluent-bit の yaml ファイルの apply
```
k apply -f fluent-bit-service-account.yaml
k apply -f fluent-bit-role-1.22.yaml
k apply -f fluent-bit-role-binding-1.22.yaml
```

### configmap の apply
```
k apply -f fluent-bit-configmap.yaml
```

### deamonset
```
k apply -f fluent-bit-ds.yaml
```
