---
page_title: "dbtcloud_webhook Resource - dbtcloud"
subcategory: ""
description: |-
  
---

# dbtcloud_webhook (Resource)




## Example Usage

```terraform
// use dbt_cloud_webhook instead of dbtcloud_webhook for the legacy resource names
// legacy names will be removed from 0.3 onwards

resource "dbtcloud_webhook" "test_webhook" {
  name        = "my-webhook"
  description = "My webhook"
  client_url  = "http://localhost/nothing"
  event_types = [
    "job.run.started",
    "job.run.completed"
  ]
  job_ids = [
    1234,
    5678
  ]
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `client_url` (String) Webhooks Client URL
- `event_types` (List of String) Webhooks Event Types
- `name` (String) Webhooks Name

### Optional

- `active` (Boolean) Webhooks active flag
- `description` (String) Webhooks Description
- `job_ids` (List of Number) List of job IDs to trigger the webhook, An empty list will trigger on all jobs

### Read-Only

- `account_identifier` (String) Webhooks Account Identifier
- `hmac_secret` (String, Sensitive) Secret key for the webhook. Can be used to validate the authenticity of the webhook.
- `http_status_code` (String) Latest HTTP status of the webhook
- `id` (String) The ID of this resource.
- `webhook_id` (String) Webhooks ID

## Import

Import is supported using the following syntax:

```shell
# Import using a job ID found in the URL or via the API.
terraform import dbtcloud_webhook.test_webhook "job_id"
terraform import dbtcloud_webhook.test_webhook wsu_abcdefg
```
