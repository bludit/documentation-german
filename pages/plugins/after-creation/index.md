# Hook nach Seitenerstellung
<!-- position: 5 -->

Nachdem eine Seite erstellt worden ist, ruft Bludit den Hook `afterPageCreate` auf. Dieser Hook wird auch für zur Veröffentlichung geplante Seiten verwendet

<div class="note">
Der Hook wurde mit der Version Bludit v3.13 erweitert.
</div>

## Beispiel: Zeichenkette zu einem Titel hinzufügen
Das folgende Beispiel fügt eine Zeichenkette vor dem Titel ein, nachdem eine Seite erstellt worden ist.

```php
<?php

class TitleAppender extends Plugin {

	public function afterPageCreate($key)
	{
		$page = new Page($key);
		$currentTitle = $page->title();
		$newTitle = 'Summer: '.$currentTitle;

		global $pages;
		$pages->edit(array(
				'key'=>$key,
				'title'=>$newTitle
		));
	}

}

?>
```

Das Plugin mit dem Beispiel kann hier heruntergeladen werden:
- https://github.com/bludit/examples/tree/master/plugins/title-appender
