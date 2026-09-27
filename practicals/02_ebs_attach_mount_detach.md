# Practical 02 — EBS Attach, Format, Mount and Detach

## Goal

Create a 5 GB EBS volume, attach it to EC2, format it, mount it, write a file, unmount it, then detach it.

## AWS Console steps

1. EC2 → Elastic Block Store → Volumes → Create Volume.
2. Type: `gp3`.
3. Size: `5 GB`.
4. Availability Zone: same as the EC2 instance.
5. Create the volume.
6. Select the volume → Actions → Attach Volume.
7. Select the EC2 instance.
8. Trainer device example: `/dev/sdf`.

## On EC2

```bash
lsblk
```

On Nitro instances the volume commonly appears as `/dev/nvme1n1`.

## Format and mount

Partitioned version from the handbook:

```bash
sudo fdisk /dev/nvme1n1
sudo mkfs.xfs /dev/nvme1n1p1
sudo mkdir -p /data
sudo mount /dev/nvme1n1p1 /data
df -h
lsblk -f
echo "Hello AWS" | sudo tee /data/file1.txt
cat /data/file1.txt
```

Then:

```bash
sudo umount /data
```

Finally detach the volume from EC2 → Volumes.

## Persistent mount option

```bash
sudo blkid /dev/nvme1n1
```

Use the UUID in `/etc/fstab`, then test with:

```bash
sudo mount -a
```

## Key interview point

**Attach** = AWS connects the disk to EC2.  
**Mount** = Linux makes the filesystem accessible at a path.
