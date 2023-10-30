![image](https://github.com/rajdyp/rajdyp.github.io/assets/15313631/f77d1632-f658-4505-9f0d-c874bfb83dc9)

```yaml
Workflow:

Sign in to AWS Console
│
├── Choose a Region
│
├── Create S3 bucket
│
├── Create (EC2) IAM role
│   │
│   ├── AWS Service
│   │
│   └── EC2
│
├── Create VPC
│
├── Create subnets
│   │
│   ├── private subnets
│   │
│   ├── public subnets
│   │
│   └── db subnets
│
├── Create IGW
│   │
│   └── Attach to VPC
│
├── Create NAT gateway
│   │
│   ├── public subnet
│   │
│   └── Allocate Elastic IP
│
├── Create route table
│   │
│   ├── Add route
│   │
│   └── Explicit subnet associations
│
├── Create security group
│   │
│   ├── Inbound rules
│   │
│   └── Outbound rules (allow all traffic)
│
├── Create DB subnet group
│
├── Create database
│
├── Create EC2 instance
│   │
│   └── Create image (AMI) # for launch template
│
├── Create launch template # for auto scaling group
│   │
│   └── Select custom AMI
│
├── Create target group
│
├── Create load balancer
│   │
│   ├── Select load balancer type # Application Load Balancer | Network Load Balancer | Gateway Load Balancer
│   │
│   └── Select target group
│
├── Create Auto Scaling group
│   │
│   ├── Select target group (load balancer)
│   │
│   └── Configure group size and scaling policies
│
└── End
```

```yaml
Step 1: Sign in to AWS Console
```

```yaml
Step 2: Choose a Region
```

```yaml
Step 3: Create S3 bucket

| --> Go to Amazon S3 service
|    | --> `Create bucket`
|    |    | --> `Bucket name`
|    |    | --> `AWS Region`
|    |    | --> `Create bucket`
```

```yaml
Step 4: Create IAM EC2 instance role
| --> Go to IAM dashboard
|    | --> `Roles` > `Create role`
|    |    | --> Trusted entity type = `AWS Service`
|    |    | --> `EC2`
|    |    | --> Add permissions > AmazonS3ReadOnlyAccess and AmazonSSMManagedInstanceCore
|    |    | --> `Role name`
|    |    | --> `Create role`
```

## Networking and Security
![image](https://github.com/rajdyp/rajdyp.github.io/assets/15313631/a61c461e-b5b5-4162-a114-778363397c21)

```yaml
Step 5: Create Virtual Private Cloud (VPC)

| --> Go to VPC Dashboard
|    | --> `Create VPC`
|    |    | --> `VPC only`
|    |    | --> `VPC name`
|    |    | --> `CIDR range`
|    |    | --> `Create VPC`
```

```yaml
Step 6: Create Subnets
| --> On VPC Dashboard
|    | --> `Subnets` > `Create subnet`
|    |    | --> `Subnet name`
|    |    | --> `Availability Zone`
|    |    | --> `CIDR range`
|    |    | --> `Create subnet`

# 2 public subnets, 2 private subnets, 2 DB subnets
```

```yaml
Step 7: Create Internet Gateway # internet connectivity
| --> On VPC Dashboard
|    | --> `Internet gateways` > `Create internet gateway`
|    |    | --> `Internet gateway name` > `Create internet gateway`
|    | --> `Internet gateway ID`
|    |    | --> `Actions` > `Attach to VPC`
|    |    |     | --> Select `VPC` > `Attach internet gateway`
```

```yaml
Step 8: Create NAT Gateways*** # internet connectivity
| --> On VPC Dashboard
|    | --> `NAT gateways` > `Create NAT gateway`
|    |    | --> `NAT gateway name`
|    |    | --> Select `Subnet`    # public subnet
|    |    | --> `Allocate Elastic IP`
|    |    | --> `Create NAT gateway`

# for high availability, create NAT gateway in each private subnet
```

```yaml
Step 9: Create Route Tables
| --> On VPC Dashboard
|    | --> `Route tables` > `Create route table`
|    |    | --> `Route table name`
|    |    | --> Select `VPC` > `Create route table`
|    |    |    | --> `Routes` > `Edit routes`
|    |    |    |    | --> `Add route` > Destination=`0.0.0.0/0` > Target=`Internet gateway` > `Save changes`
|    |    |    | --> `Subnet associations` > `Edit subnet associations`
|    |    |    |    | --> Select `Public subnets` > `Save associations`
|    | -->`Route tables` > `Create route table`
|    |    | --> `Route table name`
|    |    | --> Select `VPC` > `Create route table`
|    |    |    | --> `Routes` > `Edit routes`
|    |    |    |    | --> `Add route` > Destination=`0.0.0.0/0` > Target=`NAT gateway` > `Save changes`
|    |    |    | --> `Subnet associations` > `Edit subnet associations`
|    |    |    |    | --> Select `Private subnet` > `Save associations`

# create route table for public subnets and private subnets
```

```yaml
Step 10: Create Security Groups
| --> On VPC Dashboard
|    | --> `Security groups` > `Create security group`
|    |    | --> `Security group name`
|    |    | --> `Description`
|    |    | --> Select `VPC`
|    |    | --> Inbound rules > `Add rule` > `Create security group`

# create security groups for internet facing LB, public instances, internal LB, private instance, DB instances
```

## DB tier
```yaml
Step 11: Create DB (RDS) Subnet Groups
| --> On RDS Dashboard
|    | --> `Subnet groups` > `Create DB Subnet group`
|    |    | --> `DB subnet group name`
|    |    | --> `Description`
|    |    | --> Select `VPC`
|    |    | --> Add subnets > `Availability Zones` > `Subnets` > `Create`
```

```yaml
Step 12: Database Deployment***
| --> On RDS Dashboard
|    | --> `Databases` > `Create database`
|    |    | --> `Security group name`
|    |    | --> `Description`
|    |    | --> Select `VPC`
|    |    | --> `Add rule` > Inbound rules > `Create security group`
```

## App tier
```yaml
Step 13: Create EC2 Instances
| --> On EC2 Dashboard
|    | --> `Instances` > `Launch instances`
|    |    | --> `Instance name`
|    |    | --> Select `Amazon Machine Image`
|    |    | --> Select `Instance type`
|    |    | --> `Create new key pair`
|    |    | --> Select `VPC`
|    |    | --> Select `Subnet`
|    |    | --> Select `Security groups`
|    |    | --> Select `IAM instance profile`
```

```yaml
Step 14: Create App Tier AMI for Autoscaling
| --> On EC2 Dashboard
|    | --> `Instances` > select `instance` > `Actions` > `Image and templates` > `Create image`
|    |    | --> `Image name`
|    |    | --> `Image description`
|    |    | --> `Create image`
```

```yaml
Step 15: Create Target Group
| --> On EC2 Dashboard
|    | --> `Target Groups` > `Create target group`
|    |    | --> Choose a target type = `Instances`
|    |    | --> `Target group name`
|    |    | --> Select `Protocol`:`Port`
|    |    | --> Select `VPC`
|    |    | --> Select `Health check protocol`
|    |    | --> Define `Health check path`
|    |    | --> `Create target group`
```

```yaml
Step 16: Create Internal Load Balancer
| --> On EC2 Dashboard
|    | --> `Load Balancers` > `Create load balancer`
|    |    | --> Application Load Balancer > `Create`
|    |    | --> `Load balancer name`
|    |    | --> Scheme = `Internal`
|    |    | --> Select `VPC`
|    |    | --> Select `Subnet`
|    |    | --> Select `Security groups`
|    |    | --> Listener > `Protocol`:`Port` > Default action = `app target group`
```

```yaml
Step 17: Create EC2 Launch Templates
| --> On EC2 Dashboard
|    | --> `Launch Templates` > `Create launch template`
|    |    | --> `Launch template name`
|    |    | --> My AMIs > Owned by me > Select `AMI`
|    |    | --> Select `Instance type`
|    |    | --> Select `Key pair name` # if applicable
|    |    | --> Select existing security group > Select `Security groups`
|    |    | --> Select `IAM instance profile`
|    |    | --> `Create launch template`
```

```yaml
Step 18: Create Auto Scaling Groups
| --> On EC2 Dashboard
|    | --> `Auto Scaling Groups` > `Create Auto Scaling group`
|    |    | --> `Auto Scaling group name`
|    |    | --> Select `app launch template`
|    |    | --> Select `VPC`
|    |    | --> Select `Availability Zones and subnets`
|    |    | --> Select `Attach to an existing load balancer`
|    |    | --> Select `Choose from your load balancer target group`
|    |    | --> Select `app load balancer target groups`
|    |    | --> Configure group size and scaling policies > `Desired capacity` > `Minimum capacity` > `Maximum capacity`
|    |    | --> `Create Auto Scaling group`
```

## Web tier
```yaml
Step 19: Create EC2 Instances
| --> On EC2 Dashboard
|    | --> `Instances` > `Launch instances`
|    |    | --> `Instance name`
|    |    | --> Select `Amazon Machine Image`
|    |    | --> Select `Instance type`
|    |    | --> `Create new key pair`
|    |    | --> Select `VPC`
|    |    | --> Select `Subnet`
|    |    | --> Auto-assign public IP = `Enable` # only in web tier
|    |    | --> Select `Security groups`
|    |    | --> Select `IAM instance profile`
```

```yaml
Step 20: Create Web Tier AMI for Autoscaling
| --> On EC2 Dashboard
|    | --> `Instances` > select `instance` > `Actions` > `Image and templates` > `Create image`
|    |    | --> `Image name`
|    |    | --> `Image description`
|    |    | --> `Create image`
```

```yaml
Step 21: Create Target Group
| --> On EC2 Dashboard
|    | --> `Target Groups` > `Create target group`
|    |    | --> Choose a target type = `Instances`
|    |    | --> `Target group name`
|    |    | --> Select `Protocol`:`Port`
|    |    | --> Select `VPC`
|    |    | --> Select `Health check protocol`
|    |    | --> Define `Health check path`
|    |    | --> `Create target group`
```

```yaml
Step 22: Create Public (Internet) Load Balancer
| --> On EC2 Dashboard
|    | --> `Load Balancers` > `Create load balancer`
|    |    | --> Application Load Balancer > `Create`
|    |    | --> `Load balancer name`
|    |    | --> Scheme = `Internet-facing`
|    |    | --> Select `VPC`
|    |    | --> Select `Subnet`
|    |    | --> Select `Security groups`
|    |    | --> Listener > `Protocol`:`Port` > Default action = `web target group`
```

```yaml
Step 23: Create EC2 Launch Templates
| --> On EC2 Dashboard
|    | --> `Launch Templates` > `Create launch template`
|    |    | --> `Launch template name`
|    |    | --> My AMIs > Owned by me > Select `AMI`
|    |    | --> Select `Instance type`
|    |    | --> Select `Key pair name` # if applicable
|    |    | --> Select existing security group > Select `Security groups`
|    |    | --> Select `IAM instance profile`
|    |    | --> `Create launch template`
```

```yaml
Step 24: Create Auto Scaling Groups
| --> On EC2 Dashboard
|    | --> `Auto Scaling Groups` > `Create Auto Scaling group`
|    |    | --> `Auto Scaling group name`
|    |    | --> Select `web launch template`
|    |    | --> Select `VPC`
|    |    | --> Select `Availability Zones and subnets`
|    |    | --> Select `Attach to an existing load balancer`
|    |    | --> Select `Choose from your load balancer target group`
|    |    | --> Select `web load balancer target groups`
|    |    | --> Configure group size and scaling policies > `Desired capacity` > `Minimum capacity` > `Maximum capacity`
|    |    | --> `Create Auto Scaling group`
```


















## temporary (will be deleted)

```yaml

Step 5: Launch EC2 Instances (Web Servers)

In the EC2 Dashboard, click "Launch Instances."
Select an Amazon Machine Image (AMI) based on your operating system and application needs.
Choose an instance type based on your performance requirements.
Configure network settings, including the VPC and security group you've created.
Review and launch the instance, creating or selecting an existing key pair for SSH access.


Step 6: Configure Load Balancers

In the EC2 Dashboard, go to "Load Balancers."
Click "Create Load Balancer" and choose the Application Load Balancer (ALB).
Configure the listeners (e.g., HTTP on port 80) and create a new target group to manage traffic to your web servers.
Associate your ALB with the public subnet you created earlier.


Step 7: Launch Application Servers

Similar to web servers, launch instances in the private subnet for your application servers.
Choose an appropriate AMI, instance type, and configure security groups.
Ensure these instances can communicate with the web servers and the database.


Step 8: Implement an RDS Database

In the RDS Dashboard, click "Create Database."
Choose the database engine you need (e.g., MySQL, PostgreSQL).
Configure the database details, such as the database instance class, storage, username, and password.
Under the "Network & Security" section, select the VPC and configure the security group to allow access only from the application servers.


Step 9: Set Up Auto Scaling

In the EC2 Dashboard, navigate to "Auto Scaling Groups."
Create a new Auto Scaling group for your web servers or application servers.
Configure scaling policies, such as scaling based on CPU utilization, and define the minimum and maximum number of instances.


Step 10: Enable Monitoring and Logging

In the CloudWatch Dashboard, set up alarms to monitor your resources, such as CPU utilization and response times.
Enable logging for your services, like web server access logs and database query logs.


Step 11: Implement Backup and Disaster Recovery

Configure automated backups for your RDS instance in the RDS Dashboard.
Create a backup retention policy to specify how long backups are kept.
Consider implementing Multi-AZ deployments for high availability and create read replicas for disaster recovery.


Step 12: Implement Security Best Practices

In the IAM Dashboard, set up IAM roles for your EC2 instances to grant them necessary permissions to AWS services.
Regularly update security patches on your EC2 instances using Systems Manager or other methods.
Consider enabling AWS Web Application Firewall (WAF) and AWS Shield for additional security.


Step 13: Test and Optimize

Continuously test your architecture for performance, security, and reliability.
Use AWS Cost Explorer to monitor costs and optimize resources for cost-efficiency.
This detailed guide provides step-by-step instructions for creating each component of a three-tier architecture in AWS using the AWS Management Console. Remember to refer to AWS documentation and adapt these steps to your specific use case and requirements.
```

### Supplementary
- [Hands-on workshop](https://catalog.us-east-1.prod.workshops.aws/workshops/85cd2bb2-7f79-4e96-bdee-8078e469752a/en-US)
- [GitHub](https://github.com/aws-samples/aws-three-tier-web-architecture-workshop)
