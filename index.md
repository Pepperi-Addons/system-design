# Introduction
This repo is meant to store the architecture design conclusions and reasoning of the Pepperi system.

## The system
The system is a serverless microservice architecture as a service.

The system allows creating additional micro services.

Each microservice is full-stack application with three layers for server-side, client-side and cpi-side. 

Within the system there are builtin system addons, that the system has been implemented by them. (eg. ADAL, DocDB etc.)

Additionally there are builtin optional addons that can enable more capabilities (eg. DIMX, User Defined Collections).

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