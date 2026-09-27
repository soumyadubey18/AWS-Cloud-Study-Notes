# Practical 06 — S3 CLI + Private S3 Access

## Check AWS CLI identity

```bash
aws --version
aws sts get-caller-identity
aws s3 ls
```

## Upload, list, download and delete

Create a test file:

```bash
echo "Hello from EC2" > test.txt
```

Upload:

```bash
aws s3 cp test.txt s3://YOUR-BUCKET-NAME/
```

List:

```bash
aws s3 ls s3://YOUR-BUCKET-NAME/
```

Download:

```bash
aws s3 cp s3://YOUR-BUCKET-NAME/test.txt downloaded.txt
```

Read:

```bash
cat downloaded.txt
```

Delete object:

```bash
aws s3 rm s3://YOUR-BUCKET-NAME/test.txt
```

## Private EC2 → S3 without NAT

Create an **S3 Gateway VPC Endpoint** and associate it with the private route table.

Trainer flow:

```text
VPC → Endpoints → Create endpoint
Service = com.amazonaws.<region>.s3
Type = Gateway
VPC = VPC-A
Route table = Private-RT-A
```

Then from the private EC2:

```bash
aws s3 ls
aws s3 cp test.txt s3://YOUR-BUCKET-NAME/
```

## Common S3 CLI errors

### `Unable to locate credentials`

Check the EC2 IAM Role / CLI authentication method.

### `AccessDenied`

Check IAM Role/User permissions and the S3 bucket policy.
