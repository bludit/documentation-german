# URL des Administrations-Bereiches anpassen
<!-- position: 3 -->

Standardmäßig ist der Administrations-Bereich von Bludit über den Kontext `/admin/` erreichbar.

Die können Sie ändern, indem Sie die Datei `/bl-kernel/boot/variables.php` bearbeiten. Ändern Sie die Konstante `ADMIN_URI_FILTER` entsprechend Ihrer eigenen Anforderung.

<pre><code data-language="php">define('ADMIN_URI_FILTER', 'admin');</code></pre>
