# thoughtworks-project
thoughtworks infrastructure problem for interview process

Thinky thinks so far


[The Dev Team are ready for] a limited release (with reduced availability and reliability requirements) 

[You should] design and create the training and production environments:

You need to create two environments; one for training and one for production. You should prepare the production environments for the limited release.

Plan for the scale out during fully public release; worldwide use, available 24/7, sub­ second response times, [tolerate] single server failures

provide scripts/documentation to enable us to build the environments ourselves very easily. We will use VirtualBox, VMWare or EC2 (your choice).

[Use] Free/Libre/Open Source software (FLOSS). We request that you use Linux. 
You should deploy the static assets to a web server and the .war file to a separate application server. 
The app (companyNews) uses Prevayler for persistence

remember: working software over documentation! - Commented IaC, read me
usability, ease of use, automation - Keep manual interaction to a minimum
think about the security implications, or measures to take to ensure it is safe - usernames, passwords, encryption, keys, state, patching 
All environments:

- I will use EC2 - Reason
- I will not attempt to configure the Java app - Reason
- I will not attempt to configure Prevayler - Reason

For the Training environment:

- Assuming no performance requirements
- Deploy to one region
- No CDN or special Geo DNS LB

For the Production (Limited Release) environment:

- The Limited Release needs to be performant worldwide
- I will recommend they deploy to multiple regions and use Geo DNS LB to tune the performance of dynamic pages
- I will recommend they use CDN to reduce transfer times of static content

Minimum Viable Product based on the requirements and constraints we know of - Keep It Simple Stupid
Infrastructure as Code - use automation tooling: Ansible and Terraform
Cloud agnostic - non native tooling, open source
Version Control - use Git
Immutability to support future availability requirements
Ephemeral infrastructure to support future availability requirements
Cost
Operational overhead

In order to keep things simple
I will assume a default AWS VPC configuration is already in place
I will keep scripting to a minimum
I will use Ansible for host configuration management
I will use an S3 backend for storing state and secrets
I will use Terraform for infrastructure provisioning

I will build the environments using EC2 as per compute constraints
I will control the configuration of the EC2 hosts using Ansible

The client will receive a set of files which can be imported into their version control system
The client will need to execute from a machine which will need to have tools setup
The environment setup will first create a terraform backend for state and secrets - python?
The client will need to configure the AWS credentials they want to use
The client will need to configure the machine type they want to use - defaults can apply
I will use an AWS ubuntu image
I will assume a default AWS VPC configuration is already in place
