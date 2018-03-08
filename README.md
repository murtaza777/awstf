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
