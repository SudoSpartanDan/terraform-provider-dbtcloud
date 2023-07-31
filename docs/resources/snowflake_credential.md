---
page_title: "dbtcloud_snowflake_credential Resource - dbtcloud"
subcategory: ""
description: |-
  
---

# dbtcloud_snowflake_credential (Resource)




## Example Usage

```terraform
// use dbt_cloud_snowflake_credential instead of dbtcloud_snowflake_credential for the legacy resource names
// legacy names will be removed from 0.3 onwards

resource "dbtcloud_snowflake_credential" "new_credential" {
  project_id  = data.dbt_cloud_project.test_project.project_id
  auth_type   = "password"
  num_threads = 16
  schema      = "SCHEMA"
  user        = "user"
  password    = "password"
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `auth_type` (String) The type of Snowflake credential ('password' or 'keypair')
- `num_threads` (Number) Number of threads to use
- `project_id` (Number) Project ID to create the Snowflake credential in
- `schema` (String) Default schema name
- `user` (String) Username for Snowflake

### Optional

- `database` (String) Database to connect to
- `is_active` (Boolean) Whether the Snowflake credential is active
- `password` (String, Sensitive) Password for Snowflake
- `private_key` (String, Sensitive) Private key for Snowflake
- `private_key_passphrase` (String, Sensitive) Private key passphrase for Snowflake
- `role` (String) Role to assume
- `warehouse` (String) Warehouse to use

### Read-Only

- `credential_id` (Number) The system Snowflake credential ID
- `id` (String) The ID of this resource.

## Import

Import is supported using the following syntax:

```shell
# Import using a project ID and credential ID found in the URL or via the API.
terraform import dbtcloud_snowflake_credential.test_snowflake_credential "project_id:credential_id"
terraform import dbtcloud_snowflake_credential.test_snowflake_credential 12345:6789
```