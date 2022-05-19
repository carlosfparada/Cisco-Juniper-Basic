# POC-30-05-2022


- Presentation: Automation motivations and AAP basics
- Create an Execution Environment (EE)
- Create Inventory with Cisco/Juniper nodes
    - PoC Inventory
    - Groups: cisco_sw, cisco_rtr, juniper_sw, juniper_rtr
    - Hosts: cisco_sw1, cisco_rtr1, juniper_sw1, juniper_rtr1
        - add: 
            ---
            ansible_host: xxx.xxx.xxx.xxx
            ansible_network_os: ios
            ansible_connection: network_cli

    - Hosts: juniper-1, juniper-1
        - add: 
            ---
            ansible_host: xxx.xxx.xxx.xxx
            ansible_network_os: junos
            ansible_connection: httpapi

- Create Credentials for the managed nodes
    - set priviledge escalation
- Create a GIT Repository (GitHub) with a playbook 
- Create a Project
- Create a Template
- Run Job Template


1. basic_playbook.yml