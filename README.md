# Flyimg Helm Chart

## Usage

[Helm](https://helm.sh) must be installed to use the charts.  Please refer to
Helm's [documentation](https://helm.sh/docs) to get started.

Once Helm has been set up correctly, add the repo as follows:

```
    helm repo add flyimg https://charts.flyimg.io
```
If you had already added this repo earlier, run `helm repo update` to retrieve
the latest versions of the packages.  You can then run `helm search repo
flyimg` to see the charts.

To install the flyimg chart:

```
    helm install my-flyimg flyimg/flyimg
```

### Customizing Installation

You can customize your Flyimg installation by providing a custom values.yaml file. For example:

```
    helm install <release_name> flyimg/flyimg -f values.yaml
```

Alternatively, you can pass in parameters directly via the command line:

```
    helm install <release_name> flyimg/flyimg \
        --set key1=value1,key2=value2
```

To override the default configuration for Flyimg, you can do that by adding the needed changes in the `parameters:` section in your values.yaml file as the following example:

```yaml
parameters:
    storage_system: local
    aws_s3:
        access_id: 'xxxxxxx'
        secret_key: 'xxxxxx'
        region: 'eu-central-1'
        bucket_name: 'xxxxx'
    ....
```

## Upgrade Flyimg

To upgrade the Flyimg chart after making changes to your configuration:

```
    helm upgrade flyimg/flyimg
```

## Uninstalling Flyimg

To uninstall the chart:

```
    helm delete my-flyimg
```
