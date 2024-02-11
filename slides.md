---
theme: seriph
highlighter: shiki
lineNumbers: false
drawings:
  persist: false
transition: fade
addons:
  - slidev-addon-asciinema
---

# Slidev でスライドを作ろう

mitani24 2024-02-15

---
layout: two-cols
---

# [Slidev](https://sli.dev/) とは

- テキストベースでスライドを作成するツール
  - このスライドも Slidev で作られている
- 必要なもの
  - Node.js
  - Visual Studio Code などのテキストエディタ

::right::

![slidev logo](https://sli.dev/logo-title.png)

---

# スライド作成の大まかな流れ

1. プロジェクトを作成する
2. 開発サーバーを起動する
3. Markdown でスライドを記述する
4. 必要に応じてテーマやスタイルをカスタマイズする
5. スライドをエクスポートして共有する

---

# プロジェクトを作成する

```sh
npm init slidev@latest
```

<Asciinema src="slidev-init.cast" :playerProps="{cols: 150, rows: 25, speed: 2}" m="t-4"/>

---
layout: statement
---

# Demo

[slidev-test - StackBlitz](https://stackblitz.com/edit/slidev-zjgffb?file=slides.md)

---

# いいところ😊

- 素早く映えるスライドを作れる
- コンテンツとスタイルを分離できる
  - まずコンテンツに集中、後からスタイルを調整する進め方ができる
- 技術的な内容との親和性が高い
- 柔軟性・拡張性が高い
  - 割となんでもできる
  - theme, addon が npm packages として公開されている
    - このスライドも [slidev-addon-asciinema](https://www.npmjs.com/package/slidev-addon-asciinema) を使用している
- バージョン管理しやすい

---

# あと一歩なところ😢

- ある程度お作法への慣れが必要
- 凝ったことをやろうとすると途端にハードルが上がる
  - [UnoCSS](https://unocss.dev/), [@vueuse/motion](https://motion.vueuse.org/) 等の知識が要求される
- たまにバグっぽい挙動がある
  - `transition: slide-left` の挙動が怪しい
  - たぶんまだ Beta 版
- 日本語ドキュメントも用意されているが若干古い
  - 英語版を見たほうがいい

---
layout: statement
class: text-6xl font-700
---

使いこなせれば強力💪
