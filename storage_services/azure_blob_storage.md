# Azure Blob Storage

Azure Blob storage is an object storage solution for the cloud. It can store massive amounts of data, such as text or binary data. Azure Blob storage is unstructured, meaning that there are no restrictions on the kinds of data it can hold. Blob storage can manage thousands of simultaneous uploads, massive amounts of video data, constantly growing log files, and can be reached from anywhere with an internet connection.

## Comparison with AWS S3

| Feature / Concept           | AWS S3 (Simple Storage Service)     | Azure Blob Storage                         |
|----------------------------|--------------------------------------|--------------------------------------------|
| Object storage service     | S3                                   | Blob Storage                                |
| Top-level resource         | S3 Bucket                            | Azure Storage Account                       |
| Container/folder           | Bucket                               | Container (inside a Storage Account)        |
| Storage tiers              | Standard, Infrequent Access, Glacier | Hot, Cool, Archive                          |
| Static website hosting     | Yes                                  | Yes                                         |
| Versioning support         | Yes                                  | Yes                                         |
| Lifecycle rules            | Yes                                  | Yes                                         |
| Access control             | IAM Policies, Bucket ACLs            | Azure RBAC, Shared Access Signatures (SAS) |
| Encryption                 | SSE-S3, SSE-KMS, SSE-C                | Microsoft-managed keys, Customer-managed   |
| Event triggers             | EventBridge, SNS, Lambda             | Event Grid, Logic Apps, Functions           |
| CLI Tools                  | `aws s3`                             | `az storage blob`, `AzCopy`                 |
