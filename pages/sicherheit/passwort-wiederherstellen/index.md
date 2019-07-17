# Passwort wiederherstellen
<!-- position: 4 -->

Sie können das Passwort für den Benutzer `admin` mit dem Skript `recovery.php` wiederherstellen.


<h2 id="so-stellen-sie-das-passwort-wieder-her">So stellen Sie das Passwort wieder her</h2>

1. Laden Sie folgende Datei herunter [recovery.php](https://raw.githubusercontent.com/bludit/password-recovery-tool/master/recovery.php)
2. Diese Datei `recovery.php` laden Sie in Ihre Bludit Installation, in den Wurzel-Ordner, herauf.
3. Öffnen Sie diese Datei in Ihrem Webbrowser, zum Beispiel: https://example.com/recovery.php, ändern Sie `example.com` zu Ihrer Domain.
4. Ein neues Passwort für den `admin` Benutzer wird generiert und im Browser angezeigt.
5. Melden Sie sich im Administrations-Bereich mit dem Benutzer `admin` und dem neuen generierten Passwort an.

Das Skript recovery.php wird versuchen, sich selbst zu löschen. Sollte dies jedoch nicht der Fall sein, empfehlen wir, die Datei recovery.php manuell zu löschen.

---

<h2 id="so-stellen-sie-das-passwort-ueber-die-befehlszeile-wieder-her">So stellen Sie das Passwort über die Befehlszeile wieder her</h2>

Sie können die PHP-Datei `recovery.php` über die Befehlszeile ausführen.

```
# Wechseln Sie in das Verzeichnis, in dem Sie Bludit installiert haben
cd /var/html/bludit

# Laden Sie die Datei herunter
curl -o recovery.php https://raw.githubusercontent.com/bludit/password-recovery-tool/master/recovery.php

# Führen Sie das Tool aus
php recovery.php
```

```
Bludit Password Recovery Tool

Username: admin
New password: 00bef4566011d2015df2786dbd094003

>> The file recovery.php was deleted automatically for security reasons. <<
```