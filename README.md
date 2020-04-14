Amazon VPC Role for Ansible playbooks
=====================================

This role provides for setting up and tearing down micro(µ)-service vpcs on AWS.  Such vpcs feature public and private subnets with IAM integration. The role handles configuration of networking and computing resources on AWS.  Optionally, such VPCs can be utilized to enable EKS clusters to provide for distribution and scaling of µ-services. 

Requirements
------------

Following requirements have to be installed in order for this role to operate properly.

- boto3
- aws cli

Role Variables
--------------

A description of the settable variables for this role are mentioned here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Variables may also be sourced from other roles and/or the global scope (ie. hostvars, group vars, etc.).

| Table | Name | Description | Required [y/N] |
| ___: | :____ | :___________ | :_____________: |
| 1 | code_name | Short name for the VPC | Y | 
| 2 | aws_account_id | AWS account id | Y |
| 3 | aws_access_key | AWS access key | Y |
| 4 | aws_secret_key | AWS secret key | Y |
| 5 | eks_cluster | `yes/no`.  When yes, sets up a EKS cluster with the VPC. |  |



Instructions
------------

1.  Clone this repo into a `aws_vpc` folder
2.  Setup playbook as mentioned below with required variables.
3.  Run the playbook: `ansible-playbook < your playbook.yml filename >`

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: aws_vpc } # Setup VPC
         - { role: aws_vpc, eks_cluster: yes }  # Setup VPC and enable EKS cluster

License
-------

BSD

Author Information
------------------

This role has been authored by HC<hari.chinthalapale@verizon.net> for the purposes of demonstration only.  Any commercial use is prohibited without consent. 
