CubePDF.js
====

https://app.cube-soft.jp/ の Web サーバを構築するためのプロジェクト。

## 構成

### docker

Docker に関するリソースを配置。
現時点では、nginx コンテナに関連する設定ファイルおよびリソースのみ。
必要に応じて docker-compose.yml を修正し、それと併せて必要なファイルをこのディレクトリ下に配置する。

### server

nginx サービスを起動した時に /var/www として認識されるディレクトリ。
公開するファイルは public ディレクトリ下に配置する。

### Rakefile

開発・運営する際の便利コマンドを記述しておくためのファイル。
rake コマンドで実行可能 (Ruby で動作している)。
他の方法が好みであれば、代替しても良い。
