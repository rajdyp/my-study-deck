# AWS CLI commands

## Basic

```yaml
aws
```

```yaml
aws configure  # configure AWS CLI access key
```

## IAM

```yaml
aws iam list-users
```

```yaml
aws iam get-user --user-name <user_name>
```

```yaml
aws iam create-user --user-name <user_name>
```

```yaml
aws iam list-groups
```

```yaml
aws iam get-group --group-name <group_mame> 
```

```yaml
aws iam create-group --group-name <group_mame> 
```

```yaml
aws iam add-user-to-group --user-name <user_name> --group-name <group_mame> 
```


## S3

```yaml
aws s3 ls
```

```yaml
aws s3 mb s3://<bucket_name>  # bucket name has to be globally unique
```
