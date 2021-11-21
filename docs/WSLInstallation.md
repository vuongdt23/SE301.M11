# Cài đặt môi trường phát triển Mastodon trên Ubuntu 18.04 WSL

## Cài đặt curl và Node.js 12:

Node.js 12 không phải là phần mặc định của bản phân phối Ubuntu 18.04, chúng ta sẽ cài dặt nó thông qua curl

### Curl:
```
sudo apt install curl
```
### Node.js:
```
curl -sL https://deb.nodesource.com/setup_12.x | bash -
```

## Cài đặt Yarn

```
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add -
```
```
echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee etc/apt/sources.list.d/yarn.list`
```
## Cài đặt các System Package khác
```
apt update
```

```
apt install -y \
  imagemagick ffmpeg libpq-dev libxml2-dev libxslt1-dev file git-core \
  g++ libprotobuf-dev protobuf-compiler pkg-config nodejs gcc autoconf \
  bison build-essential libssl-dev libyaml-dev libreadline6-dev \
  zlib1g-dev libncurses5-dev libffi-dev libgdbm-dev \
  nginx redis-server redis-tools postgresql postgresql-contrib \
  certbot python-certbot-nginx yarn libidn11-dev libicu-dev libjemalloc-dev
  ```


## Cài đặt rbenv và Ruby
### Cài đặt rbenv
```shell
git clone https://github.com/rbenv/rbenv.git ~/.rbenv
cd ~/.rbenv && src/configure && make -C src
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(rbenv init -)"' >> ~/.bashrc
exec bash
git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build
```
### Sau khi cài đặt xong rbenv chúng ta sẽ cài đặt Ruby, ở đây là Ruby 2.7.2

```shell 
RUBY_CONFIGURE_OPTS=--with-jemalloc rbenv install 2.7.2
rbenv global 2.7.2
```

### Chúng ta cũng sẽ cần bundler nữa
```shell
gem install bundler --no-document
```

## Cài đặt PostgreSQL 10
```
wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
echo "deb http://apt.postgresql.org/pub/repos/apt/ $(lsb_release -cs)-pgdg main" | sudo tee /etc/apt/sources.list.d/postgresql-pgdg.list > /dev/null
sudo apt-get update
```

## Cài đặt Redis
```
sudo apt install redis-server
```


## Checkout Mã nguồn

```shell
git clone https://github.com/vuongdt23/SE301.M11 mastodon && cd mastodon
```
## Cài đặt các dependency còn lại
```shell
bundle install
yarn install
```

## Đảm bảo rằng các server Posgre và Redis đang chạy

```
sudo service redis-server start
sudo service postgresql start
```

## Tạo một user trong PosgreSQL cùng tên với User hiện tại
Thay "your_user_name" bằng Username hiện tại của bạn
```
sudo -u postgres createuser your_user_name --createdb
```

## Cài đặt các cơ sở dữ liệu dev và test
```
RAILS_ENV=development bundle exec rails db:setup
```

## Khởi động server
```
RAILS_ENV=development bundle exec rails server
```

Ứng dụng Mastodon sẽ được chạy trên port 3000.

