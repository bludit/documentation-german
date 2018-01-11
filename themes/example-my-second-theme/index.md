# Title: Beispiel: Mein zweites Theme
<!-- Position: 3 -->
---
## 1. Verzeichnisstruktur
Jetzt erstellen wir die Verzeichnisstruktur für das Theme. Dieses nennen wir `Mars`.
Erstelle das Theme-Verzeichnis im Verzeichnis `/bl-themes/`, in unserem Fall `/bl-themes/mars/`.

Jetzt erstellen wir die Unterverzeichnisse languages, css und js:
- Erstelle das Verzeichnis `languages` im Theme-Verzeichnis `/bl-themes/mars/`
- Erstelle das Verzeichnis `css` im Theme-Verzeichnis `/bl-themes/mars/`
- Erstelle das Verzeichnis `js` im Theme-Verzeichnis `/bl-themes/mars/`

Die Verzeichnisstruktur sollte jetzt so aussehen:
```
/bl-themes/mars/
	css/
	js/
	language/
```

## 2. Themeinformationen
Erstelle eine Datei mit dem Namen `metadata.json` im Theme-Verzeichnis und dem folgenden Inhalt:

```
{
	"author": "Bludit",
	"email": "",
	"website": "",
	"version": "1.0",
	"releaseDate": "2017-10-10",
	"license": "MIT",
	"compatible": "2.0",
	"notes": ""
}
```

Jetzt erstelle eine Datei `en.json` im Verzeichnis `/bl-themes/mars/languages/` mit folgendem Inhalt:

```
{
	"theme-data":
	{
		"name": "Mars",
		"description": "This is my second theme for Bludit."
	}
}
```

## 3. index.php
Jetzt arbeiten wir an der Datei `index.php`. Erstelle diese im Theme-Verzeichnis `/bl-themes/mars/` mit folgendem Inhalt:

<pre><code data-language="html"><!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">
</head>
<body>

</body>
</html>
</code></pre>

### 3.1. CSS Dateien
CSS-Dateien können einfach in das Theme eingebunden werden. Dies kann über das Tag `link` geschehen oder über den Bludit-Helper `Theme::`. Nachfolgend verwenden wir zweiteres und fügen die Datei `blog.css` in das Theme ein.

<pre><code data-language="html"><!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- CSS -->
	<?php echo Theme::css('css/blog.css') ?>
</head>
<body>

</body>
</html>
</code></pre>

### 3.2. JavaScript Dateien
JavaScript-Dateien können einfach in das Theme eingebunden werden. Dies kann über das Tag `link` geschehen oder über den Bludit-Helper `Theme::`. Nachfolgend verwenden wir zweiteres und fügen die Datei `blog.js` in das Theme ein.

<pre><code data-language="html"><!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- CSS -->
	<?php echo Theme::css('css/blog.css') ?>

	<!-- Javascript -->
	<?php echo Theme::javascript('js/blog.js') ?>
</head>
<body>

</body>
</html>
</code></pre>

### 3.3. Plugins mit dem hook siteHead
Damit Plugins funktionieren müssen Hooks mit dem Helper `Theme::plugins` gesetzt werden.
Nachfolgend setzen wir den Hook für die Plugins, die bei den SiteHeads ausgeführt werden sollen.

<pre><code data-language="html"><!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- CSS -->
	<?php echo Theme::css('css/blog.css') ?>

	<!-- Javascript -->
	<?php echo Theme::javascript('js/blog.js') ?>

	<!-- Load plugins with the hook siteHead -->
	<?php Theme::plugins('siteHead') ?>
</head>
<body>

</body>
</html>
</code></pre>

### 3.4. Seitentitel
Der Seitentitel wird in den Bereichen Head und Body gesetzt.

<pre><code data-language="html"><!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- Meta tag Title -->
	<title><?php echo $Site->title() ?></title>

	<!-- CSS -->
	<?php echo Theme::css('css/blog.css') ?>

	<!-- Javascript -->
	<?php echo Theme::javascript('js/blog.js') ?>

	<!-- Load plugins with the hook siteHead -->
	<?php Theme::plugins('siteHead') ?>
</head>
<body>
	<!-- Site Title -->
	<h1><?php echo $Site->title() ?></h1>
</body>
</html>
</code></pre>

### 3.5. Inhalt
Jetzt fügen wir Beitragsinhalte auf der Seite ein.

Um zu ermitteln auf welcher Seite der User sich gerade befindet kann die Variable `$WHERE_AM_I` verwendet werden.
Wenn der User zum Beispiel eine Seite (einen Inhalt) ansieht hat der Wert der Variable `page`, befindet er sich auf der Startseite, dann ist der Wert `home`.

<pre><code data-language="html"><!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- Meta tag Title -->
	<title><?php echo $Site->title() ?></title>

	<!-- CSS -->
	<?php echo Theme::css('css/blog.css') ?>

	<!-- Javascript -->
	<?php echo Theme::javascript('js/blog.js') ?>

	<!-- Plugins site head -->
	<?php Theme::plugins('siteHead') ?>
