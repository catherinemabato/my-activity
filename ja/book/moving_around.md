# システム内の移動

初期のシェルを使うとシステム内を移動してコマンドを実行することができますが、Nu のような現代的なシェルでも同じことができます。システムを操作する際によく使われるコマンドをいくつか見てみましょう。

## ディレクトリの内容を確認する

@[code](@snippets/moving_around/ls_example.sh)

他の章でみてきたように、`ls`はパスの内容を表示するためのコマンドです。Nu はパスの内容をテーブルとして返してくれます。

`ls`コマンドには表示する内容を変更するためにオプションで引数を渡すことができます。例えば".md"で終わるファイルの一覧を表示することができます。glob"\*.md"はファイルが'.md'で終わっていればマッチすると読むことができます。

@[code](@snippets/moving_around/ls_shallow_glob_example.sh)

上記のオプション引数"\*.txt"の中で利用されているアスタリスク(\*)はしばしばワイルドカードやグロブと呼ばれ、何にでもマッチします。グロブ"\*.txt"は"'.txt'で終わる任意のファイルにマッチする"と読むことができます。

Nu はより深いディレクトリにアクセスできる最新のグロブも利用します。

@[code](@snippets/moving_around/ls_deep_glob_example.sh)

ここでは".md"で終わるファイルを探していますが、２つのアスタリスクはさらに"ここから始まる任意のディレクトリにある"という意味です。

## 現在のディレクトリを変更する

@[code](@snippets/book/moving_around/cd_example.nu)

現在のディレクトリを変更するには`cd`コマンドを使います。他のシェルと同じように、ディレクトリの名前か上の階層に移動する場合は`..`ショートカットを利用します。

`cd`を省略してパスだけを指定することでも現在の作業ディレクトリを変更することができます。

@[code](@snippets/book/moving_around/cd_without_command_example.nu)

## ファイルシステムのコマンド

Nu はクロスプラットフォームで動作するいくつかの基本的なファイルシステムのコマンドも提供します。

`mv`コマンドを利用すればアイテムをある場所から別の場所へ移動できます。

@[code](@snippets/moving_around/mv_example.sh)

ある場所から別の場所へアイテムのコピーができます。

@[code](@snippets/moving_around/cp_example.sh)

アイテムの削除ができます。

@[code](@snippets/moving_around/rm_example.sh)

３つのコマンドは`ls`コマンドでみたグロブ機能も利用できます。

最後に、`mkdir`コマンドで新しいディレクトリを作成できます。

@[code](@snippets/moving_around/mkdir_example.sh)
