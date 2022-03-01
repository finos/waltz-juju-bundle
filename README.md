# <img src="https://user-images.githubusercontent.com/5586487/152134303-f3a34f04-d459-4581-87df-cbd0d8e6a29f.png" alt="FINOS Waltz" width="150"/>&nbsp; Bundle

In a nutshell, [Waltz](https://github.com/finos/waltz) allows you to visualize and define your organisation's technology landscape. Think of it like a structured Wiki for your architecture.

This repository contains a [Juju](https://juju.is) bundle for FINOS Waltz, which will deploy and relate the following charms:

* [finos-waltz-k8s](https://github.com/pedroleaoc/waltz-integration-juju): contains the Waltz server.
* [postgresql-k8s](https://charmhub.io/postgresql-k8s): responsible for creating a PostgreSQL database on demand for the related ``finos-waltz-k8s`` charm.
* [nginx-ingress-integrator](https://charmhub.io/nginx-ingress-integrator): manages the ingress traffic for the related ``finos-waltz-k8s`` charm, allowing users to connect to Waltz through a friendly, configurable ``service-hostname`` instead of an ephemeral IP. Can be further configured with other config options, such as ``tls-secret-name``, which will enable Ingress-terminated TLS for the Waltz service using the certificate stored in the given secret. For more information on the available configuration options, see [here](https://charmhub.io/nginx-ingress-integrator/configure).

For more information on Waltz and how to deploy it using Juju, see the [FINOS Waltz Charm's README](https://github.com/pedroleaoc/waltz-integration-juju/blob/main/README.md) and [local deployment guide](https://github.com/pedroleaoc/waltz-integration-juju/blob/main/docs/LocalDeployment.md).
