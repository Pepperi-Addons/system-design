# Addons Addon

## Contents
* [Description](#description)
* [Responsibilities](#responsibilities)
* [Rest APIs](#rest-apis)
* [UI](#ui)
* [Implementation](#implementation)

## Description
Part of the Infra layer. Manages the addons available in the system.

## Responsibilities
This is addon is in charge of managing all the addons in the system on the current tenant.

This includes: 
### Addon types
Differentiating between different types of addons. For example, mandatory system addons can't be uninstalled by API or using the UI

### Version management
Saving and handling the currently installed addons.

### Addon dependency
Allowing addons version to define dependencies between them and other addons versions and enforcing these dependencies when installing, upgrading and downgrading addons.

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

## UI
### Addon Manager
This addon exposes a UI module to allow system admins to install, uninstall, upgrade and downgrade addon as they please.

## Implementation
### Schemas
The addon using the following data schemas
#### addons
##### Purpose 
Stores all of the existing addons in the environment
##### **Type:** Muti Tenant Data??

#### addons_versions
##### Purpose 
Stores all of the versions of all of the addons
##### **Type:** Muti Tenant Data??

#### installed_addons
##### Purpose 
Stores the all the addons that are installed on the current tenant. Additionally store the version of the addon that is currently installed.
##### **Type:** ??


