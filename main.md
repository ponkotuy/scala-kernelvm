# Scalaの話

---

## おまえだれよ

@ponkotuy: ぽんこつ

Ruby/ScalaのWeb屋

最近治安の悪い某SlackででドナドナされてScalaの副業はじめました。

---

## Scalaとは
ScalaはJVM上で動くオブジェクト指向かつ関数型言語

オブジェクト指向と関数指向は直交する概念

Javaを書き易くし、関数型を導入した言語

ScalaからJavaを呼び出せる

---

## オブジェクト指向的側面
基本的なclass概念はJavaを踏襲

- class
- trait(interface)
- object(singleton)
- Generics(リッチ)

ただしできる限りimmutableにすることが推奨される

---

## 関数型的側面
- リッチなimmutable Collection
- Option/Eitherモナド
- モナド的なfor式
- scalazとcats(関数型ライブラリ)

---

## 開発者
どの程度関数型に寄せるかは論争がある

Better Java

↑

↓

純粋関数型

言語開発者はbetter Java寄り

---

## Scala is sbt
Scalaのビルドツールsbt

- ビルド
- 依存解決
- コンパイラのダウンロード
- sbt自身のバージョン管理(!)
- Docker imageの自動生成

---

## 低レイヤーな話
- Scalaはコンパイルされるとclassファイルに落ちる

- JavaからScalaを呼び出せる

- Javaから呼び出せない場合もある

---

## implicit引数
暗黙に渡される引数を作れる

```scala
def f(x: Int)(implicit y: Int) = x + y
```

```scala
implicit val y: Int = 1
f(2) // => 3
```

引き渡されるimplicit valueは型で判断される
