# Practical 09 — AWS CLI Reference Used in AWS Labs

## Identity

```bash
aws sts get-caller-identity
```

## EC2

```bash
aws ec2 describe-instances --no-cli-pager
```

## VPC

```bash
aws ec2 describe-vpcs --no-cli-pager
aws ec2 describe-subnets --no-cli-pager
aws ec2 describe-route-tables --no-cli-pager
```

## S3

```bash
aws s3 ls
aws s3 cp test.txt s3://BUCKET-NAME/
aws s3 ls s3://BUCKET-NAME/
aws s3 cp s3://BUCKET-NAME/test.txt downloaded.txt
```

## RDS

```bash
aws rds describe-db-instances --no-cli-pager
```

## CLI pager note

The practical handbook notes that `q` returns from long pager output and that this can be disabled with:

```bash
aws configure set cli_pager ""
```
