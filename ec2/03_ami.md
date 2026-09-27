# 05 — AMI (Amazon Machine Image)

## What is an AMI?

**AMI = Amazon Machine Image.** It is an EC2 launch template/blueprint containing the OS image and base configuration needed to launch an EC2 instance.

**Remember:** AMI = Blueprint.

## EC2 vs AMI

- **EC2:** the actual virtual server.
- **AMI:** the blueprint used to launch an EC2.

## Custom AMI practical from the trainer revision

1. Launch a RHEL 9 source EC2.
2. Install NGINX or another sample application.
3. Verify the server state and create `/opt/demo.txt` as the lab example.
4. EC2 → Instances → Actions → Image and templates → **Create image**.
5. Enter a name/description; trainer example: `rhel9-nginx-ami`.
6. Choose **No reboot** only when appropriate for the lab requirement.
7. Wait until the AMI is **Available**.
8. EC2 → AMIs → **Owned by me** → verify.
9. Launch another EC2 from the custom AMI.
10. Verify that the copied server state/application is present.

## Why create a custom AMI?

The trainer material lists uses such as standardized deployments, Auto Scaling, disaster recovery, golden images and faster provisioning.

**Memory:** Prepare once → launch many.
