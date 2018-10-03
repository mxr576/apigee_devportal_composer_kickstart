Apigee Edge Devportal Kickstart
-------------------------------

**This is an unofficial Composer kickstart project to spin up a Drupal
8 site with [Apigee Edge](http://dgo.to/apigee_edge) module.**

## Installing

```sh
git clone https://github.com/mxr576/apigee_devportal_composer_kickstart.git
cd apigee_devportal_composer_kickstart
composer install --no-dev # Leave out --no-dev if you need dev dependencies.
```

### Known issues
* `composer install` throws some errors when it tries to install Drupal 8
patches on Drupal >= 8.6. This automatically gets fixed when alpha8
gets released from the Apigee Edge module.

## Installing Drupal with Config Installer

You can spin-up a new site by using the exported configuration from this
repository when you are installing your test environment. Select
"Use existing configuration" when you are installing the site. After the
install process has finished the Apigee Edge module will be enabled
with its default configuration. You just need to set your authentication
key at `admin/config/apigee-edge/settings`.

### Known issues
* Config Installer has a [bug](https://www.drupal.org/project/config_installer/issues/2998832)
since Drupal 8.6.0 so you must not select the "Configuration installer"
install profile when you are installing your site.
* After the install process has finished you will see an error message
because the admin user that you created meanwhile the install process
could not be created in Apigee Edge. After you have set up the
authentication to Apigee Edge you should run the Developer sync at
`/admin/config/apigee-edge/developer-settings/sync`.
