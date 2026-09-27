# Practical 08 — Create a Custom AMI

## Goal

Prepare one EC2 server and use it as the blueprint for launching another EC2 instance.

## Steps

1. Launch RHEL 9 source EC2.
2. Install NGINX or another sample application.
3. Verify the application/server state.
4. Create `/opt/demo.txt` as the trainer example.
5. EC2 → Instances → Actions → Image and templates → Create image.
6. Enter AMI name/description.
7. Wait for AMI **Available**.
8. EC2 → AMIs → Owned by me → verify.
9. Launch a new EC2 from the custom AMI.
10. Verify the application and copied server state.

**Memory:** AMI = Blueprint → prepare once → launch copies.
