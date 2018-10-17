<!--
  Licensed under the Apache License, Version 2.0 (the "License");
  you may not use this file except in compliance with the License.
  You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

  Unless required by applicable law or agreed to in writing, software
  distributed under the License is distributed on an "AS IS" BASIS,
  WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
  See the License for the specific language governing permissions and
  limitations under the License. See accompanying LICENSE file.
-->

# Barbarian big data system

Barbarian is the world's best cloud-first, cloud-agnostic in-memory big data system founded on Apache Hadoop for enterprise-ready parallel distributed data processing at scale.

Read more at:
[https://barbarians.io/](https://barbarians.io)

Docs at:
[http://docs.barbarians.io/](http://docs.barbarians.io)

### About Barbarian

The Barbarian Data System is an in-memory, parallel, distributed (MPP) data warehousing engine designed to be deployed to Kubernetes clusters, offering Apache Hive for powerful and flexible SQL based analytics. Barbarian includes an integrated in-memory filesystem and can run in three modes of operation.
* As an in-memory, standalone data warehousing system
* As a data warehousing system backed by an external storage system like Amazon S3
* In a hybrid mode, where primary storage is the external storage system, with common paths mounted to the in-memory filesystem

Barbarian includes compelling features including Apache Hive LLAP and Tez, with transactional tables enabled by default. 

Barbarian's integrated Ignite in-memory distributed parallel filesystem is resilient to node failure with replication enabled by default.

Barbarian has no single points of failure.

Barbarian is offered with the [Apache v2.0](https://www.apache.org/licenses/LICENSE-2.0) software license.

### Installing Barbarian

Barbarian can be deployed to your Kubernetes cluster with just two commands:

```helm repo add barbarians http://charts.barbarians.io/barbarian```
```helm install barbarians/barbarian```

## Apache Tez

This repo contains the Barbarian Data System fork of the **Apache Tez** project.

## Releases

| Release | Notes |
| -- | -- |
| 0.1 | Prelease 1 |
| 0.2 | Barbarian Data System r2 |

Apache Tez
==========

Apache Tez is a generic data-processing pipeline engine envisioned as a low-level engine for higher abstractions
such as Apache Hadoop Map-Reduce, Apache Pig, Apache Hive etc.

At its heart, tez is very simple and has just two components:

*   The data-processing pipeline engine where-in one can plug-in input, processing and output implementations to 
    perform arbitrary data-processing. Every 'task' in tez has the following:
   -   Input to consume key/value pairs from.
   -   Processor to process them.
   -   Output to collect the processed key/value pairs.


*  A master for the data-processing application, where-by one can put together arbitrary data-processing 'tasks' 
   described above into a task-DAG to process data as desired. 
   The generic master is implemented as a Apache Hadoop YARN ApplicationMaster.
