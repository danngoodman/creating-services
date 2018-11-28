# Creating Services in PCF

## List Available Services

List the services that are available on the platform

```
cf marketplace
```

## Create a Configuration Service

Parts of our app will get their configurations from a service deployed to each space:

```
cf create-service p-config-server standard config-service -c '{"git": { "uri": "https://github.com/cts-workshop-12-2018/workshop-configs"} }'
```

## Create a Service Registry (Discovery)

Our apps will register with a discovery service that allows for blue/green deployment, scaling, load balancing and more:

```
cf create-service p-service-registry standard discovery-service
```

## Create a MySQL database

Create a MySQL database for persistence:

```
cf create-service p-mysql 100mb mysql-service
```