title: backslide sample
class: animation-fade
layout: true

<!-- This slide will serve as the base layout for all your slides -->
.bottom-bar[
  {{title}}
]

---

class: impact, overlay
background-image: url(https://dl.dropboxusercontent.com/s/2tgw62c1h1hdzpz/norman-tsui-KBKHXjhVQVM-unsplas)

# {{title}}
## ~ MAMANのITブログ ~

---

# Install

```shell
$ npm install -g backslide
```

依存関係が多いので躓くかも..

---

# Create a project

```shell
$ bs init
```

### 構成

```shell
.
*├── presentation.md
└── template
    ├── index.html
    ├── remark.min.js
    └── style.scss
```

基本的に `presentation.md` をいじればOK.

---

# Run

```shell
$ bs serve
```

勝手にブラウザが立ち上がり`localhost:4100`にアクセスされる。  
すると、一時的に作成された`.tmp`のrootが表示される。

--

↓

`presentation.html`をクリックする必要がある

.small[.right[`presentation.html`に直接アクセスしてほしい...]]

---

class: center, middle

# イチオシなところ

---

# Hot reload is God

* vscode-revealではできなかったのでとても捗る！
--

* reload後に位置が変わらないのも素晴らしい！

---

# Simple is Great

* デフォルトテンプレートがシンプルで格好いい！

---

# Content Classes is Elegant

.col-5[.center[

  ```txt
  .red[hoge]
  ```

  ↓

  ```html
  <div class="red">
    hoge
  </div>
  ```

]]
.col-6[.center[

  ```txt
  .center[.huge[
    AAA
  ]]
  ```

  ↓

  ```html
  <div class="center">
    <span class="huge">AAA</span>
  </div>
  ```

]]

---

## Previous slide is...

.scrollable[

````markdown
# Content Classes is Elegant

.col-5[.center[

  ```txt
  .red[hoge]
  ```

  ↓

  ```html
  <div class="red">
    hoge
  </div>
  ```

]]
.col-6[.center[

  ```txt
  .center[.huge[
    AAA
  ]]
  ```

  ↓

  ```html
  <div class="center">
    <span class="huge">AAA</span>
  </div>
  ```

]]
````

]

---

class: center, middle

# 気になるところ

---

# アニメーション機能

* 文中の文字をアニメーションでフェードインできない (と思う)
  * reveal.jsだとfragmentクラスで実現可能
* templateと変数を使えば多少は無理矢理実現できそう

---

# 上下方向のスライド構成に未対応

* 発表者も混乱するので個人的には必要ない
