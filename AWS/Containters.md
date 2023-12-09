# Containers

## Launch types

- EC2 - requires maintainance of EC2 instances. Runs ECS agent in order to register cluster
- Scaled by Auto scaling group scaling or **ECS cluster capacity provider**
- Fargate.
  - Requires task definition with specified CPU and RAM
  - Managed by ECS task role

It's recommended to use EFS for storage. S3 cannot be mounted as a file system.

## Scaling

ECS uses **AWS application auto scaling**

### Scaling metrics:

- CPU utilization
- memory
- request count per target

### Trigger scaling

- Target scaling - based on target value of CloudWatch metric
- Step - based on specified CloudWatch alarm
- Scheduled
