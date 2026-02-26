siv3dのバージョン:# include <Siv3D.hpp> // Siv3D v0.6.16

# Minge2025Summer_Team5から引っ張て来たもの

## 大事なルール

- コーディングスタイル -> [Siv3D](https://siv3d.github.io/ja-jp/develop/coding-style/) に準拠
- マージしたブランチはGitHub上から消すこと
- 画面上で表示している物体を動かすときは[s3d::DeltaTime()](https://siv3d.github.io/ja-jp/tutorial2/time/#301-%E7%B5%8C%E9%81%8E%E6%99%82%E9%96%93%E3%81%AE%E8%A8%88%E6%B8%AC) を利用する
- masterブランチで直接作業をしない



## 細かいルール

- [グローバル変数、シングルトン](https://siv3d.github.io/ja-jp/reference/avoid-global-variable/)は極力避ける

- 継承より合成(composition)を優先する

- switch-caseの中に長々と処理を書かない。関数呼び出すだけにする。

```cpp
switch (flag) {
case Run: run();
case Wait: wait();
case Tayama: tayama();
default: assert(!"invalid state of Stage::flag");
}
```

- リファクタリングばっかりしない。時期早々な抽象化をしない。(zawa、お前のことやぞ)

- whileループは無限ループの元なので極力避ける

- if 文の条件式を長くしない

```cpp
if (A and B or (not C)) run();
```
=>
```cpp
if (haveToRun()) run();
```

- const参照が使えるときはそうする
- スマートポインタを優先する
