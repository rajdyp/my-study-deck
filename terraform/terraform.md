# Terraform Notes

### Terraform Architecture
```yaml
+-----------------+       +-----------+        
| Terraform state + <---> +           |       
+-----------------+       | Terraform |       +----------+
+-----------------+       |   Core    |       | AWS      |       +-----+
|Terraform config + ----> +           + <---> + Provider + <---> + AWS |       
+-----------------+       +-----------+       +----------+       +-----+
```
### Terraform Code Comments
```hcl
# single line comment
```
```hcl
// single line comment
```
```hcl
/* multi-line comment */
```

### Terraform Module
- A Terraform module is a set of Terraform configuration files in a single directory.

## Terraform Configuration 

### Configuration Block Sample

```hcl
<BLOCK TYPE> "<BLOCK LABEL>" "<BLOCK LABEL>" {
    <IDENTIFIER> = <EXPRESSION>
}
```

### Configuration Block Types:
- Settings Block
- Provider Block
  - Adds a set of resource types and/or data sources that Terraform can manage.
- Resource Block
  - Describes one or more infrastructure objects, such as virtual networks, compute instances, etc.
- Data Block
- Input Variables Block
- Local Variables Block
- Output Values Block
- Modules Block

## Variable and Outputs 

### Variable Types:
- Input variables
  - var.<name>
- Local variables
  - local.<name>

```hcl
locals {
  service_name = "example-service"
  owener       = "rajdyp"
}
```

- Output variables

```hcl
output "instance_ip_addr" {
  value = aws.instance.instance.public.ip
}
```

### Setting Input Variables
- Input variables can be set in several ways, ranked in order of precedence from lowest to highest:
  - Terraform CLI prompts
  - Default value in the block
  - Environment variables (TF_VAR_name)
  - terraform.tfvars files
  - .auto.tfvars files (auto applied)
  - -var or -var-file options
 
### Variable Value Types
- Variables can hold different value types:
  - **Primitive types:** string, number, or boolean.
  - **Complex types:** lists, sets, maps, etc.

### Handling Sensitive Data
- When using sensitive data in variables, add "sensitive = true" attribute when defining the variable to mask the data in Terraform plan output.
- Avoid storing sensitive data in files, and consider using below options for passing in those data:
  - Environment variables (TF_VAR_name)
  - -var command
  - External secret stores like AWS Secrets Manager or HashiCorp Vault


## Troubleshooting
### Delete unwanted resource introduced due to a corrupt state.
- Temporarily add unwanted resource in the terraform config.
- Import the resource to bring it under Terraform's management.
- Delete the unwanted resource. 








