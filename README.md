# Salesforce Development Experience (SFDX) Cheatsheet

## What is SFDX?
[SFDX official site](https://developer.salesforce.com/platform/dx)

## Why do we need a cheatsheet?
Just like using `git`, there are too many commands to remember. Human brains should be occupied to do more interesting stuff.

## How to use this cheatsheet?
You are gonna wanna learn sfdx trailheads first, such as [Get Started with SFDX](https://trailhead.salesforce.com/en/trails/sfdx_get_started), [Set Up SFDX](https://trailhead.salesforce.com/en/modules/sfdx_app_dev/units/sfdx_app_dev_setup_dx)

Otherwise you might be lost on the parameters used in the cheatsheet. In fact, some of the parameters defaults the scratch org to be used, so know what you are doing is eseential.

__Hint1.__ always use `-h` to get help if you are not sure what the command does, such as `sfdx force:source:status -h`

__Hint2.__ Create shell alias to save typings... it is a personal taste thing thus not covered here.

## Cheatsheet

|Action | command | Description|
| ------------- |:-------------:| -----:|
|Web Login to dev hub|sfdx force:auth:web:login -d -a DevHub| default and set an alias|
|Open the org in browser| sfdx force:org:open -u DevHub| without `-u` will open the default scratch org|
|Create a project locally | sfdx force:project:create -n MyProject| |
|Create a scratch org with alias tempTest|sfdx force:org:create -s -f config/project-scratch-def.json -a tempTest|`-s` sets it to default scratch org for this project|
|Delete a scratch org with alias tempTest|sfdx force:org:delete -u tempTest|`-u` accepts either username or scratch org alias"|
|Check changes between the scratch org and local project|sfdx force:source:status| Similar to `git status`|
|Pull changes from the scratch org| sfdx force:source:pull|Similar to `git pull`|
|Push changes to the scratch org| sfdx force:source:push|Similar to `git push`|
|Assign corresponding permission to the current logged in user|sfdx force:user:permset:assign -n myCustomPermSet||
|Export some sample data from the scratch org| sfdx force:data:tree:export -q "SELECT Name, Location__Latitude__s, Location__Longitude__s FROM Account WHERE Location__Latitude__s != NULL AND Location__Longitude__s != NULL" -d ./data| the `pull/push` in `sfdx` dooes not sync user regular data, this step should be done individually|
|Import sample data to the current scratch org|sfdx force:data:tree:import --sobjecttreefiles data/Account.json|You might want some sample data in your CI/CD pipelines|
|Create lightning App| sfdx force:lightning:app:create -n AccountLocatorApp -d force-app/main/default/aura/ ||
|Create lightning component| sfdx force:lightning:component:create -n myComponent -d force-app/main/default/aura ||
|Create lightning event| sfdx force:lightning:event:create -n myEvent -d force-app/main/default/aura||
|Install LTS testing framework | sfdx force:lightning:test:install | https://forcedotcom.github.io/LightningTestingService/ |
|Set a connect hub as default | sfdx force:config:set defaultdevhubusername=<username|alias>||
|Set an existing scratch org as default | sfdx force:config:set defaultausername=<username|alias>||
