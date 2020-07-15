# Ansible-Deploy telemetry streaming

Use the following ansible playbook to get started using telemetry streaming on BIG-IP. The playbook will perform the following tasks
- Grab the latest AS3 and TS versions
- Download the AS3 and TS packages and intall them on BIG-IP using a role
- Deploy AS3 and TS declarations on BIG-IP using a role
- If AVR logs are needed for TS then provision the BIG-IP AVR module and configure AVR to point to TS

## Run the playbook
Download the following roles from ansible galaxy
- ansible-galaxy install f5devcentral.f5app_services_package --force
- ansible-galaxy install f5devcentral.atc_deploy --force
- Change your vars.yml file
- Run the playbook
  - ansible-playbook ts_workflow.yml
  
