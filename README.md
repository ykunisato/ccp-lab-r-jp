# Dockerfile for Rstudio in Computational Clinical Psychology Lab [Japanese]

This Dockerfile was developed for the Japanesese R users (So, it contains settings of Japanese environment). English version of this dockerfile is [here]((https://hub.docker.com/r/ykunisato/ccp-lab-r).

これは，専修大学人間科学部心理学科の[計算論的臨床心理学研究室](https://kunisatolab.github.io/main/index.html)の研究で利用するRパッケージをいれたDockerファイルのリポジトリです。このDockerファイルは，[ykunisato/paper-r](https://hub.docker.com/r/ykunisato/paper-r)と[ykunisato/ccp-lab-r](https://hub.docker.com/r/ykunisato/ccp-lab-r)をベースに日本語環境下したものであり，事前にインストールされたRパッケージは，以下と[ykunisato/paper-r](https://hub.docker.com/r/ykunisato/paper-r)に記載されていいます。作成者は専修大学人間科学部心理学科の国里愛彦です (ykunisato@psy.senshu-u.ac.jp)。エラーや追加してほしいパッケージなどがありましたら，気軽にご連絡ください。

Keywords: 心理学, 認知科学, 認知モデリング，心理学的ネットワーク分析，ネットワークメタ分析，分析・執筆，rstudio, rstan, cmdstan, rmarkdown

## 使用法

Docker Desktopがインストールされていて，ある程度の通信速度があれば，数分で使用可能です。

1.Docker Desktop ( https://www.docker.com/products/docker-desktop )をインストールする。

2.ターミナル（Macの場合。Winはコマンドプロンプト？)を開く

3.ターミナルに以下を打ち込んで、コンテナーをrunする(runの前にPullが自動的なされます)。パスワードとコンテナ名はご自身の好きなように設定ください。

```
docker run -e PASSWORD=パスワード -p 8787:8787 -v $PWD:/home/rstudio -d --name コンテナ名 ykunisato/ccp-lab-r
```

4.ブラウザを開いて，urlバー（アドレスバー）に，http://localhost:8787/ とタイプする

5.ブラウザ上にRstudioが出てくるので，IDにrstudio，パスに上記で設定したパスワードをいれる。

## Docker間の依存関係について

国里(ykunisato)が管理しているDockerコンテナとその依存関係は以下になります。

- [ykunisato/paper-r](https://hub.docker.com/r/ykunisato/paper-r) : 心理学系使いそうなRパッケージを入れたコンテナ（rocker/verseをベースに作成）
- [ykunisato/paper-r-jp](https://hub.docker.com/r/ykunisato/paper-r-jp) : ykunisato/paper-rをベースに日本語環境化したコンテナ
- [ykunisato/ccp-lab-r](https://hub.docker.com/r/ykunisato/ccp-lab-r) : ykunisato/paper-rをベースに認知モデリング,心理学的ネットワーク分析，ネットワークメタ分析で使用するパッケージを追加したコンテナ
- [ykunisato/ccp-lab-r-jp](https://hub.docker.com/r/ykunisato/ccp-lab-rjp) : ykunisato/ccp-lab-rをベースに日本語環境化したコンテナ(本コンテナ）

## 事前にインストールされている追加のRパッケージ
### 認知モデリングパッケージ

- ggdmc
- rjags
- Rsolnp
- ReinforcementLearning
- MDPtoolbox
- rtdists
- DstarM
- hBayesDM
- truncdist
- statmod
- pracma
- snowfall
- rlecuyer
- vioplot

### 心理学的ネットワーク分析パッケージ

- [qgraph](https://cran.r-project.org/web/packages/qgraph/index.html)
- [IsingFit](https://cran.r-project.org/web/packages/IsingFit/index.html)
- [IsingSampler](https://cran.r-project.org/web/packages/IsingSampler/index.html)
- [mlVAR](https://cran.r-project.org/web/packages/mlVAR/index.html)
- [graphicalVAR](https://cran.r-project.org/web/packages/graphicalVAR/index.html)
- [bootnet](https://cran.r-project.org/web/packages/bootnet/index.html)
- [mgm](https://cran.r-project.org/web/packages/mgm/index.html)
- [pcalg](https://cran.r-project.org/web/packages/pcalg/index.html)
- [NetworkComparisonTest](https://cran.r-project.org/web/packages/NetworkComparisonTest/index.html)
- [networktree](https://cran.r-project.org/web/packages/networktree/index.html)
- [networktools](https://cran.r-project.org/web/packages/networktools/index.html)
- [gimme](https://cran.r-project.org/web/packages/gimme/index.html)
- [NetworkToolbox](https://cran.r-project.org/web/packages/NetworkToolbox/index.html)
- [GGMnonreg](https://github.com/donaldRwilliams/GGMnonreg)
- [BGGM](https://github.com/donaldRwilliams/BGGM)
- [bnlearn](https://cran.r-project.org/web/packages/bnlearn/index.html)
- [igraph](https://cran.r-project.org/web/packages/igraph/index.html)
- [semPlot](https://cran.r-project.org/web/packages/semPlot/index.html)
- [EGAnet](https://cran.r-project.org/web/packages/EGAnet/index.html)

##### 以下は今後インストール予定
- [psychonetrics](https://github.com/SachaEpskamp/psychonetrics)
- [lvnet](https://cran.r-project.org/web/packages/lvnet/index.html)

### ネットワークメタ分析パッケージ

- gemtc
- netmeta
- ggnetwork

### EEG分析パッケージ

- eegUtils
