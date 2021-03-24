# raspberry-pi-update-php
```
how to update php in raspberry pi
```

## Check if you can install php7.4
```
sudo apt install --dry-run php7.4
```


## php version is not available add new version
```
sudo wget -O /etc/apt/trusted.gpg.d/php.gpg https://packages.sury.org/php/apt.gpg
echo "deb https://packages.sury.org/php/ buster main" | sudo tee /etc/apt/sources.list.d/php.list
sudo apt update
```


## install php7.4
```
sudo apt install -y php7.4-common php7.4-fpm php7.4-cli php7.4-curl php7.4-json php7.4-mysql php7.4-opcache php7.4-gd php7.4-sqlite3 php7.4-mbstring php7.4-zip php7.4-readline php-pear
```


## check version of php
```
php -v
```


## change config
```
sudo nano /etc/php/7.4/fpm/conf.d/90-pi-custom.ini.
```

## edit file
```
cgi.fix_pathinfo=0

upload_max_filesize=64m
post_max_size=64m
max_execution_time=600
```

## restart service
```
sudo service php7.4-fpm reload
```

## check configuration
```
php -i
```
