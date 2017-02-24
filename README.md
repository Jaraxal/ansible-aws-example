# ansible-aws-example

An example Ansible playbook for creating a security group and a specified number of instances on AWS.

This playbook uses the ec2 and ec2_group Ansible modules.  To learn more about configuration options with these modules:

- ec2: http://docs.ansible.com/ansible/ec2_module.html
- ec2_group:http://docs.ansible.com/ansible/ec2_group_module.html


## Configuration

Before running the playbook, you need to to make changes to a few of the configuration files.

### ansible.cfg

Edit `ansible.cfg` to specify the location of your AWS private key file.

### group_vars/all

Edit `group_vars/all` to set the following values:

- aws_access_key: **specify AWS Access Key**
- aws_secret_key: **specify AWS Secret Key**
- key_name: **specify private key name alias**
- aws_region: **specify aws region**
- vpc_id: **specify vpc id**
- cidr_ip: **specify cidr_ip**
- instance_type: **specify intance_type**

### inventory/hosts

Edit `inventory/hosts` to specify a custom Python path, such as Anaconda.

## Run Playbook

To run the playbook, you only need to use a single command

```bash
$ ansible-playbook -i inventory/hosts playbooks/aws-demo.yml
```
