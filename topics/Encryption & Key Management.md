# Encryption & Key Management

## What is Encryption?

Encryption transforms readable data into unreadable text unless decrypted with the correct key.  
In cloud security, it enforces **confidentiality**, protects sensitive data, and helps meet compliance standards.



## Key Concepts

### Types of Encryption
- **Symmetric Encryption**: Same key for encryption and decryption (e.g., AES-256)
- **Asymmetric Encryption**: Uses public/private key pairs (e.g., RSA, ECC)

### Data States
- **Data at Rest**: Stored data (e.g., EBS, S3, RDS)
- **Data in Transit**: Data moving across networks (e.g., TLS, VPN)
- **Data in Use**: Data actively processed in memory

### Key Management
- **KMS (Key Management Service)**: Centralized service for managing encryption keys
- **Envelope Encryption**: Encrypt data with a data key, which is encrypted with a master key (CMK)
- **Customer Master Key (CMK)**: Primary key used to encrypt/decrypt data keys
- **Secret Rotation**: Regularly updating keys/secrets to reduce risk



## Goals of Encryption & Key Management

- Protect sensitive data from unauthorized access  
- Meet compliance and regulatory requirements  
- Minimize the impact of data breaches  



## Best Practices

- Always enable encryption at rest and in transit  
- Use managed key services (AWS KMS, Azure Key Vault)  
- Implement envelope encryption for scalable security  
- Rotate keys regularly  
- Apply least privilege to key usage and management  
- Audit all key usage and access logs  



## Tools

- **AWS KMS** – Key creation, rotation, and policy enforcement  
- **Azure Key Vault** – Secure storage for keys, secrets, and certificates  
- **HashiCorp Vault** – Dynamic secrets, encryption as a service, and access control  


## Examples

- **S3 Bucket with SSE-KMS Enabled**  
- **TLS Certificate Enforcing HTTPS**


## Practice Scenario

### Encrypting an S3 Bucket with CMK

1. Create a CMK in AWS KMS  
2. Attach a bucket policy to enforce encryption using the CMK  
3. Enable server-side encryption (SSE-KMS) on the S3 bucket  
4. Upload objects and verify encryption status  

### Auditing Access Logs

- Enable AWS CloudTrail  
- Filter logs for `kms:Decrypt`, `kms:Encrypt`, and `s3:PutObject`  
- Review access patterns and detect anomalies  



## Mapping to Standards

- **NIST 800-53**: SC-12, SC-13  
- **CIS Controls**: 3.11, 14.4  
- **SOC 2**: CC6.6  
