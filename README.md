[![FINOS - Incubating](https://cdn.jsdelivr.net/gh/finos/contrib-toolbox@master/images/badge-incubating.svg)](https://finosfoundation.atlassian.net/wiki/display/FINOS/Incubating)
# <img src="https://user-images.githubusercontent.com/5586487/152134303-f3a34f04-d459-4581-87df-cbd0d8e6a29f.png" alt="FINOS Waltz" width="150"/>&nbsp; Bundle

In a nutshell, [Waltz](https://github.com/finos/waltz) allows you to visualize and define your organisation's technology landscape. Think of it like a structured Wiki for your architecture.

This repository contains a [Juju](https://juju.is) bundle for FINOS Waltz, which will deploy and relate the following charms:

* [finos-waltz-k8s](https://github.com/pedroleaoc/waltz-integration-juju): contains the Waltz server.
* [postgresql-k8s](https://charmhub.io/postgresql-k8s): responsible for creating a PostgreSQL database on demand for the related ``finos-waltz-k8s`` charm.
* [nginx-ingress-integrator](https://charmhub.io/nginx-ingress-integrator): manages the ingress traffic for the related ``finos-waltz-k8s`` charm, allowing users to connect to Waltz through a friendly, configurable ``service-hostname`` instead of an ephemeral IP. Can be further configured with other config options, such as ``tls-secret-name``, which will enable Ingress-terminated TLS for the Waltz service using the certificate stored in the given secret. For more information on the available configuration options, see [here](https://charmhub.io/nginx-ingress-integrator/configure).

For more information on Waltz and how to deploy it using Juju, see the [FINOS Waltz Charm's README](https://github.com/pedroleaoc/waltz-integration-juju/blob/main/README.md) and [local deployment guide](https://github.com/pedroleaoc/waltz-integration-juju/blob/main/docs/LocalDeployment.md).

## FINOS Waltz Resource Updates

This repository is set up to be able to release a new ``finos-waltz-k8s`` charm revision with the latest Waltz docker image. For more information, see [here](docs/CharmPublishing.md).

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
