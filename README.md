# Creating Services in PCF

## Login to PCF

Make sure you have the PCF CLI installed:
[https://docs.run.pivotal.io/cf-cli/install-go-cli.html](https://docs.run.pivotal.io/cf-cli/install-go-cli.html)

Verify you have a version greater than 6.37
```
cf --version
```

Instructions to login to the workshop PCF foundation (refer to the workshop agenda):
```
cf login -a api.sys.prod.us-west-2.cernercf.io --sso
```

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

For Windows, use:
```
cf create-service p-config-server standard config-service -c "{\"git\": { \"uri\": \"https://github.com/cts-workshop-12-2018/workshop-configs\"} }"
```

## Create a Service Registry (Discovery)

Our apps will register with a discovery service that allows for blue/green deployment, scaling, load balancing and more:

```
cf create-service p-service-registry standard discovery-service
```

## Create a MySQL database

Create a MySQL database for persistence:

```
cf create-service p.mysql db-small mysql-service
```

## Deploy a web app to PCF 

[Deploy a web app to PCF](https://github.com/cts-workshop-12-2018/angular7-m0)
