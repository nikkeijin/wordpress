# Moving your WordPress

> Setup wp-config.php

```
/** The name of the database for WordPress */
define('DB_NAME', 'database_name_here');
```

```
/** MySQL database username */
define('DB_USER', 'username_here');
```

```
/** MySQL database password */
define('DB_PASSWORD', 'password_here');
```

> Update MySQL

```
UPDATE wp_options SET option_value = replace(option_value, 'https://x.co.jp', 'https://y.co.jp') WHERE option_name = 'home' OR option_name = 'siteurl';
```

```
UPDATE wp_posts SET post_content = replace(post_content, 'https://x.co.jp', 'https://y.co.jp');
```

```
UPDATE wp_postmeta SET meta_value = replace(meta_value,'https://x.co.jp','https://y.co.jp');
```

# Troubleshooting

> Home page is the only page loading

Log-in wp-admin and then go to Settings > Permalinks

Press save button and the .htaccess will update the Permalinks.

> Fixing wp-admin path

Open wp-config.php and add the following code:

```
define( 'WP_HOME', 'http://y.co.jp' );
define( 'WP_SITEURL', 'http://y.co.jp' );
```

> How to Increase Maximum Upload File Size in WordPress

Open .htaccess and add the following code:

```
php_value upload_max_filesize 128M
php_value post_max_size 128M
php_value memory_limit 256M
php_value max_execution_time 300
php_value max_input_time 300
```

Open wp-config.php and add the following code:

```
@ini_set( 'upload_max_filesize' , '128M' );
@ini_set( 'post_max_size', '128M');
@ini_set( 'memory_limit', '256M' );
@ini_set( 'max_execution_time', '300' );
@ini_set( 'max_input_time', '300' );
```

> Extracting data from All-in-One WP Migration

```
npx wpress-extract your-migration.wpress
```