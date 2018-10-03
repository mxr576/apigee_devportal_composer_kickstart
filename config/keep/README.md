For environment specific configurations (config objects) that should not
be synced but must not be deleted from the current environment when a
full config import happens.

Examples
* Contact/Webform forms
* Keys
* Simplenews newsletters,
* etc.

**The content of this folder should not be in version control.**

Run the following command before every config import:
```sh
$ drush csex keep -yv
$ drush cim -yv
```

This split should be always active, if you need to disable it add this
to the settings.php or settings.local.php:
 
```php
$config['config_split.config_split.status']['status'] = FALSE;
```
