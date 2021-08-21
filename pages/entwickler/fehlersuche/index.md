# Fehlersuche
<!-- Position: 3 -->

Der Debug-Modus von Bludit kann in der Datei `init.php` im Verzeichnis `/bl-kernel/boot` aktiviert werden. Dazu muss Folgendes geändert werden (Zeile 11):

`define('DEBUG_MODE', TRUE);`

statt

`define('DEBUG_MODE', FALSE);`

Fehlermeldungen werden in der Datei `debug.txt` im Verzeichnis `/bl-content` gespeichert.
