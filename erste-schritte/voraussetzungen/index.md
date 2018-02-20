# Title: Voraussetzungen
<!-- Position: 2 -->
---
Alles, was es braucht, ist ein Server, auf dem PHP läuft.

Auf diesem muss folgendes installiert sein:

- PHP v5.3 oder höher.
- Die PHP-Erweiterung [mbstring](http://php.net/manual/de/book.mbstring.php) zur Unterstützung von UTF-8.
- Die PHP-Bibliothek [GD](http://php.net/manual/de/book.image.php) zur Bildverarbeitung.
- Die PHP-Erweiterung [DOM](http://php.net/manual/de/book.dom.php) für den Zugriff auf XML-Dokumente.
- Die PHP-Erweiterung [JSON](http://php.net/manual/de/book.json.php) für die Verwendung des Datenaustauschformats JSON.
- Unterstützt werden folgende Server:
  * Bludit läuft auf fast jedem Webserver
  * [Eingebauter PHP-Webserver](http://php.net/manual/de/features.commandline.webserver.php)
  * Nginx mit dem Modul [ngx_http_rewrite_module](http://nginx.org/en/docs/http/ngx_http_rewrite_module.html)
  * Apache mit dem Modul [mod_rewrite](http://httpd.apache.org/docs/current/mod/mod_rewrite.html)
  * Lighttpd mit dem Modul [mod_rewrite](http://redmine.lighttpd.net/projects/1/wiki/docs_modrewrite)
  * Hiawatha mit [rewrite rules](https://www.hiawatha-webserver.org/howto/url_rewrite_rules)
  * H2O, vgl. dazu im Support-Forum den Eintrag [H2O HTTP/2 web server and Bludit](https://forum.bludit.org/viewtopic.php?f=6&t=1015)
  
