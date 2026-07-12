Kubernetes cluster on AWS, It utilizes EC2 machines to spawn self-managed cluster.

This is unified repository for task-tracker-fastapi-ec2-k8s project. It contains:

1. task-tracker-fastapi-ec2-k8s-iaac
    AWS infrastructure repository provisioning resources for the cluster using OpenTofu.

2. task-tracker-fastapi-ec2-k8s-ansible
    Configuration repository building kubernetes cluster on the AWS resources using Ansible.

EC2 instances, a VPC, multiple subnets, EC2 instances as nodes, EFS as a storage and a Load balancer for access outside.

VPC provides a isolated network for the cluster and multiple subnets ensure availability, EFS provides shared storage, and EC2 instances running kubernetes.
AWS Load Balancer provides safe public access to the applications hosted on the cluster.

Ansible does the task of preparing instances as kubernetes nodes, installing kubernetes packages, and bootstraping the cluster and joining the worker nodes.

This also hosts CI/CD pipelines for deploying the infrastructure and running the cluster using Github Actions.
