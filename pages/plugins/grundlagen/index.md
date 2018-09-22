# Grundlagen
<!-- Position: 1 -->
---
Plugins befinden sich bei Bludit im Verzeichnis `bl-plugins` und haben eine vordefinierte Verzeichnis- und Dateistruktur.
Jedes Plugin ist in Bludit als Objekt mit Hooks (Methoden) dargstellt und ansprechbar.

### Inhalt
1. [Hello World](#hello-world)
2. [Plugin Struktur](#structure)
3. [Informationen über das Plugin](#information)
4. [Name und Beschreibung](#name-description)

---

## <i id="hello-world"></i> Hello World
Das "Hello World" Plugin für Bludit.
<pre><code data-language="php"><?php
	class pluginHello extends Plugin {
		public function siteSidebar() {
			echo 'Hello world';
		}
	}
?></code></pre>

## <i id="structure"></i> Plugin Struktur
Das ist die vorgegebene Verzeichnis- und Dateistruktur für ein Plugin.
```
/bl-plugins/{PLUGIN_NAME}/
	language/en.php
	metadata.json
	plugin.php
```

## <i id="information"></i> Informationen über das Plugin
Die Informationen über das Plugin befinden sich in der JSON-Datei `metadata.json`.
<pre><code data-language="JSON">{
	"author": "Bludit",
	"email": "",
	"website": "https://plugins.bludit.com",
	"version": "2.0",
	"releaseDate": "2017-10-10",
	"license": "MIT",
	"compatible": "2.0",
	"notes": ""
}</code></pre>

## <i id="name-description"></i> Name und Beschreibung
Der Name und die Beschreibung des Plugins befinden sich in der JSON-Datei `languages/en.json`.
<pre><code data-language="JSON">{
	"plugin-data":
	{
		"name": "Hello World",
		"description": "Print Hello World in the sidebar"
	}
}</code></pre>

<div class="note">
<div class="title">Beispiele</div>
Wir haben ein Gibhub-Repository mit Beispielen, welches du unter folgendem Link findest: <a href="https://github.com/bludit/examples">Bludit Beispiele</a>.
</div>
