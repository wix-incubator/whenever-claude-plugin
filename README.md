# Whenever

Build and manage [Whenever](https://www.whenever.dev) automations from Claude. Describe a recurring
task and Claude writes the workflow, checks it, and saves a draft in your Whenever account. Claude
can also turn workflows on, show their triggers, and read the results of past runs. It runs a
workflow by hand only when you ask.

## What the server's tools can do

The plugin bundles the Whenever MCP server. Besides reading your workflows, runs, triggers and docs,
its tools can change things in your Whenever account and, through your workflows, in the services
you connected:

- **Send, post and pay through your connected services.** `run_workflow_manual` and
  `start_debug_session` run a workflow now, and `publish_workflow` turns its triggers on so it runs
  by itself. A running workflow does whatever its steps do in your connected services: it can send
  emails and messages, post or publish content, change or delete records, or make payments.
  Claude runs a workflow by hand only when you ask.
- **Publish and unpublish.** `publish_workflow` makes a workflow live; `unpublish_workflow` turns
  its triggers off. `set_webhook_enabled`, `set_feed_trigger_paused`, `set_managed_trigger_paused`
  and `set_account_event_trigger_paused` pause or resume a single trigger.
- **Delete.** `delete_workflow` deletes a workflow, `delete_workflow_config` a config value and
  `delete_secret` a stored secret. Deletion is permanent.
- **Change access.** `disconnect_managed_connection` and `disconnect_manual_connection` remove a
  stored provider connection, so workflows lose access to that service. `request_secret_change`,
  `request_connection_setup` and `request_connection_rotation` give you a link to add or replace a
  secret or credential in Whenever in your browser; Claude never sees the value.
- **Create and edit.** `create_workflow`, `start_workflow_from_template`, `save_workflow_draft` and
  `set_workflow_config` create workflows and change drafts and config.

## Install

In Claude Code:

```
/plugin install whenever --marketplace wix-incubator/whenever-claude-plugin
```

## Sign in

The plugin connects to `https://mcp.whenever.dev/`. The first time Claude uses it, sign in with your
Whenever account. Claude sees only your own workflows. Provider connections and secrets are set up
in Whenever in your browser; Claude never sees their values.

## Support

Email `support` at `whenever.dev` (spelled out to keep the address away from spam crawlers).

## Privacy

[Whenever privacy policy](https://www.whenever.dev/privacy).
