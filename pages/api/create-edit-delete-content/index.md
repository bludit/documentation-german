# Inhalte erstellen/bearbeiten/löschen
<!-- Position: 3 -->
<!-- Date: 2017-10-18 22:00:00 -->

Die Bludit API unterstützt eine Funktion um eine bestimmte Seite oder eine Liste aller Seiten abzurufen.

Standardmäßig benötigt die API den `API token`. Um Inhalte zu schreiben benötigt man einen User mit der Rolle **ADMINISTRATOR** und dessen `Authorization Token`. Diesen bekommt man im Admin-Bereich unter **Verwalten->Benutzer->{Username}->Edit User->Authentication Token->Token**.

By default the API requiere the `API token`, and to write content you need an user with the **ADMINISTRATOR** role and his `Authorization Token`; You can get the `Authorization Token` on **Manage->Users->{Username}->Benutzer bearbeiten->Authentifizierungs-Token->Token**.

### Inhalt
1. [Erstellen einer neuen Seite](#create-a-new-page)
2. [Eine Seite bearbeiten](#edit-a-page)
3. [Eine Seite löschen](#delete-a-page)

---

## <a id="create-a-new-page"></a> Erstellen einer neuen Seite

### Request
- Endpoint: `/api/pages`
- Method: `POST`
- Content-Type: `application/json`
- Content

```
{
	"token": "24a8857ed78a8c89a91c99afd503afa7",
	"authentication": "193569a9d341624e967486efb3d36d75",
	"title": "My dog",
	"content": "Content of the page here, support Markdown code and HTML code."
}
```

### Response
- HTTP Code: `200`
- Content-Type: `application/json`
- Content

```
{
	"status": "0",
	"message": "Page created.",
	"data": {
		"key": "my-dog"
	}
}
```

### cURL Befehl Beispiel
Hier ist ein Beispiel der Abfrage mit dem Kommandozeilen-Tool cURL. Die Datei `data.json` beinhaltet die Informationen um eine Seite erstellen zu können.

File `data.json`
```
{
	"token": "24a8857ed78a8c89a91c99afd503afa7",
	"authentication": "193569a9d341624e967486efb3d36d75",
	"title": "My dog",
	"content": "Content of the page here, support Markdown code and HTML code."
}
```

```
$ curl -vvv -X POST -H "Content-Type: application/json" -d @data.json "https://example.com/api/pages"

> POST /api/pages HTTP/1.1
> Host: example.com
> User-Agent: curl/7.54.0
> Accept: */*
> Content-Type: application/json

< HTTP/1.1 200 OK
< Date: Sun, 27 Aug 2017 18:58:25 GMT
< Set-Cookie: Bludit-KEY=3de3df692e83b9cbbf5d31de385110bb; path=/; HttpOnly
< Expires: Thu, 19 Nov 1981 08:52:00 GMT
< Cache-Control: no-store, no-cache, must-revalidate, post-check=0, pre-check=0
< Pragma: no-cache
< Access-Control-Allow-Origin: *
< Content-Length: 50731
< Content-Type: application/json

{
	"status": "0",
	"message": "Page created.",
	"data": {
		"key": "my-dog"
	}
}
```

---

## <a id="edit-a-page"></a> Eine Seite bearbeiten

### Request
- Endpoint: `/api/pages/<key>`
- Method: `PUT`
- Content-Type: `application/json`
- Content

```
{
	"token": "24a8857ed78a8c89a91c99afd503afa7",
	"authentication": "193569a9d341624e967486efb3d36d75",
	"title": "My edited dog",
	"content": "Content of the page here, support Markdown code and HTML code."
}
```

### Response
- HTTP Code: `200`
- Content-Type: `application/json`
- Content

```
{
	"status": "0",
	"message": "Page edited.",
	"data": {
		"key": "my-dog"
	}
}
```

---

## <a id="delete-a-page"></a> Eine Seite löschen

### Request
- Endpoint: `/api/pages/<key>`
- Method: `DELETE`
- Content-Type: `application/json`
- Content

```
{
	"token": "24a8857ed78a8c89a91c99afd503afa7",
	"authentication": "193569a9d341624e967486efb3d36d75"
}
```

### Response
- HTTP Code: `200`
- Content-Type: `application/json`
- Content

```
{
	"status": "0",
	"message": "Page deleted."
}
```
