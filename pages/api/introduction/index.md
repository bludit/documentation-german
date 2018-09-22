# API Grundlagen
<!-- Position: 1 -->
<!-- Date: 2017-07-10 22:00:00 -->
<!-- DateModified: 2017-07-15 22:00:00 -->
---
Die Bludi API (Application Programming Interface) ist ein Plugin das die Integration von Bludit ermöglicht.
Mit diesem Plugin ist es möglich Daten aus der Datenbank mit einem HTTP Request abzufragen oder zu aktualisieren.

### Content
1. [Installation](#installation)
2. [URL](#url)
3. [Endpoints und Methoden](#endpoints)
4. [Methoden Parameter](#inputs)
4. [HTTP Response](#http-response)

---

## <a id="installation"></a> Installation
Das API-Plugin ist mit der Installation von Bludit automatisch dabei. Es muss nur über das Admin-Panel **Admin panel->Plugins->API->Aktivieren** aktiviert werden.

## <a id="url"></a> URL
Die URL der API lautet
```
{protocol}://{domain}/api/{endpoint}
````

Example:
```
https://example.com/api/pages
```

## <a id="endpoints"></a> Endpoints und Methoden

Endpoint		| Method 	| Beschreibung
------------------------|---------------|-----------------------------------------------|
/pages 			| GET 		| Gibt ein Array mit einer Liste aller Seiten zurück.		|
/pages/<key>		| GET		| Gibt eine Seite anhand des Schlüssels zurück	|
/pages			| POST		| Erstellt eine neue Seite				|

## <a id="inputs"></a> Methoden Parameter

Key		| Type 		| Beschreibung
----------------|---------------|-----------------------------------------------|
token 		| string 	| API token					|
limit		| integer	| Eine Zahl um die Anzahl der Seiten zu begrenzen  		|
authentication	| string	| Authentifizierungs User Token			|

## <a id="http-response"></a> HTTP Response
Das zurückgegebene Format ist JSON mit folgenden Feldern:

| Key 		| Type 		| Beschreibung 					|
----------------|---------------|-----------------------------------------------|
| message	| string	| Gibt eine kleine Message über das Ergebnis des Requests zurück.	|
| data 		| array		| Der Inhalt der Antwort dieses Endpoints |

Außerdem kann man über den HTTP-Code die verschiednen Antworten prüfen.
