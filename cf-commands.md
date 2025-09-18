
# Cloud Foundry (CF) Command Line Interface (CLI) Commands

## Authentication

- `cf login` - Log in to your Cloud Foundry instance.
-  `cf login -a api.cf.us10-001.hana.ondemand.com` - Log in to your Cloud Foundry Instance and set your domain (Example : us10-001)
-  `cf login --sso` - Log in to your Cloud Foundry instance with one-time passcode.
- `cf logout` - Log out from your Cloud Foundry instance.

## Application Management

- `cf push APP_NAME` - Push a new application to Cloud Foundry.
- `cf apps` - List all applications in the current space.
- `cf app APP_NAME` - Show details of a specific application.
- `cf delete APP_NAME` - Delete an application.
- `cf scale APP_NAME -i INSTANCES` - Scale the number of instances of an application.
- `cf restart APP_NAME` - Restart an application.
- `cf stop APP_NAME` - Stop an application.
- `cf start APP_NAME` - Start a stopped application.

## Service Management

- `cf create-service SERVICE PLAN SERVICE_INSTANCE` - Create a new service instance.
- `cf services` - List all service instances.
- `cf delete-service SERVICE_INSTANCE` - Delete a service instance.
- `cf bind-service APP_NAME SERVICE_INSTANCE` - Bind a service instance to an application.
- `cf unbind-service APP_NAME SERVICE_INSTANCE` - Unbind a service instance from an application.

## Environment Variables

- `cf set-env APP_NAME KEY VALUE` - Set an environment variable for an application.
- `cf unset-env APP_NAME KEY` - Unset an environment variable for an application.
- `cf env APP_NAME` - Show environment variables for an application.

## Route Management

- `cf create-route DOMAIN --path PATH` - Create a new route.
- `cf map-route APP_NAME DOMAIN --path PATH` - Map a route to an application.
- `cf unmap-route APP_NAME DOMAIN --path PATH` - Unmap a route from an application.
- `cf routes` - List all routes.

## Organization and Space Management

- `cf orgs` - List all organizations.
- `cf spaces` - List all spaces in the current organization.
- `cf target -o ORG_NAME -s SPACE_NAME` - Target a specific organization and space.

## User Management

- `cf create-user USERNAME PASSWORD` - Create a new user.
- `cf delete-user USERNAME` - Delete a user.
- `cf set-org-role USERNAME ORG_NAME ROLE` - Set a role for a user in an organization.
- `cf set-space-role USERNAME ORG_NAME SPACE_NAME ROLE` - Set a role for a user in a space.

## Logs and Monitoring

- `cf logs APP_NAME --recent` - Show recent logs for an application.
- `cf events APP_NAME` - Show events for an application.

## Miscellaneous

- `cf help` - Show help for CF commands.
- `cf version` - Show the version of the CF CLI.

## Conclusion

This list provides a foundational understanding of the Cloud Foundry CLI commands. For more detailed information, refer to the [Cloud Foundry CLI documentation](https://docs.cloudfoundry.org/cf-cli/).
