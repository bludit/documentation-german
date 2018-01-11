# Title: Verzeichnisstruktur
<!-- Position: 1 -->
---
Das ist die Verzeichnisstruktur von Bludit.

```
bl-content/
bl-kernel/
bl-languages/
bl-plugins/
bl-themes/
```

## bl-content
Dieses Verzeichnis ist sehr wichtig, da Bludit dort alle Dateien - Datenbanken als auch Bilder - ablegt. Vor einem Update wird dringend dazu geraten, von diesem Verzeichnis eine Sicherung anzulegen.

```
bl-content/

	databases/
		plugins/		<-- Database: plugins
		pages.php		<-- Database: pages
		security.php		<-- Database: black list, brute force protection, others
		site.php		<-- Database: site variables, name, description, slogan, others
		tags.php		<-- Database: tags
		users.php		<-- Database: users

	pages/				<-- Content: pages
		about/index.txt
		food/index.txt

	tmp/				<-- Temp files

	uploads/			<-- Uploaded files
		profiles/		<-- Profiles images
		thumbnails/		<-- Thumbnails images
		photo1.jpg
		photo2.png
```

## bl-kernel
Dieses Verzeichnis beinhaltet den Logik-Kern von Bludit.

## bl-languages
In diesem Verzeichnis befinden sich alle Sprachdateien im JSON-Format und dem Zeichensatz UTF-8.

```
bl-languages/
	bg_BG.json
	cs_CZ.json
	de_CH.json
	en.json
	es.json
	...
```

## bl-plugins
In diesem Verzeichnis befinden sich alle Plugins. Neue Plugins müssen hier abgelegt werden damit sie erkannt werden.

```
bl-plugins/
	about/
	disqus/
	rss/
	sitemap/
	simplemde/
	...
```

## bl-themes
Dieses Verzeichnis beinhaltet alle Themes. Neue Themes müssen hier abgelegt werden, damit sie erkannt werden.

```
bl-themes/
	clean-blog/
	kernel-panic/
	...
```
