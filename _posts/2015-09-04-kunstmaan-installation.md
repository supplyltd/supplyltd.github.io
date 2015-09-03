---
published: false
---

[Symfony](http://symfony.com/doc/current/book/installation.html#checking-symfony-application-configuration-and-setup)
[Kunstmaan](https://bundles.kunstmaan.be/documentation/installation)

## Install
`composer create-project kunstmaan/bundles-standard-edition myprojectname`

database_host: [hostname]

database_name: [dbname]

database_user: [dbuser]

database_password: [dbpassword]

## Generating a bundle
app/console kuma:generate:bundle

[ProjectName]\[NameOfBundle]

## Generating site
app/console kuma:generate:default-site

## Initialising the database
app/console doctrine:database:create

app/console doctrine:schema:create

app/console doctrine:fixtures:load

* Check your username and password in Terminal

* To change password: `app/console fos:user:change`

# Front-end assets
npm install -g bower

npm install -g gulp

npm install -g uglify-js

npm install -g uglifycss

## Permission
rm -rf app/cache/*

rm -rf app/logs/*

HTTPDUSER=`ps aux | grep -E '[a]pache|[h]ttpd|[_]www|[w]ww-data|[n]ginx' | grep -v root | head -1 | cut -d\  -f1`

sudo chmod +a "$HTTPDUSER allow delete,write,append,file_inherit,directory_inherit" app/cache app/logs

sudo chmod +a "`whoami` allow delete,write,append,file_inherit,directory_inherit" app/cache app/logs

## VirtualHost
	<VirtualHost *:80>
      DocumentRoot "[directory]"
      ServerName [URL]
      SetEnv APP_ENV "dev"
	</VirtualHost>

# Executing 
bundle install

npm install

bower install

gulp build

app/console assets:install --symlink

app/console assetic:dump




