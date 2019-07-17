# Brute-Force-Schutz
<!-- position: 2 -->

## Was ist eine Brute-Force-Angriff?
Bei einem Brute-Force-Angriff handelt es sich um eine Methode, die versucht Passwörter oder Schlüssel durch automatisiertes, wahlloses Ausprobieren herauszufinden [Wikipedia](https://de.wikipedia.org/wiki/Brute-Force-Methode).

## Wie funktioniert der Schutz?
Bludit bietet einen Brute-Force-Schutz zur Abwehr dieser Art von Angriffen und ist standardmäßig aktiviert.

Bei jedem fehlgeschlagenen Login fügt Bludit die IP des Benutzers, dessen Authentifizierung fehlgeschlagen ist, einer Blacklist hinzu. Wenn der Benutzer sich mehrmals fehlerhaft anmeldet, blockiert Bludit die entsprechende IP für einen bestimmten Zeitraum und der Benutzer kann sich erst anmelden, wenn die Blockierung abgelaufen ist.

## Klasse und Objekt
Es existiert ein `Sicherheits Objekt` mit dem Namen `$security` der entsprechenden Klasse `/bl-kernel/security.class.php`. Schauen Sie sich die Variablen in der Klasse an.

<pre><code data-language="php">
private $dbFields = array(
    'minutesBlocked'=>5,
    'numberFailuresAllowed'=>10,
    'blackList'=>array()
);
</code></pre>

- `minutesBlocked`: Die Anzahl der Minuten, in der die IP blockiert wird.
- `numberFailuresAllowed`: Anzahl der fehlgeschlagenen Versuche, nach denen die Sperre ausgelöst wird.
- `blackList`: Die Liste der blockierten IP-Adressen.

<div class="note">
<div class="title">Hinweis</div>
Sie können diese Werte für Ihre eigenen Anforderungen anpassen.
</div>
