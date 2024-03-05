---
title: テーブルを扱う
---

Nu でデータを表示する一般的な方法はテーブルを使用することです。Nu には、探しているものを見つけやすくしたり、必要なデータを絞り込んだりするのに便利なテーブルを操作するためのコマンドがたくさん用意されています。

まずはじめに、今回利用するテーブルを確認しましょう。

```nu
> ls
───┬───────────────┬──────┬─────────┬────────────
 # │ name          │ type │ size    │ modified
───┼───────────────┼──────┼─────────┼────────────
 0 │ files.rs      │ File │  4.6 KB │ 5 days ago
 1 │ lib.rs        │ File │   330 B │ 5 days ago
 2 │ lite_parse.rs │ File │  6.3 KB │ 5 days ago
 3 │ parse.rs      │ File │ 49.8 KB │ 1 day ago
 4 │ path.rs       │ File │  2.1 KB │ 5 days ago
 5 │ shapes.rs     │ File │  4.7 KB │ 5 days ago
 6 │ signature.rs  │ File │  1.2 KB │ 5 days ago
───┴───────────────┴──────┴─────────┴────────────
```

## データのソート

ソートに利用する列名を指定して、`sort-by`コマンドを呼びだすことでテーブルをソートできます。ファイルのサイズでテーブルをソートしたいとしましょう。

```nu
> ls | sort-by size
───┬───────────────┬──────┬─────────┬────────────
 # │ name          │ type │ size    │ modified
───┼───────────────┼──────┼─────────┼────────────
 0 │ lib.rs        │ File │   330 B │ 5 days ago
 1 │ signature.rs  │ File │  1.2 KB │ 5 days ago
 2 │ path.rs       │ File │  2.1 KB │ 5 days ago
 3 │ files.rs      │ File │  4.6 KB │ 5 days ago
 4 │ shapes.rs     │ File │  4.7 KB │ 5 days ago
 5 │ lite_parse.rs │ File │  6.3 KB │ 5 days ago
 6 │ parse.rs      │ File │ 49.8 KB │ 1 day ago
───┴───────────────┴──────┴─────────┴────────────
```

比較さえできれば任意の列でソートが行なえます。例えば、"name"、"accessed"、または"modified"列でソートすることができます。

## 必要なデータを選択する

列や行を選択することでテーブルから必要なデータを選択できます。テーブルからいくつかの列を選択してみましょう。

```nu
> ls | select name size
───┬───────────────┬─────────
 # │ name          │ size
───┼───────────────┼─────────
 0 │ files.rs      │  4.6 KB
 1 │ lib.rs        │   330 B
 2 │ lite_parse.rs │  6.3 KB
 3 │ parse.rs      │ 49.8 KB
 4 │ path.rs       │  2.1 KB
 5 │ shapes.rs     │  4.7 KB
 6 │ signature.rs  │  1.2 KB
───┴───────────────┴─────────
```

こうすることで、より必要とするデータにフォーカスしたテーブルを作ることができます。次にディレクトリからもっとも小さい 5 つのファイルを表示してみます。

```nu
> ls | sort-by size | first 5
───┬──────────────┬──────┬────────┬────────────
 # │ name         │ type │ size   │ modified
───┼──────────────┼──────┼────────┼────────────
 0 │ lib.rs       │ File │  330 B │ 5 days ago
 1 │ signature.rs │ File │ 1.2 KB │ 5 days ago
 2 │ path.rs      │ File │ 2.1 KB │ 5 days ago
 3 │ files.rs     │ File │ 4.6 KB │ 5 days ago
 4 │ shapes.rs    │ File │ 4.7 KB │ 5 days ago
───┴──────────────┴──────┴────────┴────────────
```

もっとも小さいファイルを取得するためにまずサイズでソートし、それから`first 5`を利用してテーブルから最初の 5 行を返しています。

不要な行を`skip`することもできます。上記で返された５行のうち最初の２行をスキップしてみましょう。

```nu
> ls | sort-by size | first 5 | skip 2
───┬───────────┬──────┬────────┬────────────
 # │ name      │ type │ size   │ modified
───┼───────────┼──────┼────────┼────────────
 0 │ path.rs   │ File │ 2.1 KB │ 5 days ago
 1 │ files.rs  │ File │ 4.6 KB │ 5 days ago
 2 │ shapes.rs │ File │ 4.7 KB │ 5 days ago
───┴───────────┴──────┴────────┴────────────
```

関心のある３行に絞り込みました。

データを選択するための他のコマンドもみてみましょう。テーブルの各行が数字をもつことを疑問に思っているかもしれません。これは単一の行を簡単に指定する方法として機能します。テーブルをファイル名でソートして、`nth`コマンドを利用して n 行目を選択してみましょう。

