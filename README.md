# Changes 

[change image](charts/confluent-for-kubernetes-0.824.40.tgz)
[change image](charts/confluent-for-kubernetes-0.1193.1.tgz)

# Prepare

[Helm](https://helm.sh) must be installed to use the charts.  Please refer to
Helm's [documentation](https://helm.sh/docs) to get started.

# Update charts
[https://helm.sh/docs/topics/chart_repository/#store-charts-in-your-chart-repository](https://helm.sh/docs/topics/chart_repository/#store-charts-in-your-chart-repository)

## Pull new chart tgz
```
cd charts
helm repo add bitnami https://charts.bitnami.com/bitnami
helm repo update
helm search repo bitnami
helm pull bitnami/nginx --version 18.3.5  # download the helm chart tgz
```

## Build own chart tgz
```
helm package code/*
mv *.tgz charts
```

## Update helm chart repo
```
helm repo index --url https://godq.github.io/helm-charts-test .
git add . 
git commit -m "add chart" 
git push
```

# Usage
Once Helm has been set up correctly, add the repo as follows:
```
helm repo add godq-charts https://godq.github.io/helm-charts-test
helm search repo godq-charts -l --devel | grep confluent
```
If you had already added this repo earlier, run `helm repo update` to retrieve
the latest versions of the packages.  You can then run `helm search repo
<alias>` to see the charts.

To install the <chart-name> chart:
```
helm install my-<chart-name> <alias>/<chart-name>
```
