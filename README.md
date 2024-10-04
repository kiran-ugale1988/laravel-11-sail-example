## Setup 
Windows using WSL Ubuntu install PHP and switch php version

ubuntu@DESKTOP-994R1LE:/var/www/html$ sudo apt install php8.2
ubuntu@DESKTOP-994R1LE:/var/www/html$ sudo update-alternatives --config php
There are 3 choices for the alternative php (providing /usr/bin/php).

  Selection    Path             Priority   Status
------------------------------------------------------------
  0            /usr/bin/php8.3   83        auto mode
* 1            /usr/bin/php7.3   73        manual mode
  2            /usr/bin/php8.2   82        manual mode
  3            /usr/bin/php8.3   83        manual mode
Press <enter> to keep the current choice[*], or type selection number: 2
update-alternatives: using /usr/bin/php8.2 to provide /usr/bin/php (php) in manual mode

ubuntu@DESKTOP-994R1LE:/var/www/html$ php -v
PHP 8.2.24 (cli) (built: Sep 27 2024 04:04:39) (NTS)
Copyright (c) The PHP Group
Zend Engine v4.2.24, Copyright (c) Zend Technologies
    with Zend OPcache v8.2.24, Copyright (c), by Zend Technologies


Install Laravel Sail Using ubuntu WSL
https://laravel.com/docs/11.x/installation#sail-on-windows


Below command will start installation of laravel application and automatically start laravel sail installation 

ubuntu@DESKTOP-994R1LE:/var/www/html$ curl -s https://laravel.build/laravel-11-sail-example | bash

It will take some to install then you can run laravel sail up command:

cd laravel-11-sail-example 
ubuntu@DESKTOP-994R1LE:/var/www/html/laravel-11-sail-example$./vendor/bin/sail up

like this command: php artisan migrate 
you can run using sail command like below:
ubuntu@DESKTOP-994R1LE:/var/www/html/laravel-11-sail-example$./vendor/bin/sail artisan migrate


Run Application console in docker container:
	ubuntu@DESKTOP-994R1LE:/var/www/html/laravel-11-sail-example$ docker exec -it laravel-11-sail-example-laravel.test-1 bash
	root@eb2b6e3226c1:/var/www/html#

	root@eb2b6e3226c1:/var/www/html# php artisan tinker
	Psy Shell v0.12.4 (PHP 8.3.12 — cli) by Justin Hileman
	
Or using sail command:

ubuntu@DESKTOP-994R1LE:/var/www/html/laravel-11-sail-example$ ./vendor/bin/sail tinker
Psy Shell v0.12.4 (PHP 8.3.12 — cli) by Justin Hileman
>
	

ubuntu@DESKTOP-994R1LE:/var/www/html/laravel-11-sail-example$ ./vendor/bin/sail up
Press=> ctrl+c to stop 

Add port in .env file
APP_PORT=8081

again run docker 
ubuntu@DESKTOP-994R1LE:/var/www/html/laravel-11-sail-example$ ./vendor/bin/sail up

http://localhost:8081/