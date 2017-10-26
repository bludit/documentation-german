# Title: Voraussetzungen
<!-- Position: 2 -->
---
Alles, was es braucht, ist ein Server, auf dem PHP läuft.

Auf diesem muss folgendes installiert sein:

- PHP v5.3 oder höher.
- Das PHP-Modul [mbstring](http://php.net/manual/en/book.mbstring.php) zur Unterstützung von UTF-8.
- Das PHP-Modul [gd](http://php.net/manual/en/book.image.php) für die Bildbearbeitung.
- Das PHP-Modul [dom](http://php.net/manual/en/book.dom.php) module for DOM manipulation.
- Das PHP-Modul [json](http://php.net/manual/en/book.json.php) module for JSON manipulation.
- Unterstützt werden folgende Server:
  * Bludit supports almost every webservers
  * [PHP Built-in Webserver](http://php.net/manual/en/features.commandline.webserver.php)
  * Nginx mit dem Modul [ngx_http_rewrite_module](http://nginx.org/en/docs/http/ngx_http_rewrite_module.html)
  * Apache mit dem Modul [mod_rewrite](http://httpd.apache.org/docs/current/mod/mod_rewrite.html)
  * Lighttpd mit dem Modul [mod_rewrite](http://redmine.lighttpd.net/projects/1/wiki/docs_modrewrite)
  * Hiawatha mit [rewrite rules](https://www.hiawatha-webserver.org/howto/url_rewrite_rules)
  * H2O, [forum topic](https://forum.bludit.org/viewtopic.php?f=6&t=1015)
  
