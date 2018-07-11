# Custom_component for [ha-dockermon](https://github.com/philhawthorne/ha-dockermon)

A custom platform which allows you to interact with [ha-dockermon.](https://github.com/philhawthorne/ha-dockermon)
  
To get started put `/custom_components/switch/hadockermon.py` here:  
`<config directory>/custom_components/switch/hadockermon.py`  
  
**Example configuration.yaml:**

```yaml
switch:
  platform: hadockermon
  host: 192.168.1.50
  port: 8126
  stats: true
  prefix: hadockermon
  exclude:
    - 'NGINX'
    - 'ha-dockermon'
```

**Configuration variables:**  
  
key | description  
:--- | :---  
**platform (Required)** | The platform name.  
**host (Required)** | The IP address of your Docker host.  
**port (Optional)** | The port that the service is exposed on.  
**stats (Optional)** | Show memory and network usage of the containers, this does _not_ work on every docker host.  
**prefix (Optional)** | A string that will prefix the entity name, for easy sort and grouping.  
**exclude (Optional)** | A list of Docker containers you want to exclude.  
  
## Sample overview

![Sample overview](overview.png)
  
[Home-Assistant demo site.](https://ha-test-hadockermon.halfdecent.io/)
  
To start using this make sure you have [ha-dockermon](https://github.com/philhawthorne/ha-dockermon) running.  
  
***
Due to how `custom_componentes` are loaded, it is normal to see a `ModuleNotFoundError` error on first boot after adding this, to resolve it, restart Home-Assistant.