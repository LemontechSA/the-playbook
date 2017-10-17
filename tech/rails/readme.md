El step  by step es mas o menos asi

```
brew install rbenv
brew install postgresql

rbenv install 2.3.3
rbenv global 2.3.3

gem install bundler
gem install rails -v 5.1.4

rails new miapp --database=postgresql
```

configure `config/database.yml`

```
development:
  adapter: postgresql
  encoding: unicode
  database: myapp_development
  pool: 5
  username: myapp
  password: password1

test:
  adapter: postgresql
  encoding: unicode
  database: myapp_test
  pool: 5
  username: myapp
  password: password1
```

Setup!

```
cd myapp
rake db:setup
```

Create a fake model

```
rails g scaffold Audit title:string body:text
rake db:migrate
```

Run

```
bundle exec rails s
```
