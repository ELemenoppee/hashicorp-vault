#  Enabling Audit Logs in HashiCorp Vault

This guide provides a comprehensive walkthrough on enabling audit logging in HashiCorp Vault, allowing administrators to track access and operations, enhance security monitoring, and meet compliance requirements.

## Prerequisites

+ Vault Server Running: Ensure that HashiCorp Vault is installed and running in either development or production mode.

+ Logging Directory: A directory for storing audit logs with appropriate permissions should be available on your system.

## Steps :-

### **Step 1** — Enable an Audit Device

HashiCorp Vault supports multiple audit devices, such as file or syslog. To enable a file-based audit log:

```bash
vault audit enable file file_path=/logs/vault/audit.log
```

This command specifies a file_path for storing logs, which Vault will begin to use immediately after enabling.

### **Step 2** — Verify Audit Device Configuration

After enabling, confirm the audit device is active:

```bash
vault audit list
```

This should display your configured audit devices along with their logging paths.

### **Step 3** — Test and View Logs

Generate an example log by interacting with Vault, such as listing secrets. Then, review the audit log file to see entries detailing these operations:

```bash
cat /logs/vault/audit.log
```

### **Step 4** — Disable an Audit Device (If Necessary)

If you need to disable audit logging temporarily or permanently:

```bash
vault audit disable file
```

## Additional Note

For automated setup, refer to the HashiCorp Vault Installation: https://github.com/ELemenoppee/devops-projects/tree/main/project-10 using Terraform for more details.

By enabling audit logs, you add a valuable layer of security to monitor and track operations within your Vault environment.
