# 03 — EC2 Fundamentals

## EC2

**EC2 = Elastic Compute Cloud.** EC2 provides virtual servers called instances.

**Easy answer:** EC2 is a virtual server in AWS.

**Why use it?** To run applications/workloads without maintaining physical servers ourselves.

**Remember:** EC2 = Virtual Server.

## EC2 Instance Types / Families

Trainer revision uses these major families:

| Family | Simple purpose |
|---|---|
| T | General purpose |
| C | Compute optimized |
| R | Memory optimized |
| I | Storage optimized |
| G | GPU |

The training material also references `t2.micro` / `t3.micro` for lab instances.

## Purchasing / Pricing Models in the training material

- On-Demand
- Reserved
- Spot
- Dedicated Instance
- Dedicated Host

**Memory:** On-Demand = flexible, Reserved = long-term, Spot = lowest-cost interruptible option in the training revision, Dedicated Host = entire physical server.

## EC2 states

- Pending
- Running
- Stopping
- Stopped
- Terminated

## Key Pair

A key pair is used for secure EC2 authentication. The Linux practical uses a private key file such as `.pem` with SSH.

**Remember:** Key Pair = Secure EC2 login.

## SSH

**SSH = Secure Shell.** It is used for secure remote command-line access to a Linux EC2 instance, commonly on TCP port 22.

Example:

```bash
ssh -i My_key2.pem ec2-user@<PUBLIC-IP>
```

Meaning:

- `ssh` = Secure Shell
- `-i` = use the specified private key
- `My_key2.pem` = private key file
- `ec2-user` = lab Linux login user
- `<PUBLIC-IP>` = current public IPv4 address of the EC2 instance

Before use in the Windows/Git Bash lab:

```bash
chmod 400 My_key2.pem
```

## Public IP vs Private IP

- **Public IP:** Internet-routable address used when the network and security configuration allow Internet communication.
- **Private IP:** Internal VPC address used for communication within the VPC or connected private networks, subject to routing and security.

**Remember:** Public = Internet path. Private = internal networking.

## Elastic IP (EIP)

An **Elastic IP** is a static public IPv4 address that can be associated with supported AWS resources.

**Remember:** EIP = Static public IP.

## User Data

User Data is supplied at launch and can automate first-boot tasks such as installing and starting Apache.

**Remember:** User Data = first-boot automation.

## Stop vs Reboot vs Terminate

- **Stop:** shut down the instance so it can generally be started again.
- **Reboot:** restart the OS.
- **Terminate:** remove the instance.

**Remember:** Stop / Reboot / Terminate = Shutdown / Restart / Remove.
