# ACIT-4640-lab-7-week

## Generating SSH key
# I generated a new Ed25519 SSH key named aws and saved it inside my ~/.ssh directory:
```
ssh-keygen -t ed25519 -f ~/.ssh/aws
```
This created two files:

~/.ssh/aws — my private key
~/.ssh/aws.pub — my public key

## Importing the Key to AWS

# After generating the key pair, I used the included script to import my public key into AWS:
```
./import_key aws.pub
```
## Running Terraform

Next, I went into the Terraform directory and ran the following commands in order:
```
cd terraform
terraform init
terraform fmt
terraform validate
terraform plan
terraform apply
```
After applying it outputs the dns and public ips 
