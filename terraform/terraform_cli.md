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

## Destroy
```yaml
terraform destroy    # destroy all remote objects managed by Terraform configuration
```

```yaml
terraform providers
```

## State
```yaml
terraform state list
```

```yaml
terraform state show <resource>
```

```yaml
terraform apply -replace <resource>
```

## Show
```yaml
terraform show
```

```yaml
terraform show -json | jq
```
