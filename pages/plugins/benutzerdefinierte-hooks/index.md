# Benutzerdefinierte Hooks für Plugins
<!-- position: 4 -->

Bludit unterstützt benutzerdefinierte Hooks für Plugins. Es können eigene Hooks erstellt werden, die überall aufgerufen werden können.

<div class="note">
Benutzerdefinierte Hooks wurden mit Bludit v3.13 eingeführt.
</div>

## Beispiel
Das folgende Beispiel definiert die zwei benutzerdefinierten Hooks `select` and `insert`.

Damit die Hooks verwendet werden können müssen sie (object methods) zum Array `$this->customHooks` der Methode `init()` hinzugefügt werden.

```php
<?php

class MyHooks extends Plugin {

	public function init()
	{
        $this->customHooks = array(
            'select',
            'insert'
        );
	}

	public function select()
	{
		echo 'Custom hook select';
	}

	public function insert()
	{
		echo 'Custom hook insert';
	}
}

?>
```

Nachdem das Plugin aktiviert worden ist, kann der benutzerdefinierte Hook mit dem Helper `Theme::plugins` im Theme aufgerufen werden.

```php
<?php
	...
	Theme::plugins('select');
	...
	Theme::plugins('insert');
?>
```
