# Code As Module for Terraform
Terraform can import github code into a module

# How to use
### Where terraform init, plan, apply will run, create a main.tf with:
```
module null-from-github {
  source = "github.com/ion-training/terraform-use-me-as-module-github.git"
}
```

### terraform init
### terraform plan
### terraform apply

# Sample output
```
$ terraform init
Initializing modules...
Downloading github.com/ion-training/terraform-use-me-as-module-github.git for null-from-github...
- null-from-github in .terraform/modules/null-from-github

Initializing the backend...

Initializing provider plugins...
- Finding latest version of hashicorp/null...
- Installing hashicorp/null v3.1.0...
- Installed hashicorp/null v3.1.0 (signed by HashiCorp)

Terraform has created a lock file .terraform.lock.hcl to record the provider
selections it made above. Include this file in your version control repository
so that Terraform can guarantee to make the same selections by default when
you run "terraform init" in the future.

Terraform has been successfully initialized!

You may now begin working with Terraform. Try running "terraform plan" to see
any changes that are required for your infrastructure. All Terraform commands
should now work.

If you ever set or change modules or backend configuration for Terraform,
rerun this command to reinitialize your working directory. If you forget, other
commands will detect it and remind you to do so if necessary.
$
```

```
$ terraform apply

Terraform used the selected providers to generate the following execution plan. Resource actions are
indicated with the following symbols:
  + create

Terraform will perform the following actions:

  # module.null-from-github.null_resource.mynull will be created
  + resource "null_resource" "mynull" {
      + id = (known after apply)
    }

Plan: 1 to add, 0 to change, 0 to destroy.

Do you want to perform these actions?
  Terraform will perform the actions described above.
  Only 'yes' will be accepted to approve.

  Enter a value: yes

module.null-from-github.null_resource.mynull: Creating...
module.null-from-github.null_resource.mynull: Creation complete after 0s [id=6489515912540201318]

Apply complete! Resources: 1 added, 0 changed, 0 destroyed.
$
```
