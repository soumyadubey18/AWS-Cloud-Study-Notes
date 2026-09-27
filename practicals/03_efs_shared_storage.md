# Practical 03 — EFS Shared Storage

## Goal

Mount one EFS file system on two Linux EC2 instances and verify that files created on one server are visible on the other.

## Steps

1. Launch two Linux EC2 instances.
2. Install EFS utilities on both:

```bash
sudo yum install amazon-efs-utils -y
```

3. Create EFS.
4. EFS Security Group: allow **NFS TCP 2049** from the EC2 Security Group.
5. Create mount directory on both:

```bash
sudo mkdir /shared-data
```

6. Mount:

```bash
sudo mount -t efs fs-xxxxxxxx:/ /shared-data
```

7. Verify:

```bash
df -h
```

8. Server 1:

```bash
cd /shared-data
echo "Hello from Server-1" > file1.txt
touch students.txt
```

9. Server 2:

```bash
cd /shared-data
ls
```

You should see the shared files.

## Automatic mount at boot (trainer option)

```text
fs-xxxxxxxx:/ /shared-data efs defaults,_netdev 0 0
```

Save it in `/etc/fstab`, then:

```bash
sudo mount -a
```
