# Addons Addon

## Description
Part of the Infra layer. Manages the addons available in the system.

## Responsibilities
This is addon is in charge of managing all the addons in the system on the current tenant.

This includes: 
### Addon types
Differentiating between different types of addons. For example, mandatory system addons can't be uninstalled by API or using the UI

### Version management

### Addon dependency

### Addon Manager UI
A client side page that allows system admins to install, uninstall, upgrade and downgrade addon as they please.

## Rest API's

The following is a list of official rest API this addon exposes:

### Install the latest phased version of an addon
##### **Method:** POST
##### **URL:** /addons/installed_addons/:addonUUID/install
##### **Body:** None
##### **Response:** 
Job response
```json
{
    "ToVersion": "the version that was installed"
}
```

### Uninstall
POST /addons/installed_addons/:addonUUID/uninstall