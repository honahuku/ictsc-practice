# ictsc-practice

## member

[@honahuku](https://github.com/honahuku)  
[@SoragamiRaito](https://github.com/SoragamiRaito)  
[@Ringo-onct](https://github.com/Ringo-onct)  
[@gumi-69](https://github.com/gumi-69)  

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
