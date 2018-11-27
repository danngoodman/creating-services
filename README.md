# Creating Services in PCF

## List Available Services

List the services that are available on the platform

```
cf marketplace
```

## Create a Configuration Service

```
cf create-service p-config-server standard config-service -c '{"git": { "uri": "https://github.com/cts-workshop-12-2018/workshop-configs"} }'
```

## Create a Service Registry (Discovery)

```
cf create-service p-service-registry standard discovery-service
```