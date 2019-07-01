# How to Install Free Extensions for EasyPHP Devserver v16

These updates created without EasyPHP Warehouse.

## PHP

1. [Download PHP (Thread Safe Version)](http://windows.php.net/download)
  
   
2. Create folder in "eds-binaries/php" for new PHP
 * Name should be like "php7016vc14x86"

3. Copy these files from any installed PHP from "eds-binaries/php" to new PHP

 * eds-app-actions.php
 * eds-app-dashboard.php
 * eds-app-launch.exe
 * eds-app-settings.php

4. Edit "eds-app-settings.php" for new PHP version

 ```PHP
	'app_version'				=>	"7.0.16 x86",
	'app_version_nb'			=>	"7.0.16",
	'app_build'					=>	"VC14",
	'app_mode'					=>	"x86 (32-bit)",
	'app_architecture'			=>	"x86",
 ```

5. Copy "php.ini" from current php of EasyPHP. (Tested in PHP 5.6.X and 7.0.X)


## Xdebug

1. [Download Xdebug](https://xdebug.org/download.php) for your PHP version

2. Copy "php_xdebug-2.5.0-7.0-vc14.dll" to PHP folder

3. Edit "eds-app-settings.php" for Xdebug version and for file which you downloaded

 ```PHP
	'xdebug_version'			=>	"2.5.0",
	'xdebug_dll'				=>	"php_xdebug-2.5.0-7.0-vc14.dll"
 ```

4. Edit "php.ini"

 * zend_extension = "" will be created by EasyPHP directly. (Tested)
 * xdebug.default_enable=1 to load extension
 * xdebug.auto_trace=1 to start trace
 * xdebug.profiler_enable=1 to start profiler
 
 ```
zend_extension = ""
xdebug.default_enable=1
xdebug.remote_enable=1
xdebug.remote_host=127.0.0.1
xdebug.remote_port=9009
xdebug.remote_handler=dbgp
xdebug.remote_mode=req
xdebug.remote_autostart = false
xdebug.dump_globals=1
xdebug.dump=COOKIE,FILES,GET,POST,REQUEST,SERVER,SESSION
xdebug.dump.SERVER=REMOTE_ADDR,REQUEST_METHOD,REQUEST_URI
xdebug.show_local_vars=1
xdebug.show_mem_delta=1
xdebug.collect_includes=1
xdebug.collect_vars=1
xdebug.collect_params=4
xdebug.collect_return=1
xdebug.auto_trace=0
xdebug.trace_options=0
xdebug.trace_format=0
xdebug.trace_output_dir="C:\Program Files (x86)\EasyPHP-Devserver-16.1\eds-binaries\xdebug\trace"
xdebug.trace_output_name="trace.%t"
xdebug.profiler_enable=0
xdebug.profiler_append=1
xdebug.profiler_enable_trigger=1
xdebug.profiler_output_dir="C:\Program Files (x86)\EasyPHP-Devserver-16.1\eds-binaries\xdebug\profiler"
xdebug.profiler_output_name="cachegrind.out.%s.%t"
 ```
 
 
## To Do List
1. Xdebug Manager for EasyPHP
2. and more...


## Others
#### Xdebug Profiler Viewer
   - [WinCacheGrid](https://github.com/ceefour/wincachegrind)
