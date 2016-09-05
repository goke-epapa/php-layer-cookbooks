# PHP Server Cookbooks
----------------------
Collection of useful cookbooks for configuring PHP Layers on Amazon Opsworks


## Cookbooks
- newrelic



## Sample Usage


### New Relic Sample Usage
OS: Ubuntu 14.10

Add the JSON below as custom JSON for the PHP Layer
```
{
    "newrelic": {
        "application_monitoring" : {
            "app_name" : "Test Application"
        },
        "license": "********************************************",
        "php_agent": {
            "php_recipe": "mod_php5_apache2::default",
            "execute_php5enmod": true,
            "config_file": "/etc/php5/mods-available/newrelic.ini",
            "config_file_to_be_deleted": "/etc/php5/apache2/conf.d/newrelic.ini"
        }
    }
}
```
Add newrelic::default and newrelic::php_agent as setup recipes on the PHP Layer
newrelic::default installs the New Relic agent that performs the server monitoring
newrelic::php-agent configures the agent to monitor the PHP application

For more information visit: https://blog.newrelic.com/2014/07/31/monitoring-aws-opsworks/



## Authors
- Adegoke Obasa
