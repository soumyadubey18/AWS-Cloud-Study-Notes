# 07 — EFS (Elastic File System)

## What is EFS?

**EFS = Elastic File System.** The trainer material describes it as AWS managed file storage designed for shared access by multiple compute resources.

**Remember:** EFS = Shared File Storage.

## Key points from the trainer lab

- Multiple Linux EC2 instances can mount the same EFS.
- Protocol: **NFS (Network File System)**
- Port: **TCP 2049**
- The lab demonstrates access from EC2s in different Availability Zones.
- EFS automatically scales as data grows/shrinks.

## EFS practical flow

1. Launch two Linux EC2 instances.
2. Install EFS utilities on both:

```bash
sudo yum install amazon-efs-utils -y
```

3. Create an EFS file system.
4. Use an EFS Security Group allowing NFS 2049 from the EC2 Security Group.
5. On both EC2s:

```bash
sudo mkdir /shared-data
```

6. Mount the EFS:

```bash
sudo mount -t efs fs-xxxxxxxx:/ /shared-data
```

7. Verify:

```bash
df -h
```

8. On server 1:

```bash
cd /shared-data
echo "Hello from Server-1" > file1.txt
touch students.txt
```

9. On server 2, open `/shared-data` and verify the same files.

10. Optional automatic mount at boot:

```bash
sudo vi /etc/fstab
fs-xxxxxxxx:/ /shared-data efs defaults,_netdev 0 0
sudo mount -a
```

## EBS vs EFS

- **EBS:** block/disk storage for EC2.
- **EFS:** shared file storage that multiple Linux EC2 instances can mount.

**Memory:** EBS = Block | EFS = File.
