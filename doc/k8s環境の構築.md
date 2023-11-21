# k8s環境の構築
## kind
kindというdockerでk8sを動作させるためのツールがある。各個人のPCとかでk8sを触るならこれがおすすめ。

```bash
kind create cluster --config=cluster-config.yml
kubectl cluster-info --context kind-kind
# これが通ったらkindのセットアップ成功
kubectl get nodes
```
