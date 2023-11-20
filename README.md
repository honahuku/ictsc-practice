# ictsc-practice

## member

@honahuku  
@SoragamiRaito  
@Ringo-onct  
@gumi-69  

## rule

### commit & branch

コミットメッセージとブランチの命名規則は[Conventional Commits](https://www.conventionalcommits.org/ja/v1.0.0/)に準拠するものとします。  
例としては以下のとおりです。  

```text
feat: hoge関数の追加
feat: poyoの導入
fix: typo
```

### merge & review

mainへの直接コミットはせず、Pull Request(PR) を作成し1名以上のレビューをもらってください。

## kind

```bash
kind create cluster --config=cluster-config.yml
kubectl cluster-info --context kind-kind
# これが通ったらkindのセットアップ成功
kubectl get nodes
```

## Argo CD と kubeshar

[ArgoCDを入れる](https://github.com/honahuku/ictsc-practice/tree/main/ArgoCD.md)
[kubesharkを入れる](https://github.com/honahuku/ictsc-practice/tree/main/kubeshar.md)
