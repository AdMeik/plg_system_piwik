# Yireo Matomo (Piwik) plugin for Joomla

## Disclaimer - Contributors welcome - Yireo Piwik is now called "PhpMatomo"
This project is no longer maintained by the team that initially created it.
The plugin is open-source and **looking for contributors helping to maintain it**. Any issues will be picked up by the community. Feel free to use the sources as basis for other projects as well.

## Introduction & Benfits compared to other Matomo (Piwik) plugins
This plugin allows you to integrate Matomo (previously called Piwik) in your Joomla site, while not using any client-side code (e.g. JavaScript). There are different benefits of this approach
* the Matomo (Piwik) integration will not slow down the client side loading
* additionally, it is fully compliant with EU cookie-regulations
* the plugin does not require a cookie banner to ask for user permission
* all tracking is done on the server side

## Benefits compared to other Tracking plugins (like Google Analytics)
* One main benefit is, that no hidden third party is involved. All data stays at a place under the control of the website maintainer.
* See also: FAQ article on the official website: https://matomo.org/faq/new-to-piwik/faq_15/

## Setup / Installation
* Install the plugin in the Extension Manager
* Enable the plugin in the Plugin Manager
* Configure your Matomo (Piwik) API in the plugin settings (see next chapter)

## Update from version 1.0.x to version 1.1.x
When the project went to Github the project structure needed some updates. To avoid conflicts in Joomla! with other piwik plugins, that might have the same name "piwik" and to follow the new name of Piwik called "Matomo" we took the opportunity to rename the plugin to "PhpMatomo".

### Known issues - Please read before updating 
As the new and the old plugin register the same functions, they cannot be activated at the same time. Otherwise Joomla! will not work anymore.
Therefore the old "System - Piwik" plugin has to be deactivated before activating the "System - PhpMatomo (Piwik)" plugin

### Update instructions
To update from Yireo-Piwik to PhpMatomo, please do the following:
* Install the plugin in the Extension Manager
* In the Plugin manager copy the plugin configuration from "System - Piwik" to "System - PhpMatomo (Piwik)"
* Uninstall or disable the plugin "System - Piwik" in the Plugin Manager
* Enable the plugin "System - PhpMatomo (Piwik)" in the Plugin Manager


## Usage
* Within the Plugin Manager, enable and configure this plugin
* Configure the (numeric) website ID: This is found under the Websites-tab in Matomo (Piwik) itself. See also: https://matomo.org/faq/general/faq_19212/
* Configure the API-token. This is found under the API-page in Matomo (Piwik). See also: https://matomo.org/faq/general/faq_114/

To use Matomo (Piwik) within your 404 pages as well, you need to modify the error.php file of your Joomla template. Add the following code:
```php
include_once JPATH_SITE . '/plugins/system/phpmatomo/phpmatomo.php';
if (class_exists('PlgSystemPhpMatomo')) {
	PlgSystemPhpMatomo::callPiwik();
}
```

## Further details about the plugin
* Tutorial how to configure the Yireo Piwik Plugin for Joomla! https://www.yireo.com/tutorials/joomla/joomla-extension-tutorials/1580-configuring-yireo-piwik-for-joomla


## FAQ: What is the difference between the normal Matomo (Piwik) widget and this plugin?
Usually Matomo (Piwik) is integrated through a JavaScript widget, which sets a cookie in the browser. This Matomo (Piwik) plugin works through the PHP API, and works without cookies. Note that the PHP API is not aware of JavaScript-measured statistics like screen resolution. If you want to know more about difference, please refer to the Matomo (Piwik) website: https://matomo.org/ .
