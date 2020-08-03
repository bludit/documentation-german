# Verwandte Inhalte
<!-- position: 10 -->

Mit dem Code der Beispiele können verwandte Inhalte (Seiten oder Beiträge) ausgegeben werden.

## Beispiel: Verwandte Inhalte
Beim folgenden Beispiel werden die Titel verwandter Inhalte ausgegeben.

```php
<?php
$relatedPages = $page->related();
foreach ($relatedPages as $pageKey) {
	$related = new Page($pageKey);
	echo $related->title();
}
?>
```

## Beispiel: Sortierung verwandter Inhalte
Mit `->related()` wird eine unsortierte Liste verwandter Inhalte ausgegeben. Im folgenden Beispiel werden die Inhalte nach Datum sortiert.

```php
<?php
// Insert in array by unixtimestamp
$sort = array();
$relatedPages = $page->related();
foreach ($relatedPages as $pageKey) {
	$tmp = new Page($pageKey);
	$sort[$tmp->date['U']] = new Page($pageKey);
}

// Sort array by key which is unixtimestamp
krsort($sort);

// Print related page title and date
foreach ($sort as $related) {
	echo $related->title();
	echo $related->date();
}
?>
```