```nu
> ls | sort-by name
───┬───────────────┬──────┬─────────┬────────────
 # │ name          │ type │ size    │ modified
───┼───────────────┼──────┼─────────┼────────────
 0 │ files.rs      │ File │  4.6 KB │ 5 days ago
 1 │ lib.rs        │ File │   330 B │ 5 days ago
 2 │ lite_parse.rs │ File │  6.3 KB │ 5 days ago
 3 │ parse.rs      │ File │ 49.8 KB │ 1 day ago
 4 │ path.rs       │ File │  2.1 KB │ 5 days ago
 5 │ shapes.rs     │ File │  4.7 KB │ 5 days ago
 6 │ signature.rs  │ File │  1.2 KB │ 5 days ago
───┴───────────────┴──────┴─────────┴────────────

> ls | sort-by name | nth 5
──────────┬────────────
 name     │ shapes.rs
 type     │ File
 size     │ 4.7 KB
 modified │ 5 days ago
──────────┴────────────
```

## テーブルからデータを取得する

これまでは、テーブルを必要なものだけにトリミングする操作を行ってきました。ときには一歩進んで、列全体ではなく、セル自体の値が必要になるかもしれません。たとえば、ファイル名のリストだけを取得したいとしましょう。この場合`get`コマンドを利用することができます。

```nu
> ls | get name
───┬───────────────
 0 │ files.rs
 1 │ lib.rs
 2 │ lite_parse.rs
 3 │ parse.rs
 4 │ path.rs
 5 │ shapes.rs
 6 │ signature.rs
───┴───────────────
```

これで各ファイルの名前が取得できました。

これはさきほどみた`select`コマンドと同じにみえるかもしれません、比較のために`select`コマンドの出力もみておきましょう。

```nu
> ls | select name
───┬───────────────
 # │ name
───┼───────────────
 0 │ files.rs
 1 │ lib.rs
 2 │ lite_parse.rs
 3 │ parse.rs
 4 │ path.rs
 5 │ shapes.rs
 6 │ signature.rs
───┴───────────────
```

両者は非常に似ています！両者の違いを明確にしておきましょう。

- `select` - 指定された列のみを含む新しいテーブルを作成します
- `get` - 指定された列内の値を返します

テーブルからこれらを区別する方法の一つは、`value`列名です。これにより値のリストであることがわかります。

`get`コマンドは、パスを受け取りテーブル内のより深いデータへアクセスすることができます。これにより.json ファイルにあるような複雑なデータを簡単に操作することができます。

## テーブルのデータを変更する

テーブルからデータを選択することに加えて、テーブルの内容を更新することもできます。新しい列を加えたり、セルの内容を編集したりできるのです。Nu では、その場で編集するのではなく、パイプラインの各コマンドは新しいテーブルを返します。

### 新しい列を追加する

`add`コマンドを使用して、新しい列をテーブルに追加できます。例をみてみましょう。

```nu
> open rustfmt.toml
─────────┬──────
 edition │ 2018
─────────┴──────
```

値が 2021 の"next_edition"列を追加してみましょう。

```nu
> open rustfmt.toml | insert next_edition 2021
──────────────┬──────
 edition      │ 2018
 next_edition │ 2021
──────────────┴──────
```

元のファイルは変更されていないことに注意してください。

```nu
> open rustfmt.toml
─────────┬──────
 edition │ 2018
─────────┴──────
```

Nu の変更は永続的な変更ではなく、値自体に作用する関数的な変更です。これにより、結果を書き出す準備ができるまでパイプライン上で様々な種類の作業をおこなうことができます。ここでは、`save`コマンドを使用して結果を書き出すことができます。

```nu
> open rustfmt.toml | insert next_edition 2021 | save rustfmt2.toml
> open rustfmt2.toml
──────────────┬──────
 edition      │ 2018
 next_edition │ 2021
──────────────┴──────
```

### 列を更新する

`insert`コマンドと同様に、`update`コマンドを利用して列の内容を新しい値に変更することもできます。実際に動作を確認するために同じファイルを開いてみましょう。

```nu
> open rustfmt.toml
─────────┬──────
 edition │ 2018
─────────┴──────
```

今度は、サポートした次の edition を指定するよう更新しましょう。

```nu
> open rustfmt.toml | update edition 2021
─────────┬──────
 edition │ 2021
─────────┴──────
```

### 値を増やす

数字やバージョンを扱う際に便利なコマンドがもうひとつあります、`inc`です。

```nu
> open rustfmt.toml
─────────┬──────
 edition │ 2018
─────────┴──────
> open rustfmt.toml | inc edition
─────────┬──────
 edition │ 2019
─────────┴──────
```

"edition"の値は数字なので、`inc`を使って更新することができます。バージョンを扱う際には`inc`がその真価を発揮します。

```nu
> open Cargo.toml | get package.version
0.1.3
> open Cargo.toml | inc package.version --minor | get package.version
0.2.0
```

バージョンを扱う際には、フラグを利用して、バージョンのインクリメント方法を指定できます。

- **--major** - メジャーバージョンをインクリメント (0.1.3 -> 1.0.0)
- **--minor** - マイナーバージョンをインクリメント (0.1.3 -> 0.2.0)
- **--patch** - パッチバージョンをインクリメント (0.1.3 -> 0.1.4)