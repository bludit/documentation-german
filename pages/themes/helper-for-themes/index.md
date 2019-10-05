# Helper-Klassen für Themes
<!-- Position: 100 -->

Die Helper unterstützen den Entwickler dabei den Code übersichtlicher zu gestalten und geben die Möglichkeit, weniger
Code schreiben zu müssen.

Diese Objekte besitzen statische Methoden (zu sehen an den Doppelpunkten beim Aufruf)

## Title
Erzeugt einen Titel-Head-Tag mit dynamischen Inhalt aus den Einstellungen der Seite.
```php
<?php
	echo Theme::headTitle();
?>
```

```
<title>Page title | Title site</title>
```

## Description
Erzeugt einen Description-Head-Tag mit dynamischen Inhalt aus den Einstellungen der Seite.
```php
<?php
	echo Theme::headDescription();
?>
```

```
<meta name="description" content="Description about your site">
```

## CSS Dateien
Diese Methode generiert einen Stylesheet-Head-Tag um eine CSS mit dem Namen `blog.css` aus dem Ordner `/bludit/themes/{THEME_NAME}/css/` einzufügen.
```php
<?php
	echo Theme::css('css/blog.css');
?>
```

```
<link rel="stylesheet" type="text/css" href="https://example.com/bl-themes/{THEME_NAME}/css/blog.css">
```

Es gibt auch die Möglichkeit gleich mehrere CSS Einträge zu erstellen.
<pre><code data-language="php"><?php
	echo Theme::css(array('css/file1.css', 'css/file2.css'));
?></code></pre>

```
<link rel="stylesheet" type="text/css" href="https://example.com/bl-themes/{THEME_NAME}/css/file1.css">
<link rel="stylesheet" type="text/css" href="https://example.com/bl-themes/{THEME_NAME}/css/file2.css">
```

## Javascript Dateien
Diese Methode generiert einen Script-Head-Tag um eine Javascript-Datei mit dem Namen `main.js` aus dem Ordner `/bludit/themes/{THEME_NAME}/js/` einzufügen.

```php
<?php
	echo Theme::js('js/main.js');
?>
```

```
<script src="https://example.com/bl-themes/{THEME_NAME}/js/main.js"></script>
```

Es gibt auch die Möglichkeit gleich mehrere Script Einträge zu erstellen.
```php
<?php
	echo Theme::js(array('js/file1.js', 'js/file2.js'));
?>
```

```
<script src="https://example.com/bl-themes/{THEME_NAME}/js/file1.js"></script>
<script src="https://example.com/bl-themes/{THEME_NAME}/js/file2.js"></script>
```

## Favicon
Diese Methode generiert einen Head-Tag für das Favicon. In diesem Beispiel befindet sich das Icon im Hauptverzeichnis des Themes `/bludit/themes/{THEME_NAME}/favicon.png`.

<pre><code data-language="php"><?php
	echo Theme::favicon('favicon.png');
?></code></pre>

```
<link rel="shortcut icon" href="https://examples.com/bl-themes/{THEME_NAME}/favicon.png" type="image/png">
```

## Plugins einbinden
Bludit unterstützt Plugins. Jedes Plugin besitzt Hooks (Einhängepunkte) über die man steuern kann, an welcher Stelle ein Plugin beim Seitenaufbau aktiv werden soll.

Im folgenden Beispiel werden alle Plugins im Head-Bereich ausgeführt.

```php
<?php
	Theme::plugins('siteHead');
?>
```

Hinzufügen aller Plugins beim Beginn des Body-Abschnitts.
```php
<?php
	Theme::plugins('siteBodyBegin');
?>
```

## jQuery einbinden
Bludit verwendet [jQuery](http://jquery.com) und stellt eine Methode für das Einbinden zur Verfügung.

```php
<?php
	echo Theme::jquery();
?>
````

```
<script src="https://example.com/bl-kernel/js/jquery.min.js"></script>
```

Man kann [jQuery](http://jquery.com) auch vom offiziellen CDN einbinden.

```php
<?php
	$cdn = true;
	echo Theme::jquery($cdn);
?>
```

```
<script src="https://code.jquery.com/jquery-3.2.1.min.js" integrity="sha256-hwg4gsxgFZhOsEEamdOYGBf13FyQuiTwlAQgxVSNgt4=" crossorigin="anonymous"></script>
```

## FontAwesome einbinden
Bludit verwendet [FontAwesome](http://fontawesome.io) und stellt eine Methode für das Einbinden zur Verfügung.

```php
<?php
	echo Theme::fontAwesome();
?>
```

```
<link rel="stylesheet" href="https://example.com/bl-kernel/css/font-awesome/css/font-awesome.min.css">
```

Man kann [FontAwesome](http://fontawesome.io) auch vom offiziellen CDN [BootstrapCDN](https://www.bootstrapcdn.com) einbinden.

```php
<?php
	$cdn = true;
	echo Theme::fontAwesome($cdn);
?>
```

```
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css">
```
