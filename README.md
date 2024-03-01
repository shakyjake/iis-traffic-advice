# IIS Traffic Advice Support

Provides support for the [Traffic Advice Spec](https://github.com/buettner/private-prefetch-proxy/blob/main/traffic-advice.md) in IIS

## How to use

Copy/paste the `.well-known` folder into the root directory of your website.

## Requirements

[URL Rewrite Module](https://www.iis.net/downloads/microsoft/url-rewrite)

### Potential issues/conflicts

If you have an existing `web.config` file inside the `.well-known` directory you will need to manually merge the rewrite rules from the `web.config` file in this repository. 

If you're using [win-acme](https://www.win-acme.com/) for LetsEncrypt certificates you may need to change the `Validation->CleanupFolders` setting in settings.json to `false` to prevent win-acme deleting the `.well-known` folder. You may also want to add the rewrite rules into win-acme's `Web_Config.xml` file - I'm not certain whether win-acme places its config file in the `acme-challenge` subdirectory or not 
