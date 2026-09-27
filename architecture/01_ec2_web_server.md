# EC2 Web Server Architecture

```mermaid
flowchart LR
    U[User Browser] --> I[Internet] --> IGW[Internet Gateway]
    IGW --> RT[Public Route Table]
    RT --> EC2[Public EC2]
    EC2 --> HTTP[Apache / httpd :80]
```

**Flow:** User -> Internet -> IGW -> route table -> EC2 -> Apache.
