# Useful commands

**Install Terraform**

```sh
brew install terraform
```

**(only run only to generate provider releated files) Inintialize Terraform to download provider related resource. similiar to `npm install`**

```sh
terraform init
```

**Preview what resources to be created/updated/delete**

```sh
terraform plan
```

**Actually create/update/delete all the resources. pass in flag `-auto-approve` to skip confirmation**

```sh

# automatically apply all variables defined in `terraform.tfvars` files
terraform apply

# apply variable values to skip the command prompt. without terraform.tfvars file
terraform apply -var "subnet_prefix=10.0.1.0/24"

# apply all variables from a specific file other than default `terraform.tfvars`
terraform apply -var-file example.tfvars

```

**List all the created resources**

```sh
terraform state list
```

**See detail of one resource. `terraform state show <resource full name including type>`**

```sh
terraform state show aws_eip.one
```

**Show only the custom output without apply**

```sh
terraform output
```

**Delete all resources**

```sh
terraform destroy
```

# directory walkthrough

- `.terraform` - Terraform managed plugin releated files such as AWS providers.
- `.terraform.lock.hcl` - Terraform managed plugin lock file. Similiar to `packages.lock` and `yarn.lock` file.
- `terraform.tfstate` - Terraform managed state tracking file. It keeps track current state of live resources. This is used to compare what resources will be changed when `apply` is run.
- `terraform.tfstate.backup` - Terraform managed state tracking file for the PREVIOUS state. This is used for revert in case current `apply` run fails.
