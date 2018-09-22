# Beispiel: Mein erstes Theme
<!-- Position: 2 -->

Nachfolgend erstellen wir ein neues, einfaches Theme mit dem Namen 'Coffee'.

- Erstelle das Theme-Verzeichnis im Verzeichnis `/bl-themes/`, in unserem Fall `/bl-themes/coffee/`
- Erstelle das Verzeichnis `languages` im Theme-Verzeichnis `/bl-themes/coffee/`
- Erstelle die Datei `en.json` im Verzeichnis `/bl-themes/coffee/languages/`
- Erstelle die Datei `metadata.json` im Verzeichnis `/bl-themes/coffee/`
- Erstelle die Datei `index.php` im Verzeichnis `/bl-themes/coffee/`

Die Verzeichnisstruktur mit den eben erstellten Dateien muss jetzt so aussehen:
```
/bl-themes/coffee/
	language/en.json
	metadata.json
	index.php
```

Im nächsten Schritt erstellen wir den Inhalt der Dateien. Wir beginnen mit der Datei `index.php` und fügen dieser folgenden HTML und PHP Code zu.
<pre><code data-language="html"><!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">
	<title>Bludit</title>
</head>
<body>
	<?php foreach ($pages as $Page): ?>

	<h1><?php echo $Page->title() ?></h1>
	<div><?php echo $Page->content() ?></div>

	<hr>

	<?php endforeach; ?>
</body>
</html>
</code></pre>

Bearbeite jetzt die Datei `languages/en.json` um den Namen und die Beschreibung des Themes hinzuzufügen.
<pre><code data-language="php">{
	"theme-data":
	{
		"name": "Coffee",
		"description": "This is my first theme for Bludit."
	}
}
</code></pre>

Jetzt bearbeiten wir die Datei `metadata.json` um die Informationen über das Theme zu vervollständigen.
<pre><code data-language="php">{
	"author": "Bludit",
	"email": "",
	"website": "",
	"version": "1.0",
	"releaseDate": "2017-10-10",
	"license": "MIT",
	"compatible": "2.0",
	"notes": ""
}
</code></pre>

Herzlichen Glückwunsch, du hast soeben dein erstes Theme für Bludit erstellt!

<div class="note">
<div class="title">Beispiele</div>
Wir haben ein Gibhub-Repository mit Beispielen, welches du unter folgendem Link findest: <a href="https://github.com/bludit/examples">Bludit Theme Beispiele</a>.
</div>