</head>
<body>
	<!-- Site Title -->
	<h1><?php echo $Site->title() ?></h1>

	<?php
		if ($Url->whereAmI()=='home') {
			echo 'The user is browsing the front page';
		}
		elseif ($Url->whereAmI()=='page') {
			echo 'The user is browsing a particular page';
		}
		elseif ($Url->whereAmI()=='category') {
			echo 'The user is browsing a particular category';
		}
		elseif ($Url->whereAmI()=='tag') {
			echo 'The user is browsing a particular tag';
		}
	?>
</body>
</html>
</code></pre>

Befindet sich der User auf der Startseite generiert Bludit ein Array `$pages` mit allen veröffentlichten Seiten. Jede Seite ist hierbei ein [Seiten Objekt](https://).

<pre><code data-language="html"><!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- Meta tag Title -->
	<title><?php echo $Site->title() ?></title>

	<!-- CSS -->
	<?php echo Theme::css('css/blog.css') ?>

	<!-- Javascript -->
	<?php echo Theme::javascript('js/blog.js') ?>

	<!-- Plugins site head -->
	<?php Theme::plugins('siteHead') ?>
</head>
<body>
	<!-- Site Title -->
	<h1><?php echo $Site->title() ?></h1>

	<?php
		if ($Url->whereAmI()=='home') {
			foreach ($pages as $Page) {
				echo '<h1>'.$Page->title().'</h1>';
				echo '<div>'.$Page->content().'</div>';
				echo '<hr>';
			}
		}
		elseif ($Url->whereAmI()=='page') {
			echo 'The user is browsing a particular page';
		}
		elseif ($Url->whereAmI()=='category') {
			echo 'The user is browsing a particular category';
		}
		elseif ($Url->whereAmI()=='tag') {
			echo 'The user is browsing a particular tag';
		}
	?>
</body>
</html>
</code></pre>

Sieht sich der User eine bestimmte Seite an, generiert Bludit ein Objekt mit dem Namen `$Page`, die viele Methoden zur Verfügung stellt.
In unserem Beispiel verwenden wir die Methoden `title()` und `content()`. Um die anderen Methoden kennen zu lernen schau dir die folgende Seite an: [Page Object](http://)

<pre><code data-language="html"><!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- Meta tag Title -->
	<title><?php echo $Site->title() ?></title>

	<!-- CSS -->
	<?php echo Theme::css('css/blog.css') ?>

	<!-- Javascript -->
	<?php echo Theme::javascript('js/blog.js') ?>

	<!-- Plugins site head -->
	<?php Theme::plugins('siteHead') ?>
</head>
<body>
	<!-- Site Title -->
	<h1><?php echo $Site->title() ?></h1>

	<?php
		if ($Url->whereAmI()=='home') {
			foreach ($pages as $Page) {
				echo '<h1>'.$Page->title().'</h1>';
				echo '<div>'.$Page->content().'</div>';
				echo '<hr>';
			}
		}
		elseif ($Url->whereAmI()=='page') {
			echo '<h1>'.$Page->title().'</h1>';
			echo '<div>'.$Page->content().'</div>';
		}
		elseif ($Url->whereAmI()=='category') {
			echo 'The user is browsing a particular category';
		}
		elseif ($Url->whereAmI()=='tag') {
			echo 'The user is browsing a particular tag';
		}
	?>
</body>
</html>
</code></pre>

### 3.6. Plugin Unterstützung für die Hooks 'site body begins' und 'site body ends'
Um unser Theme fertigzustellen fügen wir noch die Funktionen für Plugins hinzu.

<pre><code data-language="html"><!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">

	<!-- Meta tag Title -->
	<title><?php echo $Site->title() ?></title>

	<!-- CSS -->
	<?php echo Theme::css('css/blog.css') ?>

	<!-- Javascript -->
	<?php echo Theme::javascript('js/blog.js') ?>

	<!-- Plugins site head -->
	<?php Theme::plugins('siteHead') ?>
</head>
<body>
	<!-- Plugins site body begin -->
	<?php Theme::plugins('siteBodyBegin') ?>

	<!-- Site Title -->
	<h1><?php echo $Site->title() ?></h1>

	<?php
		if ($Url->whereAmI()=='home') {
			foreach ($pages as $Page) {
				echo '<h1>'.$Page->title().'</h1>';
				echo '<div>'.$Page->content().'</div>';
				echo '<hr>';
			}
		}
		elseif ($Url->whereAmI()=='page') {
			echo '<h1>'.$Page->title().'</h1>';
			echo '<div>'.$Page->content().'</div>';
		}
		elseif ($Url->whereAmI()=='category') {
			echo 'The user is browsing a particular category';
		}
		elseif ($Url->whereAmI()=='tag') {
			echo 'The user is browsing a particular tag';
		}
	?>

	<!-- Plugins site body end -->
	<?php Theme::plugins('siteBodyEnd') ?>

</body>
</html>
</code></pre>

<div class="note">
<div class="title">Beispiele</div>
Wir haben ein Gibhub-Repository mit Beispielen, welches du unter folgendem Link findest: <a href="https://github.com/bludit/examples">Bludit Theme Beispiele</a>.
</div>
