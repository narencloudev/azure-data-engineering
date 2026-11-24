# ADF Security: Managed Identity and Key Vault

## Managed identity
A managed identity gives an Azure resource an identity in Microsoft Entra ID so it can authenticate to supported services without storing a password in code.

## Key Vault
Azure Key Vault securely stores secrets, keys, and certificates. ADF can retrieve supported secrets through a Key Vault linked service when permissions and network access are configured.

## Least privilege
Grant only the permissions required for the specific storage account, database, or secret. Prefer scoped roles and access policies according to the service's current authorization model.

## Security checklist
- Prefer managed identity where supported.
- Store secrets in Key Vault, not in notebooks, Git, or plain-text JSON.
- Restrict network access and use private connectivity where required.
- Rotate credentials and review permissions.
- Never commit connection strings, keys, or tokens to GitHub.

## Practice
Document the permissions needed for ADF to read from a storage account and retrieve a secret from Key Vault.
