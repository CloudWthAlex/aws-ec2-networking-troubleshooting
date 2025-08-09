# AWS EC2 Networking Troubleshooting Project

## Project Overview
Investigated why two EC2 instances in the same VPC had different internet connectivity:
- Instance A: No internet access (only private IP)
- Instance B: Internet access (had public IP)

## Key Findings
1. **Public vs Private IPs**: 
   - Instance B had both public and private IPs
   - Instance A only had a private IP
2. **SSH Connectivity**:
   - Could only SSH to Instance B using its public IP
3. **VPC CIDR Recommendation**:
   - Advised against using public IP ranges (12.0.0.0/16) for VPCs
   - Explained potential routing conflicts

## Screenshots

### Instance A Configuration
![Instance A Details](images/instance-a-details.png)

### Instance B Configuration
![Instance B Details](images/instance-b-details.png)

### SSH Connection
![SSH Connection](images/ssh-connection.png)

## Lessons Learned
1. Importance of public IP assignment for internet access
2. OSI model concepts applied to AWS networking
3. Proper VPC CIDR selection best practices
