# Cloud_Security
# Task 4: IAM Policies, Secure Storage, and Data Encryption

## 🔐 Overview
This task simulates implementing IAM policies, encrypting sensitive data, and securely storing it as if using a cloud platform (e.g., AWS S3), without requiring a credit card.

## 📁 Files Included
- `encrypt_data.py` - Python script to encrypt/decrypt data
- `data.txt` - Sample confidential data to encrypt
- `encrypted_file.txt` - Encrypted result simulating secure cloud storage
- `IAM_Policy.json` - Simulated IAM policy for access control
- `report_task4.pdf` - Documentation of the entire setup

## 🧪 How to Use
1. Create or edit `data.txt` with your data.
2. Run `python encrypt_data.py encrypt` to encrypt and store it.
3. Run `python encrypt_data.py decrypt` to recover the original message.

## 📋 Notes
- This is a local simulation of cloud security practices.
- No actual AWS account or billing is required.

## 👩‍💻 Done By
Vanshika Sahu

##codes
1. IAM_Policy.json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "s3:GetObject",
        "s3:PutObject"
      ],
      "Resource": "arn:aws:s3:::my-secure-bucket/*"
    }
  ]
}

2. encrypt_script.py
   from cryptography.fernet import Fernet
import os

# Generate key and encrypt data
key = Fernet.generate_key()
cipher = Fernet(key)

# Simulate a file
with open("data.txt", "w") as f:
    f.write("Sensitive Job Application Data")

# Encrypt the file
with open("data.txt", "rb") as file:
    encrypted = cipher.encrypt(file.read())

with open("simulated_s3/encrypted_data.txt", "wb") as file:
    file.write(encrypted)

print("File encrypted and saved in simulated_s3 folder.")



