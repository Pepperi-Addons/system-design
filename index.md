# Pepperi System

## Contents
* [Introduction](#introduction)
* [Keywords](#keywords)
* [Layers](#layers)

## Introduction
This repo is meant to store the architecture design conclusions and reasoning of the Pepperi system.

### What is the system?
The system is a serverless microservice architecture as a service, for multi tenant applications.

The system is build for multiple micro-services and allowing creation of additional micro-services into the system. 

Each micro-service can have server-side logic, client-side UI and business logic.

The micro services have access to capabilities exposed by other micro services. 

The are basic builtin services that expose basic serverless functionality, like exposing API endpoints to microservice functions, and saving data in serverless data bases.

These basic services are currently implemented by AWS serverless technologies including Lambda, S3, DynamoDB, SNS, API Gateway and more.

Theoretically it should be possible to implement the system on any cloud or even local infrastructure, by replacing the basic micro-services by services that implement them on other infrastructures.

## Keywords

The following is a list of keywords that will be used in this documentation. Each keyword is a naming of a component in the Pepperi system. These keywords will later be used in the documentation when we deep dive into the system.

* [System](#system)
* [Addon](#addon)
* [Environment](#environment)
* [Tenant](#tenant)


### System
The entirety of the system defined here and it's architecture. Hopefully this is only a place holder and we will be able to name it.

### Addon
Each micro service in the system is an addon. 

The addon is created in the environment by the developer and can be installed on tenants in order to expose its functionality. 

There are mandatory addons, that implement the system basic functionality that the must be installed on the tenant for the system to work, and there are optional addons that expose additional optional functionality.

See [addon development](addon-development.md) for more information on how addons are developed.

### Environment
The environment is an instance of the system. Each environment is fully decoupled from other environments. 

An addon can be developed for a single environment or for multiple environments.

Separate environments can be deployed on different AWS regions, or even a different AWS account entirely.
We currently have 3 environments production, staging and eu.

### Tenant

### Server Side

### Client Side

### CPI Side

### Template

### 

## Layers
We will divide the design into folders, each folder containing design of a layer in the system.

The following is a overview of each layer including link to a deep dive to each layer.

### [Bootstrap](bootstrap/index.md)


### [Infra](infra/index.md)
The infra subset is a subset of addons that their purpose is to expose serverless capabilities to other addons.

#### [Addons](infra/addons.md)
Manages the addons available in the system.

#### [Relations]()

#### [ADAL]()

#### [CPI Node]()

#### [Async Addon API]()

#### [Addon API]()

### [Data Sources]()
These addons implement the data source interface defined by the ADAL allowing addons to store schema defined data.

#### [DocDB]()
store Key-Document data in a serverless NoSQL data base. (using AWS DynamoDB)
#### [IndexDB]()
store data in a indexable database optimized for search and aggregations (using AWS Elastic Search)
#### [GraphDB]()
store highly connected data in a graph data base. (using AWS Neptune)

### [Data Services](services/index.md)
The services is a subset of addons that their purpose is to supply services above the data addons.

#### [DIMX]()
#### [Data Queries]()

### [Legacy](legacy/index.md)

* [Core]()

### [User Defined](user-defined/index.md)
The user defined micro services are a subset of addons that their task is to expose the infra capabilities to system admins and configurators.

The system comes built in with the following services:
* [User Defined Collections](user-defined/collections.md)
* [User Defined Pages](user-defined/pages)
* [User Defined Scripts](user-defined/scripts.md)
* [User Defined Events](user-defined/events.md)
* [User Defined Blocks](user-defined/blocks.md)

### [Product](product/index.md)

* Survey
* 