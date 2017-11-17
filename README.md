# Salesforce Development Experience (SFDX) Cheatsheet

## What is SFDX?
[SFDX official site](https://developer.salesforce.com/platform/dx)

## Why do we need a cheatsheet?
Just like using `git`, there are too many commands to remember. Human brains should be occupied to do more interesting stuff.

## How to use this cheatsheet?
You should learn sfdx trailheads first, such as [Get Started with SFDX](https://trailhead.salesforce.com/en/trails/sfdx_get_started), [Set Up SFDX](https://trailhead.salesforce.com/en/modules/sfdx_app_dev/units/sfdx_app_dev_setup_dx)

Otherwise, you might be lost on the parameters used in the cheatsheet. in fact, some of the parameters defaults the scratch org to be used, so know what you are doing is eseential.

## Cheatsheet

|Action | command | Description|
| ------------- |:-------------:| -----:|
|Web Login to dev hub|sfdx force:auth:web:login -d -a DevHub| default and set an alias|
|Open the org in browser| sfdx force:org:open -u DevHub| without `-u` will go to default scratch org|