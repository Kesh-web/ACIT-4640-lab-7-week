# ACIT-4640-lab-7-week

# Generating SSH key
## I generated a new Ed25519 SSH key named aws and saved it inside my ~/.ssh directory:
```
ssh-keygen -t ed25519 -f ~/.ssh/aws
```
ssh-keygen is the main command to start the creation of the key, -t is the type of key so in this case ed25519 based on the Edwards-curve Digital Signature Algorithm, -f is the location of which the file will be created. 

This created two files:

~/.ssh/aws — my private key

~/.ssh/aws.pub — my public key

# Importing the Key to AWS

## After generating the key pair, I used the included script to import my public key into AWS:
```
./import_key aws.pub
```
This imports the aws.pub key we created into our aws. Remember to use the public key not the private one.

# Running Terraform

## Next, I went into the Terraform directory and ran the following commands in order:
```
cd terraform
terraform init
terraform fmt
terraform validate
terraform plan
terraform apply
```
Once we cd into the terraform directory. We do ```init``` to initlaize the working directory. ```fmt``` formats terraform config file contents. ```validate``` is used to verify the syntax and internal consistency. ```plan``` creates an execution plan which lets you preview changes. ```apply``` executes those changes.

## Post terraform
After applying it outputs the dns and public ips which we use to complete the hosts.yml file in the inventory directory.


## Ansible


After editing our yml file we ran this command to do a syntax check on the yml. Used to identify any errors before executing the file.
```
ansible-playbook playbook.yml --syntax-check
```

After checking the syntax we use 
```
ansible-playbook playbook.yml
```
This runs the playbook. Executing all the commands that we have it. Here are a few installing Nginx Creating an index.html using the tempalte module, and reloading and enabling the service.


## Here is the screenshot of the rendered html page

<img width="619" height="384" alt="image" src="https://github.com/user-attachments/assets/7b4d9ddd-3671-4cbe-8f49-70b9bf1a6a22" />

After you can use the "delete_lab_key" script to delete the key we made at the beginning and use ```terraform destroy``` to destroy the aws infrastructure we created.

The end.

Alfred Chan
Kesh Thalagala
Leeanne Li



