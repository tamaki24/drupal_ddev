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
