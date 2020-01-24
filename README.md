# Docker Wordpress

## これは？
公式のWordpressイメージを使用したカスタム

## どう使う？
ローカルでは、テーマフォルダを作成しテーマを作成
`.env`ファイルの`THEME_NAME`にはテーマの名前を、`THEME_DIRECTORY`にはマウントするテーマフォルダを指定する

すべてのファイルをローカルに永続化せずDockerのexternalを使う
最初起動しようとするとvolumeを作れと言われるので従う
以降は、Docker内のVolumeに永続化されているので、一度Downしてもデータをそのままにしておける

volumeによるマウントを使用すると、rootユーザーでディレクトリが作成されてしまうため、Wordpressからメディアのアップロードやプラグインのインストールができなくなってしまうので、初回のコンテナ起動後`docker-compose exec -T wordpress chown www-data:www-data /var/www/html`として、Wordpressが変更できるようにする
