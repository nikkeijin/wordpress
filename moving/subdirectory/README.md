# Move Your WordPress Files Out of the Root Directory

1 - Move ALL of the WordPress core files into a subdirectory.\
2 - Copy the index.php and .htaccess file to the root.\
3 - Update MySQL DB.

> Update MySQL DB

```
UPDATE wp_options SET option_value = replace(option_value, 'https://x.co.jp', 'https://y.co.jp') WHERE option_name = 'home' = 'siteurl';
```

```
UPDATE wp_options SET option_value = replace(option_value, 'https://x.co.jp', 'https://y.co.jp/subdirectory') WHERE option_name = 'siteurl';
```

```
UPDATE wp_posts SET post_content = replace(post_content, 'https://x.co.jp', 'https://y.co.jp/subdirectory');
```

```
UPDATE wp_postmeta SET meta_value = replace(meta_value,'https://x.co.jp','https://y.co.jp/subdirectory');
```

More information: https://wordpress.org/support/article/giving-wordpress-its-own-directory/