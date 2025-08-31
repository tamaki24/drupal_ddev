# drupal for DDEV

# premise
docker

# DDEV install
```
# mac
brew install ddev/ddev/ddev

# wsl2
curl -fsSL https://ddev.com/install.sh | bash

# Initialize mkcert (共通)
mkcert -install

# check
ddev -v
```
[DDEV Install](https://docs.ddev.com/en/stable/users/install/ddev-installation/#macos)


# project settings
```
mkdir project-name && cd project-name

ddev config --project-type=drupal10 --docroot=web --create-docroot
ddev start
ddev composer create "drupal/recomended-project"

# command line tool
ddev composer require drush/drush
```
[DDEV CMS Quickstarts Drupal](https://docs.ddev.com/en/stable/users/quickstart/#drupal)

# Go 🚀
```
ddev launch
```

# After Clone
```
# 起動
ddev start

# 依存パッケージのインストール
ddev composer install

# Drupalのセットアップ（初回）
ddev drush site:install --account-name=admin --account-pass=admin

# 起動
ddev launch
```

# etc

## PHP Version
```
# .ddev/config.yaml
php_version: "X.X"
```

## DDEV restart
```
ddev restart
```

## Language settings
ConfigurationにLanguagesなどの項目がない場合
```
# モジュールの有効化
ddev drush en language content_translation config_translation -y
```

## 設定（config/sync）の保存先を変更
### settings.php 末尾に追記
```
$settings['config_sync_directory'] = '../config/sync';
```
### ディレクトリの作成
```
mkdir -p config/sync
```

### drushで設定
```
ddev drush config:export
```

