# ♣️ Adding Secrets to Vault ♣️

## Description 

This guide provides instructions on securely adding secrets to HashiCorp Vault, a tool that helps manage secrets and sensitive data in a centralized, secure way.

## Prerequisites 👽

+ Vault Installed and Configured: Ensure that Vault is installed and initialized on your system.

 + Vault CLI Access: This guide assumes that you have the Vault CLI installed and configured.

## Steps 👓:-

**Step 1** — Log into Vault (if needed)

If you haven't already logged into Vault, use the following command with your Vault token to authenticate:

```bash
vault login <your-token>
```

Replace <your-token> with your actual Vault token.

**Step 2** — Determine the Path for the Secret

Vault organizes secrets by paths. Decide on the path where you’ll store the secret. For example, to store a database password, you might use the path `secret/data/database`.

**Step 3** — Add a Secret to Vault

To add a secret, use the `vault kv put` command followed by the path and key-value pairs you want to store. For example, to store a username and password for a database, use:

```bash
vault kv put secret/data/database username="my-username" password="my-password"
```

In this example:
+ `secret/data/database` is the path where the secret is stored.
+ `username` and `password` are the key names, and their values are the secret data you’re storing.

**Step 4** — Verify the Secret

To confirm that the secret was added successfully, retrieve it using the vault kv get command:

```bash
vault kv get secret/data/database
```

This command will display the secret data for verification.

**Step 5** — Update an Existing Secret (Optional)

If you need to update an existing secret, use the same vault kv put command with the new values:

```bash
vault kv put secret/data/database username="new-username" password="new-password"
```

Vault will automatically version the secret, retaining a history of previous values.

