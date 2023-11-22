# Argo CD

## Argo CD CLI のインストール

```bash
# ダウンロード終わるまで待つ
curl -sSL -o argocd-linux-amd64 https://github.com/argoproj/argo-cd/releases/latest/download/argocd-linux-amd64

sudo install -m 555 argocd-linux-amd64 /usr/local/bin/argocd

rm argocd-linux-amd64
```

## Argo CD のインストール

```bash
kubectl create namespace argocd

kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

## Argo CD API サーバーにアクセス

```bash
# バックグラウンドで起動して次のコマンド打てるように
kubectl port-forward svc/argocd-server -n argocd 8080:443 &
```

ブラウザで[https://localhost:8080](https://localhost:8080)にアクセス

## adminユーザーの初期パスワードを取得

```bash
argocd admin initial-password -n argocd
```

Username:admin
Password:コードの実行結果

## パスワードの変更

GUIでやるのが楽かも。  
User Info→UPDATE PASSWORD

## アプリのデプロイ

GUI便利です。  
参考→[https://dev.classmethod.jp/articles/kind_kubernete_argocd_getting_started/](https://dev.classmethod.jp/articles/kind_kubernete_argocd_getting_started/)

公式→[https://argo-cd.readthedocs.io/en/stable/getting_started/](https://argo-cd.readthedocs.io/en/stable/getting_started/)
