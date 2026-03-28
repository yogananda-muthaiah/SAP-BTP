# SAP CAP (Cloud Application Programming Model) CLI & NPM Commands

A practical list of essential commands and scripts for developing, testing, and managing SAP CAP projects, following best practices from [cap.cloud.sap](https://cap.cloud.sap/).

---

## Initialize a New CAP Project

```bash
cds init my-bookshop      # Creates a new CAP project 'my-bookshop'
cds add samples           # Adds sample content to your project 
cds add model             # Adds a 'db' folder for models (if not present)
```

---

## CDS Development Commands

```bash
cds watch                 # Live-reloads app on save (for development)
cds serve                 # Serves your service locally
cds run                   # Alias for cds serve (recommended)
cds deploy --to sqlite    # Deploys your data model to a local sqlite db
cds compile srv/service.cds --to sql   # Compiles model to SQL
```

---

## Adding Features & Layers

```bash
cds add hana              # Sets up for SAP HANA deployment
cds add mta               # Initializes an MTA (Multi-Target Application)
cds add approuter         # Adds an Approuter module
cds add xsuaa             # Adds authentication/authorization (XSUAA)
cds add samples           # Adds working sample content
cds add pipeline          # Adds CI/CD pipeline config
```

---

## Testing & Debugging

```bash
npm test                  # Runs unit and integration tests
cds watch --profile test  # Runs in test profile with test db
cds mock                  # Launches mock services for testing
cds lint                  # Checks model syntax/style
```

---

## Deployment

```bash
cds deploy --to sqlite    # Deploy data model to local sqlite for dev/testing
cds deploy --to hana      # Deploy data model to SAP HANA
cf push                   # Deploy MTA to Cloud Foundry (after build)
mbt build                 # Builds MTA archive (if using MTA)
```

---

## Data Management

```bash
cds deploy                # Deploys all db artifacts
cds bind                  # Binds service instances to the app (BTP context)
cds unbind                # Unbinds service instances
cds repl                  # Opens a REPL for interactive data access
```

---

## Common NPM Scripts (package.json)

```json
"scripts": {
  "start": "cds run",
  "watch": "cds watch",
  "build": "cds build/all",
  "test": "mocha test/",
  "deploy": "cds deploy --to hana"
}
```
> These scripts can be run as `npm start`, `npm run watch`, etc.

---

## Other Useful CAP Commands

```bash
cds upgrade               # Upgrade project to latest CAP version
cds help                  # List all available CAP commands
```

---

## References

- [CAP Documentation](https://cap.cloud.sap/docs/)
- [CAP Command-Line Interface](https://cap.cloud.sap/docs/cli/cds/)
- [SAP Tutorials for CAP](https://developers.sap.com/topics/cloud-application-programming.html)

---

*For more options, run `cds help` or consult the links above. Tailor commands to your specific workflow as needed!*

