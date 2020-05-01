
# Ref

## DB
- [tables](https://wiki.dolibarr.org/index.php/Category:Table_SQL)
- `htdocs\install\mysql\tables\`


# Env

## mysql: binary log

1. sudo vi /etc/mysql/my.cnf

```
[mysqld]

log_bin=mysql-bin_log
server-id=1

```
or
```
mysql=/etc/mysql/my.cnf
me=/vagrant/www/dolibarr-study/my.cnf 
sudo cp -f $mysql $me
vi $me
sudo cp -f $me $mysql
```


2. 
```
sudo service mysql restart

mysql -uroot -pXXXXXXX -e "show variables like '%log_b%';"

mysql -uroot -pXXXXXXX -e "show variables like '%binlog%';"

mysql -uroot -pXXXXXXX -e "show master logs;"
```


## git
1. `git clone https://github.com/Dolibarr/dolibarr.git`
2. `cd dolibarr`
3. for downsizing, add items to .gitignore
```
htdocs/includes/
htdocs/langs/
*.png
*.svg
*.jpg
*.gif
*.ico
htdocs/theme/common/fontawesome-5/
htdocs/install/
```
4. remove `htdocs/conf/conf.php` from .gitignore
4. remove .gitignore files under subdir, like `htdocs\custom\.gitignore` to monitor changes in there dirs.
5. `git init`
6. `git add . && git commit -m "first"

## php and debug
1. create a mysql database `CREATE DATABASE IF NOT EXISTS xx DEFAULT CHARSET utf8mb4 COLLATE utf8mb4_unicode_ci;`
2. enable `gd2`,`intl`,`mysqli`and `php_xdebug` in `D:\A\Scoop\apps\php7.4\current\php.ini`, and `xdebug.idekey=PHPSTORM`
3. `php -S localhost:8000`
4. firefox addon [xdebug-ext-quantum](https://addons.mozilla.org/en-US/firefox/addon/xdebug-ext-quantum/), and set idekey
5. phpstorm, DBGp Proxy -> IDE key: PHPSTORM
6. visit `localhost:8000/install`

## Dolibarr

1. rename `composer.json` to `composer-doli.json` as [patches in 3rd packages](https://github.com/Dolibarr/dolibarr/pull/11224)


1. enable modules: `Debug Logs`
2. use 3rd modules: 
  - DoliMyAdmin https://wiki.dolibarr.org/index.php/Module_DoliMyAdmin_(Administration_of_Dolibarr_Database)
  - Module Extra Admin Tools EN https://wiki.dolibarr.org/index.php/Module_Extra_Admin_Tools_EN
