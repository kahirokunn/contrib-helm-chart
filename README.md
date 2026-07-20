# Redash Community Kubernetes Helm Charts

The code is provided as-is with no warranties.

## Usage

[Helm](https://helm.sh) must be installed to use the charts.
Please refer to Helm's [documentation](https://helm.sh/docs/) to get started.

Once Helm is set up properly, add the repo as follows:

```console
helm repo add redash https://getredash.github.io/contrib-helm-chart
```

You can then run `helm search repo redash` to see the charts.

### Install from GHCR as an OCI chart

Use the OCI chart when you want to install a specific version directly from GHCR without adding a Helm repository.

| Who uses this | Chart URL | Example |
| --- | --- | --- |
| Cluster operator | `oci://ghcr.io/kahirokunn/charts/redash` | `helm upgrade --install my-release oci://ghcr.io/kahirokunn/charts/redash --version 4.1.0 -f my-values.yaml` |

The publish workflow reads the package version from `charts/redash/Chart.yaml` and does not overwrite a version that is already in GHCR.

| Maintainer action | Published version | Required condition |
| --- | --- | --- |
| Push a change under `charts/redash/` to `master` | The version in `Chart.yaml` | Increase `version` before publishing changed chart contents. |
| Push a `redash-<version>` tag | The version in `Chart.yaml` | The tag must match the chart name and version, such as `redash-4.1.0`. |
| Run **Actions > Publish Helm chart to GHCR > Run workflow** | The version at the selected Git ref | Use this to publish an existing version for the first time. |

<!-- Keep full URL links to repo files because this README syncs from master to gh-pages.  -->
Chart documentation is available in [redash directory](https://github.com/getredash/contrib-helm-chart/blob/master/charts/redash/README.md).

## Contributing

<!-- Keep full URL links to repo files because this README syncs from master to gh-pages.  -->
We'd love to have you contribute! Please refer to our [contribution guidelines](https://github.com/getredash/contrib-helm-chart/blob/master/CONTRIBUTING.md) for details.

## License

<!-- Keep full URL links to repo files because this README syncs from master to gh-pages.  -->
[Apache 2.0 License](https://github.com/getredash/contrib-helm-chart/blob/master/LICENSE).
