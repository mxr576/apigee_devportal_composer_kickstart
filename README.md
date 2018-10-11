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

## Installing Drupal with Config Installer

You can spin-up a new site by using the exported configuration from this repository when you are installing your test environment.

1. [Change the storage location of the sync directory](https://www.drupal.org/docs/8/configuration-management/changing-the-storage-location-of-the-sync-directory) to "../config/sync".
2. Select "Use existing configuration" when you are installing the site.
3. After the install process has finished the Apigee Edge module will be enabled with its default configuration. You just need to set your authentication key at `admin/config/apigee-edge/settings`.

### Known issues
* Config Installer has a [bug](https://www.drupal.org/project/config_installer/issues/2998832) since Drupal 8.6.0 so you must not select the "Configuration installer" install profile when you are installing your site.
* After you have set up the authentication to Apigee Edge you should run the Developer sync at `/admin/config/apigee-edge/developer-settings/sync` to synchronise the uid1 user (created meanwhile the install process) with Apigee Edge.
