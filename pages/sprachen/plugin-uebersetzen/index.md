# Übersetzen eines Plugins
<!-- Position: 1 -->

Jedes Plugin besitzt ein Verzeichnis `languages` in welchem sich unterschiedliche Dateien für jede unterstützte Sprache befinden.

```
/bl-plugins/<PLUGIN_NAME>/languages/
	de_DE.json
	en.json
	es.json
	fr_FR.json
	...
```

<div class="note">
<div class="title">Dateikodierung</div>
Alle Dateien sind im <b>JSON</b> Format und dem Zeichensatz <b>UTF-8</b>.
</div>

---

Folgendes Beispiel zeigt die Sprachdatei für die Sprache Englisch `en.json`.
Jede Zeile ist ein Key-Value Paar mit dem Key auf der linken und dem Wert auf der rechten Seite.

<pre><code data-language="JSON">{
	"plugin-data":
	{
		"name": "Page list",
		"description": "Shows the list of pages in order."
	},

	"home": "Home",
	"show-home-link": "Show home link"
}</code></pre>

Wie man sehen kann gibt es ein Feld mit dem Namen `plugin-data`. Dieses hat den Namen und die Beschreibung des Plugins.
Die weiteren Felder sind die Übersetzungen für die Schlüssel `home` und `show-home-link`.

Folgendes Beispiel zeigt die Sprachdatei für die Sprache Spanisch `es.json`.

<pre><code data-language="JSON">{
	"plugin-data":
	{
		"name": "Listado de paginas",
		"description": "Muestra el listado de paginas en orden."
	},

    "home": "Inicio",
    "show-home-link": "Mostrar link de la pagina de incio"
}</code></pre>
