---
title: "Change Theme Minimal Mistakes"
date: 2019-09-16
categories:
  - blog
tags:
  - jekyll
  - template
  - minimal-mistakes
---

Themeを変更する際にやったことをメモしておく

### Flow
##### DL Theme from Github 
紆余曲折あったのが、`minimal-mistakes`本体をDLしてきて、その設定を変更しようとすると色々面倒だった。
特に不要なもの必要なもの変更すべきものを精査しながら設定すると、数も多いし間違うし。

またその設定サイト参考にした際に、テンプレート種別を`Liquid`から`jekyll-archives`に変更するような手順があったが、そもそもその糸が分からないことや設定だけ書き換えても動かないなどの問題があった。それはjekyll-archivesは別途インストールする必要があったらしい。

さらに、インストールする際にGemfileに描くのか、gemspecに書くのか、そもそもgemspec is 何状態だったのでさらに混乱した。

↑↑↑ というようなことがあり、再設定し直しとかしてすっかり消耗してしまった。
で、よくよく調べたら本家とは別にStarterテンプレート的なのが別リポジトリにあった。

[mmistakes/mm-github-pages-starter
](https://github.com/mmistakes/mm-github-pages-starter)

これだとイチから構築するようのテンプレートなので楽だった。初めからこちらを使っていればよかった。

### Config
上記のテンプレートで１点気をつけることとしては(というかこのテンプレートに限らずだが)
`bundle install --path vender/bundle`みたいに同階層にgemをインストールした場合、jekyllのビルド対象から外してやる必要がある。

```bash
$ vi _config.yml

exclude:
  - vendor
```

他にも本体のテンプレートを見ると、一通り設定してあったので同じようにしておく
(vendor以外はやってもやらなくてもよいと思う)

[本体のgitignore設定](https://github.com/mmistakes/minimal-mistakes/blob/master/.gitignore)

ここまでやっとくと後は自分用の設定のみ集中することができる
自分用の設定ついては省略します

### Contents
Starterテンプレートの`_posts`ディレクトリにいくつかのパターンが入っているので、それを参考にしながらmarkdownで書いていく

### Publish and Post
pushして完了

### End
ドキュメントに色々書いてあるので、手をつける前に読んでおくのが最短ルートだなと思った。これに限らず。
