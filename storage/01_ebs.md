# 06 — EBS (Elastic Block Store)

## What is EBS?

**EBS = Elastic Block Store.** It provides persistent **block storage** for EC2 and behaves like a disk attached to a server.

**Remember:** EBS = Block / Disk.

## Snapshot

An **EBS Snapshot** is a point-in-time backup of an EBS volume. It can be used for recovery or to create another volume.

**Remember:** Snapshot = Backup of EBS.

## Attach vs Mount

- **Attach:** Connect the EBS volume to the EC2 instance at the AWS level.
- **Mount:** Make the filesystem accessible at a directory such as `/data` inside Linux.

## EBS practical — 5 GB gp3

The trainer lab uses:

- Size: **5 GB**
- Type: **gp3**
- Availability Zone: same as the EC2 instance
- Console device example: `/dev/sdf`
- On Nitro instances it commonly appears as `/dev/nvme1n1`

Flow:

```text
Create volume
→ Attach to EC2
→ lsblk
→ partition/format
→ mount
→ verify
→ create file
→ unmount
→ detach
```

## Commands used in the lab

```bash
lsblk
sudo fdisk /dev/nvme1n1
sudo mkfs.xfs /dev/nvme1n1p1
sudo mkdir -p /data
sudo mount /dev/nvme1n1p1 /data
df -h
lsblk -f
echo "Hello AWS" | sudo tee /data/file1.txt
cat /data/file1.txt
sudo umount /data
```

For a volume without a separate partition, the lab notes also show:

```bash
sudo mkfs.xfs /dev/nvme1n1
sudo mkdir -p /data
sudo mount /dev/nvme1n1 /data
```

## Persistent mount (lab note)

The training material uses `blkid` to get the UUID and then adds the UUID entry to `/etc/fstab`, followed by:

```bash
sudo mount -a
```

## Why unmount before detach?

The lab flow unmounts the filesystem before detaching so pending filesystem activity is safely closed.
