# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version 2.7

* System dependencies

* Configuration

* Database creation mmsql

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

1) docker-compose run web rails new . --api --skip-activerecord --force --no-deps
2) docker-compose build
3) docker-compose up
4) docker-compose exec db /opt/mssql-tools/bin/sqlcmd \
   -S localhost -U SA -P 'my2020securePass' \
   -Q 'ALTER LOGIN SA WITH PASSWORD="my2020securePass"'

5) docker-compose run --rm web bundle install
6) docker-compose run --rm web bundle exec rake db:create
7) docker-compose run --rm web bundle exec rake db:migrate

Access to docker container:
docker exec -it docker-rails-mmsql_db_1 "bash"