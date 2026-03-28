# SAP CAP CLI: `cds add` Commands – How They Work

The `cds add` command is a powerful CAP CLI tool that helps you quickly scaffold, integrate, and configure common capabilities in your CAP project. Each sub-command sets up specific features or integrations using best practices.

---

## General Syntax

```bash
cds add <feature>
```
This will add the specified feature to your project and update files (like `package.json`, `.cdsrc.json`, or insert new folders/files) to wire everything up.

---

## Most Common Features

### 1. **`cds add hana`**
**Purpose:** Prepares your CAP project for deployment to SAP HANA.
- Adds `@sap/hana-client` and `@sap/hdbext` dependencies.
- Adds default `db`/`src` model for HANA.
- Creates `default-env.json` for local HANA emulation (if needed).
- Updates `.cdsrc.json` for HANA.
- **When:** Use this when you plan to use SAP HANA as your persistence layer.
- **How:**  
  ```bash
  cds add hana
  ```

---

### 2. **`cds add mta`**
**Purpose:** Sets up Multi-Target Application (MTA) descriptor for SAP BTP Cloud Foundry deployment.
- Generates `mta.yaml` file based on your project content.
- Auto-updates when main modules are added/removed.
- **When:** Required for Cloud Foundry BTP deployments that need MTA.
- **How:**  
  ```bash
  cds add mta
  ```

---

### 3. **`cds add xsuaa`**
**Purpose:** Integrates SAP XSUAA authentication and authorization.
- Adds security config: `xs-security.json`.
- Updates `manifest.yml`/`mta.yaml`.
- Adds dependency for `@sap/xssec`.
- **When:** Use when your CAP app will have authentication/authorization via SAP BTP.
- **How:**  
  ```bash
  cds add xsuaa
  ```

---

### 4. **`cds add approuter`**
**Purpose:** Adds an Application Router for UIs and authentication.
- Creates an `approuter/` folder with configuration files.
- Adds sample routing config.
- Updates MTA as needed.
- **When:** For multi-module projects or UIs (especially if using SAP Fiori Elements).
- **How:**  
  ```bash
  cds add approuter
  ```

---

### 5. **`cds add samples`**
**Purpose:** Adds sample services, data, and models for learning/quick start.
- Brings in working sample entities (Books, Authors, etc.).
- Safe for new or demo/test projects.
- **How:**  
  ```bash
  cds add samples
  ```

---

### 6. **`cds add pipeline`**
**Purpose:** Sets up a CI/CD pipeline configuration (usually for SAP BTP CI/CD).
- Adds `.pipeline/` folder with configs for CI/CD.
- **How:**  
  ```bash
  cds add pipeline
  ```

---

### 7. **`cds add health`**
**Purpose:** Adds health check endpoints for your service (for monitoring readiness/liveness).
- Adds endpoints like `/health` out-of-the-box.
- Useful for containerized/BTP managed environments.
- **How:**  
  ```bash
  cds add health
  ```

---

### 8. **`cds add multitenancy`**
**Purpose:** Enables Multitenancy for SaaS scenarios.
- Adds Tenant-specific configuration and boilerplate handlers.
- Updates MTA dependencies as needed.
- **How:**  
  ```bash
  cds add multitenancy
  ```

---

### 9. **`cds add cf-manifest`**
**Purpose:** Adds `manifest.yml` file for pushing the app directly to Cloud Foundry without MTA.
- **How:**  
  ```bash
  cds add cf-manifest
  ```

---



## How These Add Commands Work

- Checks your current project state and adds missing dependencies.
- Modifies project files as needed: `package.json`, `.cdsrc.json`, `mta.yaml`, etc.
- Scaffolds new folders/setup according to the feature you add.
- Can be run multiple times for different features (idempotent, will not overwrite custom code).

> **Tip:** Always check `git diff` after running any `cds add ...` to review changes.

---

## For More Information

- Full list and details: [cds add documentation](https://cap.cloud.sap/docs/tools/cds-cli#cds-add)
- Run `cds help add` for dynamic help on all addable features in your current CAP CLI installation.

---

*Keep your CAP projects robust and up-to-date by leveraging these commands whenever you need to add new capabilities!*
