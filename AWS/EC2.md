# EC2

```sh
# Connect to EC2 with SSH
ssh -i Certificate.pem ec2-user@PUBLIC_IP_OF_EC2_INSTANCE
```

**Availability zones** - groups of servers within specific region

**Security groups** are rules for inbound and outbound traffic attached to EC2

## Instance types

`m5.2xlarge`

- m - instance class
- 5 - generation
- 2xlarge - size of instance

## Purchasing options

- on-demand
- reserved for 1 or 3 years
- savings - commitment to use resources
- spot instances
- dedicated hosts - book entire physical server
- dedicated instances - no other customers will share hardware
- capacity reservations - reserve capacity in specific AZ for amount of time

## Spot instances

Spot fleet - set of spot instances + optional on-demand instances

### Strategies to allocate spot instances

- `lowestPrice`
- `diversified` - across all pools
- `capacityOptimized` - pool with optimal capacity for the number of instances
- `poolCapacityOptimized` - pools with highest capacity available at first, then - with lowest price

**Elastic IP** - fixed public IP

## ENI

**ENI** - virtual network card bound to specific AZ.

- 1 primary private IP and multiple private IPs
- 1 elastic IP per private IP
- one public IP
- security groups

## Placement groups

- Cluster
- Spread - up to 7 instances per AZ
- Partition - instanced combined in racks (hardware). Up to 7 partitions per AZ and 100 instances in total.

During **hibernate** RAM is dumped on encrypted root EBS volume

## AMI

**AMI** (amazon machine image) is bound to AZ.

## Storages

### **EBS drive** (Elastic block store)- network drive

- one instance per one EC2
- bound to AZ
- has limited GBs and IOPS

gp2, gp3, io1, io2, and Magnetic (Standard) can be used as boot volumes.

**io1/io2** volumes can be attached up to 16 EC2 instances.

### EFS - network file system

- shared between multiple AZs
- has standard-infrequent access (IA) for files that used rarely
- connects up to 100 EC2 instances.
