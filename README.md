# KVwpBaseHtaccess
Basic .htaccess file to WordPress

Ha www nélkül használjuk az adott domaint, akkor a **.htaccess** file 399. sorában tegyük elérhetővé az átirányítást a www.domain.name-ről a domain.name-re.

```apache
#<IfModule mod_rewrite.c>
#  RewriteCond %{HTTPS} !=on
#  RewriteCond %{HTTP_HOST} ^www\.(.+)$ [NC]
#  RewriteRule ^ http://%1%{REQUEST_URI} [R=301,L]
#</IfModule>
```

## Hozzáadott új funkciók:

**wp-config.php-file védelme**

```apache
<files wp-config.php>
  order allow,deny
  deny from all
</files>
```


**.htaccess file védelme**

```apache
<files ~ "^.*\.([Hh][Tt][Aa])">
  order allow,deny
  deny from all
  satisfy all
</files>
```
