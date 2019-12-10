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

class: center, middle, impact

# Deploy

---

# Deploy (inline)

```
$ bs export
```

--

* リソースが無ければ、Single HTMLができる😄 (約500KB + コンテンツ量)
--

* GitHub PagesやS3、Netlifyなどでデプロイ👍
---

# Deploy (no inline)

```
$ bs export -l
```

--

* 外部リソース(`remark.js.min`など)をHTMLに埋め込まない
--

  * そのままではパスの問題で参照できない可能性がある
--

  * `template/index.html`で`remark.js.min`の読みこみをCDN経由に..


```diff
-  <script src="remark.min.js"></script>  
+  <script src="https://cdnjs.cloudflare.com/ajax/libs/remark/0.14.0/remark.min.js"></script>  
```

---

class: center, middle

# イチオシなところ

---

# Hot reload is God

* vscode-revealではできなかったのでとても捗る！
--

* reload後に位置が変わらないのも素晴らしい！

---

# Simple

* 以下3つのコマンドでOK
  * `bs init`
  * `bs serve`
  * `bs export`
--

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

* 中抜き文字を気軽にフェードインできない
--

  * reveal.jsだとfragmentクラスで実現可能
--

* templateと変数を使えば無理矢理実現できそう

---

first_name: invisible
last_name: invisible

## 途中文字をフェードインする例

* 私の姓は <span class="{{last_name}}">Aikawa</span> です
* 私の名は <span class="{{first_name}}">Tadashi</span> です
--

first_name: visible
--

last_name: visible

---

## 途中文字をフェードインする例

````markdown
first_name: invisible
last_name: invisible

## 中抜け文字をフェードインする例

 * 私の姓は <span class="{{last_name}}">Aikawa</span> です
 * 私の名は <span class="{{first_name}}">Tadashi</span> です

--

first_name: visible
--

last_name: visible

--
````

---

## 途中文字をフェードインする例

`style.scss`

```scss
.visilbe {
  visibility: visible;
}

.invisible {
  visibility: hidden;
}
```

---

## 途中文字をフェードインする例

グリッドや複雑なレイアウトを使う場合は`template`と組み合わせて使う必要あり

---

# ローカルのリソースが参照できない

* 画像ファイルを同梱する場合、デプロイしたら参照できない
  * exportの際に相対パスが **ファイルシステムの絶対パス** に置換される..
--

* 絶対パスを相対パスのままexportする方法があればいける?


---

# 上下方向のスライド構成に未対応

* 発表者も混乱するので個人的には必要ない

---

class: impact

# That's all👍
