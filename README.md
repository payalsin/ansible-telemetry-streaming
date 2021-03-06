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
- got clone this repo (git clone https://github.com/payalsin/ansible-telemetry-streaming.git)
- Change your vars.yml file to reflect your environment
  - If avr is required set the avr_needed paramter to "yes", if not needed change it to "no"
- Run the playbook
  - ansible-playbook ts_workflow.yml
- JSON files used
  - ts_poller_and_listener_setup_declaration.json is used for basic TS setup
  - as3_ts_setup_declaration.json file is used to declare TS logging profiles etc. using AS3
    - If more logging profile are needed - you can refer to file as3_ts_setup_declaration_adv.json
 
  
## Pre-requisites
- BIG-IP 14.1+ version is being used
- If AVR is required to be configured make sure there is enough memory for the module to be enabled along with all the other BIG-IP modules that are provisioned in your environment
- The TS delaration is for Azure log analytics (modify it to use your own consumer), chnage your TS json file with the correct workspace ID and sharedkey
