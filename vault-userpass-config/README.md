# Userpass: Username and Password-Based Authentication and Authorization in Vault


## Steps

### Enable Userpass Authentication

To activate the userpass authentication method, execute the following command:

```bash
vault auth enable userpass
```

Once enabled, we can create user accounts with specific usernames and passwords. Additionally, each account can be assigned predefined policies that determine their level of access.

### Creating User Accounts

In this example, we will create two types of user accounts:

+ Admin Account – Has full access to Vault based on the admin policy.
+ Regular User Account – Has limited access based on a non-admin policy (e.g., jenkins).

Creating an Admin Account

To create an admin account with the username admin, password admin, and assigned admin policy, use the following command:

```bash
vault write auth/userpass/users/admin password=admin policies=admin
```

Expected Output:

```bash
Success! Data written to: auth/userpass/users/admin
```

Creating a Non-Admin User Account

To create a regular user account with the username user1, password testuser, and assigned jenkins policy, execute:

```bash
vault write auth/userpass/users/user1 password=testuser policies=jenkins
```

Expected Output:

```bash
Success! Data written to: auth/userpass/users/user1
```

### Summary of Actions Performed

✔️ Enabled the userpass authentication method in Vault.

✔️ Created an admin user with unrestricted access.

✔️ Created a regular user with restricted access based on the jenkins policy.

This setup ensures secure authentication while providing role-based access control to Vault resources. 🚀