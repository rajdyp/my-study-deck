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
- Terraform Settings Block
- Terraform Provider Block
- Terraform Resource Block
- Terraform Data Block
- Terraform Input Variables Block
- Terraform Local Variables Block
- Terraform Output Values Block
- Terraform Modules Block

### Variable Types:
- Input variables
  - var.<name>
- Local variables
  - local.<name>

```hcl
locals {
  service_name = "My service"
  owener       = "rajdyp"
}
```

- Output variables

```hcl
output "instance_ip_addr" {
  value = aws.instance.instance.public.ip
}
```













