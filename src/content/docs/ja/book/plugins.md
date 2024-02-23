---
title: プラグイン
---

プラグインを用いることで Nu の機能を拡張することができます。プラグインは、Nu の組み込みコマンドと同じ操作の多くを実行することができ、Nu 本体とは別に追加できるという利点もあります。

プラグインを追加するには、ビルドして PATH にバイナリーを配置するだけです。Nu のプラグインは、PATH 内の他のバイナリーと区別できるように`nu_plugin_`というファイル名ではじまります。

**注:** 将来的には、プラグインは Nu がみつけられるように特定の場所に配置されることになるかもしれません。

Nu が起動すると、システムがスキャンされ、見つかったプラグインがロードされます。

Nu プラグインが利用するプロトコルは Nu の開発中に変更される可能性があります。プロトコルの詳細と独自のプラグインの作成方法を学ぶのに最適なのは、[Nu リポジトリのプラグインのソース](https://github.com/nushell/nushell/tree/master/crates)を読むことです。
[コントリビュータブックのプラグインの章](https://github.com/nushell/contributor-book/blob/master/en/plugins.md)も参照してください。