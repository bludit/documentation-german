# Site Object
<!-- Position: 2 -->


Das Objekt `$Site` beinhaltet alle Informationen über die Datenbank `/bl-content/databases/site.php`

## Methoden und Beispiele

### URL Filter
Die Rückgabewerte sind Standardwerte und können vom User geändert werden.

<pre><code data-language="php"># Get the admin filter
$Site->uriFilters('admin'); # returns /admin/

#Get the post filter
$Site->uriFilters('post'); # returns /post/

#Get the page filter
$Site->uriFilters('page'); # returns /

#Get the tag filter
$Site->uriFilters('tag'); # returns /tag/

#Get the blog filter
$Site->uriFilters('blog'); # returns /blog/
</code></pre>

### Seitentitel
<pre><code data-language="php">echo $Site->title();</code></pre>

### Seiten-Slogan
<pre><code data-language="php">echo $Site->slogan();</code></pre>

### Seitenbeschreibung
<pre><code data-language="php">echo $Site->description();</code></pre>

### Fußzeilentext
<pre><code data-language="php">echo $Site->footer();</code></pre>

### Aktuelles Theme
<pre><code data-language="php">$theme = $Site->theme();</code></pre>

### Aktuelles Theme für den Admin-Bereich
<pre><code data-language="php">$theme = $Site->adminTheme();</code></pre>

### Eingestellte Zeitzone
<pre><code data-language="php">echo $Site->timezone();</code></pre>

### Eingestellte Sprache
<pre><code data-language="php">echo $Site->language();</code></pre>

### Eingestellte Locale
<pre><code data-language="php">echo $Site->locale();</code></pre>

### Eingestellte Haupt-Seite
<pre><code data-language="php">echo $Site->homepage();</code></pre>

### Anzahl der Seiten auf einer Seite
<pre><code data-language="php">echo $Site->postsPerPage();</code></pre>

### Aktuelle Version von Bludit
<pre><code data-language="php">echo $Site->currentBuild();</code></pre>
