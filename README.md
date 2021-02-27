下記コマンドでwebapp配下にrailsプロジェクトを作成する。
docker-compose run --rm app rails new . --force --database=mysql --skip-bundle

プロジェクトを作成すると
puma.rb
database.yml
が作成されるので下記コマンドでコピーする。
cp init/puma.rb config/puma.rb
cp init/database.yml config/database.yml

下記コマンドでdbを作成します。
docker-compose exec app rails db:create

【補足】
dbの接続情報設定は
docker-compose.yml
database.yml
の2か所にあるので合わせる事
