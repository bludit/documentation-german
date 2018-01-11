# Title: Inhalte lesen
<!-- Position: 2 -->
<!-- Date: 2017-08-27 13:00:00 -->
---
Die Bludit API unterstützt eine Funktion um eine bestimmte Seite oder eine Liste aller Seiten abzurufen.

Standardmäßig benötigt die API den `API token`.

### Content
1. [Anfrage einer Liste aller Seiten](#request-a-list-of-pages)
2. [Anfrage einer bestimmten Seite](#request-a-particular-pages)

---

## <a id="request-a-list-of-pages"></a> Anfrage einer Liste aller Seiten

### Request
- Endpoint: `/api/pages`
- Method: `GET`
- Parameters: `token`

### Response
- HTTP Code: `200`
- Content-Type: `application/json`
- Content

```
{
        "status": "0",
        "message": "List of pages, amount of items: 15",
        "data": [
		{
                        "key": "the-dog",
                        "title": "The Dog",
                        "content": "Content of the page",
                        "description": "Description of the page",
                        "date": "2017-08-24 22:00:00",
                        "permalink": "http:\/\/example.com\/the-dog"
                },
                {
                        ....
                }
        ]
}
```

### cURL Befehl Beispiel
Hier ist ein Beispiel der Abfrage mit dem Kommandozeilen-Tool cURL:
```
$ curl -vvv -X GET -G "https://example.com/api/pages" -d "token=80a09ba055b73f68e3c9e7c9ea12b432"

> GET /api/pages?token=80a09ba055b73f68e3c9e7c9ea12b432 HTTP/1.1
> Host: example.com
> User-Agent: curl/7.54.0
> Accept: */*

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
        "message": "List of pages, amount of items: 15",
        "data": [
		{
                        "key": "the-dog",
                        "title": "The Dog",
                        "content": "Content of the page",
                        "description": "Description of the page",
                        "date": "2017-08-24 22:00:00",
                        "permalink": "http:\/\/example.com\/the-dog"
                },
                {
                        ....
                }
        ]
}
```

### AJAX mit jQuery
Beispiel eines AJAX-Requests mit der Bibliothek [jQuery](https://api.jquery.com/jQuery.ajax/).
```
$.ajax({
	url: "https://example.com/api/pages",
	method: "GET",
	data: "token=80a09ba055b73f68e3c9e7c9ea12b432",
	dataType: 'json',
	success: function(json) {
		console.log(json);
	}
});
```

Ein vollständiges Beispiel gibt es unter [Bludit Examples](https://github.com/bludit/examples/tree/master/api/ajax-request-list-of-pages).

---

## <a id="request-a-particular-pages"></a> Anfrage einer bestimmten Seite

### Request
- Endpoint: `/api/pages/<key>`
- Method: `GET`
- Parameters: `token`

### Response
- HTTP Code: `200`
- Content-Type: `application/json`
- Content

```
{
	"status": "0",
	"message": "List of pages, amount of items: 15",
	"data": {
		"key": "the-dog",
		"title": "The Dog",
		"content": "Content of the page",
		"description": "Description of the page",
		"date": "2017-08-24 22:00:00",
		"permalink": "http:\/\/example.com\/the-dog"
	}
}
```

### cURL Befehl Beispiel
Hier ist ein Beispiel der Abfrage mit dem Kommandozeilen-Tool cURL:
```
$ curl -vvv -X GET -G "https://example.com/api/pages/the-dog" -d "token=80a09ba055b73f68e3c9e7c9ea12b432"

> GET /api/pages/the-dog?token=80a09ba055b73f68e3c9e7c9ea12b432 HTTP/1.1
> Host: example.com
> User-Agent: curl/7.54.0
> Accept: */*

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
	"message": "List of pages, amount of items: 15",
	"data": {
		"key": "the-dog",
		"title": "The Dog",
		"content": "Content of the page",
		"description": "Description of the page",
		"date": "2017-08-24 22:00:00",
		"permalink": "http:\/\/example.com\/the-dog"
	}
}
```

### AJAX mit jQuery
Beispiel eines AJAX-Requests mit der Bibliothek [jQuery](https://api.jquery.com/jQuery.ajax/).
```
$.ajax({
        url: "https://example.com/api/pages/the-dog",
        method: "GET",
        data: "token=80a09ba055b73f68e3c9e7c9ea12b432",
        dataType: 'json',
        success: function(json) {
                console.log(json);
        }
});
```

Ein vollständiges Beispiel gibt es unter [Bludit Examples](https://github.com/bludit/examples/tree/master/api/ajax-request-a-particular-page).
