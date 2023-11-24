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

`Username:admin`  
`Password:コードの実行結果`

## パスワードの変更

GUIでやるのが楽かも。  
User Info→UPDATE PASSWORD

## デプロイ

親Applicationの`app-of-apps.yaml`をデプロイするだけ。

```bash
kubectl apply -f app-of-apps.yaml
```

## 子Applicationの追加

1. 子Applicationのディレクトリ作成&manifestファイル作成
1. `/applications`に新規ファイル作成&Applicationを定義
1. Githubリポジトリにpushする(`spec.syncPolicy`を`automated`にしているため自動でArgoCDがデプロイしてくれるらしい。)

## 参考

- Argo CDのインストール。  
[kindでKubernetesクラスターを作成してArgo CDのGetting Startedをやってみる](https://dev.classmethod.jp/articles/kind_kubernete_argocd_getting_started/)  
公式: [https://argo-cd.readthedocs.io/en/stable/getting_started/](https://argo-cd.readthedocs.io/en/stable/getting_started/)

- App Of Appsのapplication管理  
[ArgoCDでApplicationをmanifestで管理する](https://zenn.dev/kassshi/articles/argocd-app-of-apps)
