# Lab Notes

## Training Context

This repository documents a Google Cloud Skills Boost lab focused on Cloud KMS, Cloud Storage, IAM, and audit logging.

The lab was completed in a temporary training environment.

## Core Workflow

1. Create a Cloud Storage bucket.
2. Review the sample financial document.
3. Enable Cloud KMS.
4. Create `labkey` and the `qwiklab` CryptoKey.
5. Base64-encode sample plaintext for the API.
6. Encrypt the data with Cloud KMS.
7. Save the returned ciphertext as `1.encrypted`.
8. Decrypt the ciphertext and verify the original text.
9. Upload `1.encrypted` to Cloud Storage.
10. Assign Cloud KMS Admin.
11. Assign Cloud KMS CryptoKey Encrypter/Decrypter.
12. Encrypt multiple finance files in a loop.
13. Upload the encrypted files to Cloud Storage.
14. Review KMS activity in Cloud Audit Logs.

## IAM Separation

### Cloud KMS Admin
Used to manage KMS resources, including key rings and keys.

### Cloud KMS CryptoKey Encrypter/Decrypter
Used to perform encryption and decryption operations with a CryptoKey.

This separation matters because the principal managing key infrastructure does not necessarily need to be the same principal using the key for cryptographic operations.

## Encryption Notes

Base64 encoding was used only to package the data for the API. Base64 itself is not encryption.

The actual confidentiality protection came from Cloud KMS producing ciphertext.

## Evidence Limitation

The lab was completed, but the later evidence-collection rerun expired before I captured clean screenshots of:

- the batch `.encrypted` files in Cloud Storage
- the KMS audit-log view

Those steps are documented in the notes, but no screenshots are published for them.
