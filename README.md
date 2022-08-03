[![FINOS - Incubating](https://cdn.jsdelivr.net/gh/finos/contrib-toolbox@master/images/badge-incubating.svg)](https://finosfoundation.atlassian.net/wiki/display/FINOS/Incubating)

[![Get it from the Charmhub](https://charmhub.io/finos-waltz-bundle/badge.svg)](https://charmhub.io/finos-waltz-bundle)

[![Create FINOS Waltz release branch](https://github.com/finos/waltz-juju-bundle/actions/workflows/create_release.yaml/badge.svg)](https://github.com/finos/waltz-juju-bundle/actions/workflows/create_release.yaml)
[![Publish FINOS Waltz Images](https://github.com/finos/waltz-juju-bundle/actions/workflows/publish_images.yaml/badge.svg)](https://github.com/finos/waltz-juju-bundle/actions/workflows/publish_images.yaml)
[![Refresh EC2 FINOS Waltz deployment](https://github.com/finos/waltz-integration-juju/actions/workflows/refresh_deployment.yaml/badge.svg)](https://github.com/finos/waltz-integration-juju/actions/workflows/refresh_deployment.yaml)
[![Publish Charm](https://github.com/finos/waltz-integration-juju/actions/workflows/publish.yaml/badge.svg)](https://github.com/finos/waltz-integration-juju/actions/workflows/publish.yaml)
[![Renew the CA-verified Certificate](https://github.com/finos/waltz-integration-juju/actions/workflows/renew_certificate.yaml/badge.svg)](https://github.com/finos/waltz-integration-juju/actions/workflows/renew_certificate.yaml)

# Charmed Waltz
A Charmed bundle containing everything needed to deploy and operate Waltz on a Kubernetes cluster: 

* [**finos-waltz-k8s**](https://github.com/finos/waltz-integration-juju), which contains the Waltz server.
* [**postgresql-k8s**](https://charmhub.io/postgresql-k8s), responsible for creating a PostgreSQL database on demand for the related ``finos-waltz-k8s`` charm.
* [**nginx-ingress-integrator**](https://charmhub.io/nginx-ingress-integrator), which manages the ingress traffic for the related ``finos-waltz-k8s`` charm, allowing users to connect to Waltz through a friendly, configurable ``service-hostname`` instead of an ephemeral IP.

In addition to the charms above, [Waltz public bundle](https://github.com/finos/waltz-juju-bundle/blob/public/bundle.yaml) also contains the [**postgresql-data-k8s**](https://charmhub.io/postgresql-data-k8s) charm related to the ``postgresql-k8s`` charm, which will inject a public Waltz database sample into the Waltz database for demo purposes.

>💡If you are evaluating Waltz, you can follow [this guide](/docs/guides/LocalDeployment.md) for a quick 10-minutes Waltz deployment. You will also learn how to provision a K8s cluster on your laptop using MicroK8s. You don't need to have any previous Kubernetes knowledge!

## Waltz 
From the projects [repository](https://github.com/finos/waltz):
> In a nutshell Waltz allows you to visualize and define your organisation's technology landscape. Think of it like a structured Wiki for your architecture.

## Juju and Charmed Operators

The [Juju Charmed Operator Lifecycle Manager (OLM)](https://juju.is/docs/olm) is a hybrid-cloud application management and orchestration system for installation and day 2 operations. It helps deploy, configure, scale, integrate, maintain, and manage Kubernetes native, container-native and VM-native applications—and the relations between them.

A charmed operator (also known, more simply, as a “charm”) encapsulates a single application and all the code and know-how it takes to operate it, such as how to combine and work with other related applications or how to upgrade it. Charms are programmed to understand a single application, its operations, and its potential to communicate or integrate with other applications. A charm defines and enables the channels by which applications connect.

### Cloud vendor agnostic

The instructions cover the deployment of FINOS Waltz charmed operators on a host PC. However these charms can be deployed on any Kubernetes cluster.

### Multi-hybrid cloud

The applications necessary to run Waltz were deployed as a _bundle_ in the same cloud. [Juju](https://juju.is/) allows, however, for you to deploy each application on a different cloud and then integrate the stack across your estate.

### Offline installation

We assume your host had a functioning Internet connection. However it is also possible to [deploy charmed operators offline](https://juju.is/docs/olm/working-offline).

## Installation
To get started, you can checkout the [local run documention](/docs/guides/LocalDeployment.md), which will walk you through and explain all the different deployment steps to run a local Waltz instance, and will point you to docs for alternative deployments, such as clouds, barebone installations and other.

## FINOS Waltz Resource Updates

This repository is set up to be able to release a new ``finos-waltz-k8s`` charm revision with the latest Waltz docker image. For more information, see [here](docs/development/CharmPublishing.md).

## Contributing

1. Fork it (<https://github.com/finos/waltz-juju-bundle/fork>)
2. Create your feature branch (`git checkout -b feature/fooBar`)
3. Read our [contribution guidelines](.github/CONTRIBUTING.md) and [Community Code of Conduct](https://www.finos.org/code-of-conduct)
4. Commit your changes (`git commit -am 'Add some fooBar'`)
5. Push to the branch (`git push origin feature/fooBar`)
6. Create a new Pull Request

_NOTE:_ Commits and pull requests to FINOS repositories will only be accepted from those contributors with an active, executed Individual Contributor License Agreement (ICLA) with FINOS OR who are covered under an existing and active Corporate Contribution License Agreement (CCLA) executed with FINOS. Commits from individuals not covered under an ICLA or CCLA will be flagged and blocked by the FINOS Clabot tool (or [EasyCLA](https://github.com/finos/community/blob/master/governance/Software-Projects/EasyCLA.md)). Please note that some CCLAs require individuals/employees to be explicitly named on the CCLA.

*Need an ICLA? Unsure if you are covered under an existing CCLA? Email [help@finos.org](mailto:help@finos.org)*

## License

Copyright 2022 Canonical

Distributed under the [Apache License, Version 2.0](http://www.apache.org/licenses/LICENSE-2.0).

SPDX-License-Identifier: [Apache-2.0](https://spdx.org/licenses/Apache-2.0)
