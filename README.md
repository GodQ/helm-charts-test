## Usage

[Helm](https://helm.sh) must be installed to use the charts.  Please refer to
Helm's [documentation](https://helm.sh/docs) to get started.

Guide to add charts:
[https://helm.sh/docs/topics/chart_repository/#store-charts-in-your-chart-repository](https://helm.sh/docs/topics/chart_repository/#store-charts-in-your-chart-repository)


    $ helm package examples/alpine/
    $ mv alpine-0.1.0.tgz charts/
    $ helm repo index charts --url https://godq.github.io/helm-charts
    $ git add . && git commit -m "add chart" && git push


Once Helm has been set up correctly, add the repo as follows:

    helm repo add godq-charts https://godq.github.io/helm-charts

If you had already added this repo earlier, run `helm repo update` to retrieve
the latest versions of the packages.  You can then run `helm search repo
<alias>` to see the charts.

To install the <chart-name> chart:

    helm install my-<chart-name> <alias>/<chart-name>
