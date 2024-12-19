# cloud-test

## Setup

To set up environment:

```bash
python3 -m venv venv
source venv/bin/activate
export AWS_ACCESS_KEY_ID=...
export AWS_SECRET_ACCESS_KEY=...
git clone https://github.com/unixan-com/cloud-test
cd cloud-test
```

The inventory files (`static-inventory.yaml` and `dynamic.aws_ec2.yml`) should be modified for one's own resources.

## Running the playbooks

After setting up, then to create the example resources:

```bash
ansible-playbook ./create.yaml --inventory=static-inventory.yaml
```

And then to "discover" the resources, add cloud tags to them, and report an inventory:

```bash
ansible-playbook ./discover.yaml --inventory=dynamic.aws_ec2.yml
```
