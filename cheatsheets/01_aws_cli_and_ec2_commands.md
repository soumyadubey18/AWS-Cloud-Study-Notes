# AWS CLI + EC2 Command Cheat Sheet

## AWS CLI
```bash
aws --version
aws sts get-caller-identity
aws s3 ls
aws s3 cp test.txt s3://BUCKET-NAME/
aws s3 ls s3://BUCKET-NAME/
aws s3 cp s3://BUCKET-NAME/test.txt downloaded.txt
aws s3 rm s3://BUCKET-NAME/test.txt
```

## EC2 / Linux checks used in AWS labs
```bash
ssh -i My_key2.pem ec2-user@<PUBLIC-IP>
chmod 400 My_key2.pem
lsblk
df -h
mount
umount /data
systemctl status httpd
systemctl start httpd
systemctl enable httpd
curl http://localhost
ss -tulnp
ip addr
ip route
ping <PRIVATE-IP>
```

## Storage
```bash
sudo fdisk /dev/nvme1n1
sudo mkfs.xfs /dev/nvme1n1p1
sudo mkdir -p /data
sudo mount /dev/nvme1n1p1 /data
sudo blkid /dev/nvme1n1
sudo mount -a
sudo umount /data
```
