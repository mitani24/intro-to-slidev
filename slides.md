---
theme: seriph
title: Slidev はいいぞ
author: mitani24
export:
  dark: true
transition: fade
addons:
  - slidev-addon-asciinema
---

# Slidev はいいぞ

2024-02-15 社内 LT 大会

<p class="absolute bottom-10 right-10 font-700">
  mitani24
</p>

---
layout: two-cols
---

# [Slidev](https://sli.dev/) とは

- テキストベースのスライド作成ツール
- いくつかのパッケージ群で構成される
  - Node.js 製 CLI
  - theme などの npm packages
  - VSCode 拡張
- 類似ツール
  - [Marp](https://marp.app/)
  - [Fusuma](https://hiroppy.github.io/fusuma/)

このスライドも Slidev で作られている

::right::

![slidev logo](https://sli.dev/logo-title.png)

---
layout: statement
---

# 特長1: テキストベース

---

# 特長1: テキストベース

主に Markdown でスライドを記述する

<div grid="~ cols-2 gap-8">
<div>

Input

```md {all|1-4|6-12|14|all}
---
theme: seriph
transition: slide-left
---

# Slidev はいいぞ

2024-02-15 社内 LT 大会

<p class="absolute bottom-10 right-10 font-700">
  mitani24
</p>

---

<!-- 2ページ目 -->
```

</div>
<div>

<p m="t-0">Output</p>

![slide title page](/slide-title.png)

</div>
</div>

<style>
p {
  @apply mt-0!;
}
</style>

---

# 特長1: テキストベース

## 利点

- 素早く映えるスライドを作れる
- コンテンツとスタイルを分離できる
  - まずコンテンツに集中、後からスタイルを調整する進め方ができる
- バージョン管理しやすい

<style>
h2 {
  @apply my-4!;
}
</style>

---
layout: statement
---

# 特長2: SPA として出力する

---

# 特長2: SPA として出力する

- 見た目がスライドっぽい Web アプリ
- 作業は開発サーバーを起動して行う

## 利点

- コードの変更は即座にスライドに反映
- Web 技術でできることは Slidev でも実現可能
- [GitHub Pages](https://pages.github.com/) など好きな場所にホストして公開できる

<style>
h2 {
  @apply mb-4!;
}
</style>

---
layout: statement
---

# 特長3: 高すぎる表現力

---

# 高すぎる表現力: コードブロック

行ハイライトや TypeScript の型情報付きのコードブロックを使える

<div grid="~ cols-2 gap-8">

```ts {all|2|1-6|9|all}
interface User {
  id: number
  firstName: string
  lastName: string
  role: string
}

function updateUser(id: number, update: User) {
  const user = getUser(id)
  const newUser = { ...user, ...update }
  saveUser(id, newUser)
}
```

```ts twoslash
interface User {
  id: number
  firstName: string
  lastName: string
  role: string
}

function updateUser(id: number, update: User) {
  const user = getUser(id)
  const newUser = { ...user, ...update }
  saveUser(id, newUser)
}
```

</div>

---

# 高すぎる表現力: Monaco Editor

スライドの中で自動補完付きのライブコーディング

```ts {monaco}
interface User {
  id: number
  firstName: string
  lastName: string
  role: string
}

function updateUser(id: number, update: User) {
  const user = getUser(id)
  const newUser = { ...user, ...update }
  saveUser(id, newUser)
}
```

---

# 高すぎる表現力: 数式・ダイアグラム

LaTeX や Mermaid はもちろん使える

<div grid="~ cols-2 gap-8">

$$
\begin{array}{c}
\nabla \times \vec{\mathbf{B}} -\, \frac1c\, \frac{\partial\vec{\mathbf{E}}}{\partial t} &
= \frac{4\pi}{c}\vec{\mathbf{j}}    \nabla \cdot \vec{\mathbf{E}} & = 4 \pi \rho \\
\nabla \times \vec{\mathbf{E}}\, +\, \frac1c\, \frac{\partial\vec{\mathbf{B}}}{\partial t} & = \vec{\mathbf{0}} \\
\nabla \cdot \vec{\mathbf{B}} & = 0
\end{array}
$$


```mermaid
sequenceDiagram
    Alice->John: Hello John, how are you?
    Note over Alice,John: A typical interaction
```

</div>

---

# 高すぎる表現力: video, iframe, ...

埋め込めます。それ

<div grid="~ cols-2 gap-8">
<video src="/video.mov" autoplay loop muted />
<iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3240.82803068985!2d139.7645498765545!3d35.681236172587326!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x60188bfbd89f700b%3A0x277c49ba34ed38!2z5p2x5Lqs6aeF!5e0!3m2!1sja!2sjp!4v1707909133619!5m2!1sja!2sjp" width="400" height="300" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
</div>

---

# 高すぎる表現力: Vue Component

なんでもできるやん…

<div grid="~ cols-2 gap-8" m="t-4">
<div>

自作 Vue Component を埋め込める

```html
<Counter :count="10" />
```

<Counter :count="10" m="t-4" />
</div>
<div>

便利な Built-in Component も用意されている

```html
<Tweet id="1390115482657726468" />
```

<Tweet id="1390115482657726468" scale="0.5" />
</div>

</div>

---

# 高すぎる表現力

## 利点

- 技術的な内容と親和性が高い
  - 多様な表現を簡単に扱えるよう工夫されている
- 拡張性が高い
  - 多くの機能が拡張できる
  - 公式やコミュニティにより開発された theme, addon が npm packages として公開されている
  - もちろん自作もできる

<style>
h2 {
  @apply mb-4!;
}
</style>

---
layout: statement
---

# あと一歩なところ

---

# あと一歩なところ

- ある程度お作法への慣れは必要
- 凝ったことをやろうとすると途端にハードルが上がる
  - [UnoCSS](https://unocss.dev/), [@vueuse/motion](https://motion.vueuse.org/) 等の知識が要求される
- 凝ろうと思えばいくらでも凝れるのでやらないことを決めないと凝り続けてしまう
- たまに怪しい挙動がある
  - たぶんまだ Beta 版
- 日本語ドキュメントも用意されているが若干古い
  - 英語版を見たほうがいい

---

# まとめ

- Slidev はテキストベースのスライド作成ツール
- Web 技術がベースとなっている
- 高い表現力とそれを扱いやすくする工夫がたくさん

---
layout: cover
background: https://source.unsplash.com/qaCJ6A0Rfvg
---

# Slidev はいいぞ
