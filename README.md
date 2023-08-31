# PHP Goodies 🐘

## Profile a script to get a list of all function calls sorted by cumulative time:
```
apt install php-xdebug

### PHP 7
php -d xdebug.profiler_enable=1 -d xdebug.profiler_output_dir=. the_script.php
### PHP 8:
php -d xdebug.mode=profile -d xdebug.output_dir=. the_script.php

apt install valgrind
callgrind_annotate cachegrind.out... > profile.txt
```

## Profile a all scripts processed via Apache:
```
apt install php-xdebug

### PHP 7:
echo -e "xdebug.profiler_enable=1\nxdebug.profiler_output_dir=/tmp" >> /etc/php/7.3/apache2/php.ini
### PHP 8:
echo -e "xdebug.mode=profile\nxdebug.output_dir=/tmp" >> /etc/php/8.2/apache2/php.ini

service apache2 restart

apt install valgrind
cd /tmp
callgrind_annotate cachegrind.out... > profile.txt
```
