
### CloudFoundy CLI Installation
> Install according to your OS
* https://github.com/cloudfoundry/cli/releases

### CloudFoundry Version
> Once Installed from above step - Kindly run the below command anyone to check if its been installed Properly
```
cf -v
cf7 -v
cf8 -v
```

### Destination 
```
cf create-service destination lite my-destination-service
cf create-service-key my-destination-service my-destination-service-key
```

```
cf service-key my-destination-service my-destination-service-key
```

### SAP BTP Job Scheduler
```
cf create-service jobscheduler lite Jobscheduler -c '{"enable-xsuaa-support": true}'
```

### XSUAA (Authorization & Trust) 
```
cf create-service xsuaa application myxsuaa
cf create-service-key myxsuaa myxsuaa-service-key
```

```
cf create-service xsuaa space my-xsuaa
cf create-service-key my-xsuaa my-xsuaa-sk
```

```
cf create-service xsuaa apiaccess myxsuaa-api
cf create-service-key myxsuaa-api myxsuaa-api-service-key
```

### Autoscaler
```
cf create-service autoscaler standard autoscaler
cf create-service application-logs lite myapplication-logs
cf create-service auditlog-management default myauditlog
cf create-service transport standard transport
cf create-service redis-cache trial redis
cf create-service it-rt integration-flow iflow
cf create-service connectivity lite connectivity
cf create-service credstore trial credentials
cf create-service feature-flags  lite feature-flags
cf create-service html5-apps-repo app-host html5-apps
cf create-service html5-apps-repo app-runtime html5-apps-runtime
```

### Alert Notification Services
```
cf create-service alert-notification standard alert-notification
cf create-service-key alert-notification sk
```

### Reporting
```
cf create-service uas reporting-ga-admin uas
cf create-service-key uas sk
```

### Saas Registry for Multitenant
```
cf create-service saas-registry application saas-registry   
```

```
cf create-service data-attribute-recommendation-trial standard data-attribute-recommendation
```


```
### takes more time
cf create-service-key data-attribute-recommendation sk
```

```
cf marketplace -e hana
cf create-service hana schema hdb-staging-schema -c '{ "schema" : "STAGING4UPLOADS" }'
cf create-service-key hdb-staging-schema hdb-staging-schema-sk
cf service-key hdb-staging-schema hdb-staging-schema-sk
CONNECT STAGING4UPLOADS PASSWORD "Your_Long_Password_From_The_ServiceKey"
SELECT Current_User, Current_Schema FROM dummy
```

### Database 
```
cf create-service postgresql-db trial postgres-hyperscaler
cf create-service-key postgres-hyperscaler postgre_key      ### Need to execute after 5mins
cf service-key postgres-hyperscaler-postgre_key
```

```
cf delete -rf csv2hdb
cf delete-service-key -f hdb-staging-schema hdb-staging-schema-sk
cf delete-service -fw hdb-staging-schema
```

```
cf create-service personal-data-manager-service standard pdm
```
