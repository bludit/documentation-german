# Title: Translate a theme
<!-- Position: 2 -->
---
Jedes Theme besitzt ein Verzeichnis `languages` in welchem sich unterschiedliche Dateien für jede unterstützte Sprache befinden.

```
/bl-themes/{THEME_NAME}/languages/
	de_DE.json
	en.json
	es.json
	fr_FR.json
	...
```

<div class="note">
<div class="title">File Encoding</div>
All dictionary files are <b>JSON</b> files and are encoding on <b>UTF-8</b>.
</div>

---

Folgendes Beispiel zeigt die Sprachdatei für die Sprache Englisch `en.json`. 
Jede Zeile ist ein Key-Value Paar mit dem Key auf der linken und dem Wert auf der rechten Seite.

<pre><code data-language="JSON">{
	"theme-data":
	{
		"name": "Pure",
		"description": "Simple and clean, based on the framework Pure.css."
	}
}</code></pre>

Wie man sehen kann gibt es ein Feld mit dem Namen `theme-data`. Dieses hat den Namen und die Beschreibung des Themes.

Folgendes Beispiel zeigt die Sprachdatei für die Sprache Spanisch `es.json`.

<pre><code data-language="JSON">{
	"theme-data":
	{
		"name": "Pure",
		"description": "Simple y minimalista, basado en el framework Pure.css."
	}
}</code></pre>
