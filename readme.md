## Docker local commands

### Docker Build

```bash
docker build -t demowebsite . 
```

### Export a Image to Filesystem

```bash
docker  save busybox > busybox.tar
or 
docker save myimage:latest | gzip > myimage_latest.tar.gz

```

### Docker load image from Filesystem

```bash 
docker load --imput <image.tar.gz>

```

## Azure/local commands

### Login ACR for image push

Login to Azure Tenant:

```bash
az login
```

List all subscriptions:

```bash
az account list 
```

Select target Subscription:

```bash
az account set -s <Subscription ID/Name>
```

Get all ACR in the selected subscription:

```bash
az acr list
```

Login local Docker to ACR:

```bash
az acr login -n MyRegistry
```

### Docker Tag

```bash
docker tag SOURCE_IMAGE[:TAG] TARGET_IMAGE[:TAG]
docker tag demowebsite:latest acrdemowebsite0324.azurecr.io/demowebsite:latest
```

### Docker Push to ACR

```bash
docker push TARGE_IMAGE[:TAG]
docker push acrdemowebsite0324.azurecr.io/demowebsite:latest
```
