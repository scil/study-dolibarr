# study-dolibarr

## warning
do not use `composer update` as [patches in 3rd packages](https://github.com/Dolibarr/dolibarr/pull/11224)

# Env

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



