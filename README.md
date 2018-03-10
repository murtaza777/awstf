# AWS with Terraform
## Setup 
On Ubuntu 16
Perform as root

`python --version` -> 2.7.12

`apt-get update`

`apt install python-pip`

`pip install --upgrade pip`

`curl -O https://releases.hashicorp.com/terraform/0.11.2/terraform_0.11.2_linux_amd64.zipe`

`mkdir /bin/terraform`

`unzip terraform_0.11.2_linux_amd64.zip -d /bin/terraform`

`export PATH=$PATH:/bin/terraform`

`terraform --version`

`pip install awscli --upgrade`

`aws --version`

`apt-get update`

`apt-get install software-properties-common`

`apt-add-repository ppa:ansible/ansible`

`apt-get update`

`apt-get install ansible`

`ansible --version`

`ssh-keygen` -> ~/.ssh/kryptonite

`ssh-agent bash`

`ssh-add ~/.ssh/kryptonite`

`ssh-add -L`

`vi /etc/ansible/ansible.cfg` -> search /host , uncomment host_key_checking=False

`mkdir terransible`

`cd terransible`

## AWS - IAM and DNS Setup

In IAM create a new user _terransible_, give it programmatic access, add existing policies *AdministratorAccess* and download credentials.

In Route53, use an existing domain or register a new domain

Back on the user terminal (from the above setup) run

`aws configure --profile myprofile` -> Enter downloaded credentials, defualt region, format default None

To check the setup run

`aws ec2 describe-instances --profile myprofile`

To configure route53 run

`aws route53 create-reusable-delegation-set --caller-reference 1224 --profile myprofile` -> caller-reference is any 4 digit no, copy the response json into a file for later use

In Route53, go to registered domains, go to add or edit nameservers and add the servers obtained from the previous command
