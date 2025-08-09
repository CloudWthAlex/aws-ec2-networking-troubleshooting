# Detailed Project Documentation

## Problem Statement
Customer reported:
- Two EC2 instances in same VPC (10.0.0.0/16)
- Same subnet and configurations
- Instance A couldn't reach internet
- Instance B could reach internet
- Question about using 12.0.0.0/16 for new VPC

## Investigation Steps

### Task 1: Environment Analysis
1. Verified both instances were in same VPC/subnet
2. Compared networking configurations:
   - Instance A: Only private IP (10.0.10.10)
   - Instance B: Both private (10.0.10.11) and public IP
3. Checked route tables - both had default route to IGW

### Task 2: SSH Connectivity Test
1. Attempted SSH to both instances:
   - Success: Instance B via public IP
   - Failed: Instance A (no public IP)
2. Confirmed private IPs can't be accessed outside VPC

### Task 3: CIDR Range Analysis
Researched RFC 1918 private address ranges:
- Recommended against using public ranges (12.0.0.0/16) because:
  1. Potential routing conflicts
  2. Security risks
  3. AWS best practices recommend private ranges

## Solution Implemented
1. Enabled auto-assign public IP for Instance A
2. Verified internet connectivity
3. Provided customer documentation on:
   - Public/private IP differences
   - VPC CIDR selection best practices
