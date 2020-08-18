# infra

the goal here is to migrate the datafruits infrastructure to kubernetes

i plan to do this using [helmsman](https://github.com/Praqma/helmsman), which allows for desired-state based administration of kubernetes clusters with [helm](https://helm.sh) charts.

it's possible to use multiple configuration files instead of one big one, but it introduces some problems with having to duplicate shared settings and there's no inbuilt mechanism in TOML or YAML for referencing other files, so for now I'm going to keep everything in helmsman.yaml.

there are already charts built for postgres and traefik (for ingress), but we need to build out our own for everything else.

the charts dir contains the [templates](https://docs.bitnami.com/tutorials/create-your-first-helm-chart/#step-1-generate-your-first-chart) created when running `helm create <chart-name>`.

the values dir contains (empty) YAML files which will eventually be populated with the values we want to use to configure our deployments. [Read more](https://helm.sh/docs/chart_template_guide/values_files/)
