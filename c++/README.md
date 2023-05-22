# M1 Macにおいてのg++の環境構築

Mac OSではc++のコンパイラとして, Clang系のみが標準搭載されている.</br>
今回の環境構築ではgcc系のコンパイラをインストールする.

## インストール方法

1. gccをインストール

以下コマンドでインストール.</br>
```
brew install gcc
```

実行後, `/opt/homebrew/bin`下に, ```g++-13```のようなファイルが作成されている.

2. pathの設定

gccをインストールすると, 2種類のコンパイラが同居している状態になる.

- /usr/bin/g++(clang)

- /opt/homebrew/bin/g++-13(gcc)

clangではなくgccにしたいため、以下のコマンドを実行.</br>

```
ln -s /opt/homebrew/bin/g++-13 /usr/local/bin/g++
```

シンボリックリンクを作成する場所はどこでも(どこでもは良くないが)良い気がする(最悪PATHの設定をどうにかすればいいので...).</br>
コマンド実行後, `which g++`を実行し, 変化があるときgcc系を呼び出すことに成功.できていない場合, `echo $PATH`を実行し, PATHの設定を見ることを推奨.</br>

## インストールすることの利点

gcc系にはclang系にはない`#include <bits/stdc++.h>`という標準ライブラリを纏めたものを使用することができる.</br>

### 参考文献

- [Visual studio codeで競プロ環境構築[mac OS]](https://qiita.com/EngTks/items/ffa2a7b4d264e7a052c6)</br>
- [MacでGCCを"正しく"環境構築しよう！](https://qiita.com/DaikiSuyama/items/09f5aa399aad37783146#fn4)</br>
- [M1 Macでの競プロ用のC++環境構築ガイド](https://persimmonblog.com/guide-for-setting-up-environment-for-m1mac/)
