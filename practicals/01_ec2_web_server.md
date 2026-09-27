# Practical 01 — EC2 Web Server with Apache

## Goal

Launch a public Linux EC2, install Apache, create a simple webpage, and test access.

## EC2 launch

- RHEL 9 lab example
- `t3.micro` when appropriate for the lab
- Existing key pair
- Public subnet / public IPv4
- Security Group:
  - SSH TCP 22 from your IP
  - HTTP TCP 80 from `0.0.0.0/0`
  - HTTPS 443 only if HTTPS is configured

## SSH

```bash
cd /d/Downloads
ssh -i My_key2.pem ec2-user@<CURRENT-PUBLIC-IP>
```

## Install and start Apache

```bash
sudo dnf install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd
sudo systemctl status httpd --no-pager
```

## Create a test page

```bash
echo "<h1>Welcome Soumya to AWS</h1>" | sudo tee /var/www/html/index.html
curl http://localhost
```

Then open the current EC2 public IP in a browser using `http://`.

## Troubleshooting flow

```text
EC2 Running?
→ httpd installed?
→ httpd active?
→ listening on port 80?
→ SG HTTP 80?
→ Public IP?
→ Public route table → IGW?
→ curl localhost?
→ browser retest
```

## Common trainer errors

### `Unit httpd.service could not be found`

Apache is not installed. Install it.

### `inactive (dead)`

Apache is installed but stopped. Start it and check status.

### `curl localhost:80: Connection refused`

Nothing is listening on port 80; check Apache.

### Browser cannot open, but localhost works

Check Security Group 80, public IP, public route table → IGW, and use `http://` when HTTPS is not configured.

### `dnf ... → Killed`

The practical notes explain this as possible memory pressure on a small lab instance. The lab workaround is to add temporary swap or use a larger instance.
