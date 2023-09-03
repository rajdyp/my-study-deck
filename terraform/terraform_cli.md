# Terraform commands

## Basic commands
```yaml
terraform -help
```

```yaml
terraform init    # initializes a working directory
```

```yaml
terraform init -upgrade    # to allow selection of new versions
```

```yaml
terraform fmt
```

```yaml
terraform console
```

```yaml
terraform validate
```

## Plan
```yaml
terraform plan    # creates an execution plan
```

```yaml
terraform plan -out <file_name>    # save generated plan to a file on disk
```

```yaml
terraform plan -destroy
```

## Apply
```yaml
terraform apply    # executes the actions proposed in a Terraform plan
```

```yaml
terraform apply -refresh-only
```

```yaml
terraform apply -auto-approve
```

```yaml
terraform apply -replace <resource>
```

## Variables
```yaml
terraform plan/apply -var <var_name>=<value>    # variables on the CLI
```

```yaml
export TF_VAR_<var_name>=<value>    # export environment variable
```

```yaml
unset TF_VAR_<var_name>    # unset environment variable
```

## Destroy
```yaml
terraform destroy    # destroy all remote objects managed by Terraform configuration
```

```yaml
terraform providers
```

## State
```yaml
terraform state list    # list all resources in the state file
```

```yaml
terraform state show <resource>
```

```yaml
terraform state rm <resource>
```

```yaml
terraform refresh
```

```yaml
terraform taint <resource>
```

```yaml
terraform untaint <resource>
```

## Workspace
```yaml
terraform workspace new <ws_name>
```

```yaml
terraform workspace show
```

```yaml
terraform workspace list
```

```yaml
terraform workspace select <ws_name>
```

## Show
```yaml
terraform show
```

```yaml
terraform show -json | jq
```

## Output
```yaml
terraform output
```

## import
```yaml
terraform import
```
