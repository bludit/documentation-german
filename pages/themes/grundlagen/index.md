# Grundlagen
<!-- Position: 1 -->
---
Bludit ist bei Themes sehr flexibel und erlaubt die Verwendung jedes Frameworks ([Bootstrap](http://getbootstrap.com/), [Kube](http://imperavi.com/kube/), [Pure.io](purecss.io), [Skel](https://github.com/n33/skel), [Less](http://lesscss.org/), etc), jeglichen Javascript code oder was immer du möchtest.

Alle Themes liegen im Verzeichnis 'bl-themes' und haben eine vordefinierte Struktur.

### Inhalt
1. [Theme Verzeichnisstruktur](#structure)
2. [Information über das Theme](#information)
3. [Name und Beschreibung](#name-description)

---

## <a id="structure"></a> Theme Verzeichnisstruktur
Dies ist die Verzeichnisstruktur mitsamt der benötigten Dateien für ein Theme.
```
/bl-themes/{THEME_NAME}/
	language/en.json
	metadata.json
	index.php
```

## <a id="information"></a> Information über das Theme
Die Information des Themes befindet sich in der JSON Datei `metadata.json`.
<pre><code data-language="JSON">{
	"author": "Bludit",
	"email": "",
	"website": "https://themes.bludit.com",
	"version": "2.0",
	"releaseDate": "2017-10-10",
	"license": "MIT",
	"compatible": "2.0",
	"notes": ""
}</code></pre>

## <i id="name-description"></i> Name und Beschreibung
Der Name und die Beschreibung des Themes befinden sich in der JSON Datei `languages/en.json`.
<pre><code data-language="JSON">{
	"theme-data":
	{
		"name": "Hello World",
		"description": "My new theme"
	}
}</code></pre>

<div class="note">
<div class="title">Beispiele</div>
Wir haben ein Gibhub-Repository mit Beispielen, welches du unter folgendem Link findest: <a href="https://github.com/bludit/examples">Bludit Theme Beispiele</a>.
</div>
