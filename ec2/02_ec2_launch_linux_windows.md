# 04 — Launching EC2: Linux and Windows

## Linux EC2 lab flow

1. Open AWS Management Console → EC2.
2. Click **Launch Instance**.
3. Enter instance name, e.g. `aws-server1`.
4. Choose a Linux AMI; trainer material uses Red Hat Enterprise Linux (RHEL).
5. Choose the lab instance type, e.g. `t2.micro` or eligible `t3.micro`.
6. Select/create the key pair.
7. Choose VPC/subnet/Security Group; allow required access.
8. Review root EBS storage.
9. Launch the instance.
10. Wait for **Running** and lab status checks.
11. Connect using SSH/PuTTY.

## Default resources seen in the trainer launch exercise

Depending on the launch configuration, the lab notes show:

- Default VPC
- Default subnet
- Default Security Group
- Public IPv4 address
- Root EBS volume
- Network Interface (ENI)

## Windows EC2 lab flow

1. Open EC2 → **Launch Instance**.
2. Choose a Windows Server AMI.
3. Choose `t2.micro` in the trainer example.
4. Create/select a key pair (`.pem` in the example).
5. Allow RDP traffic for the lab.
6. Keep the trainer lab root volume example (8 GiB gp2).
7. Launch the instance.
8. EC2 → **Connect** → **Get Password** → choose the key file → **Decrypt Password**.
9. Download the Remote Desktop file and connect.
10. Use `Administrator` when prompted by the RDP client.

**Important:** The trainer notes use broad RDP access for the classroom exercise but explicitly warn that production environments should use more restrictive Security Group rules.

## Linux vs Windows access

| EC2 OS | Typical lab remote access | Port |
|---|---|---:|
| Linux | SSH | 22 |
| Windows | RDP | 3389 |
