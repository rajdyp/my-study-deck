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

