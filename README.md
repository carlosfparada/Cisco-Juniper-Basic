# POC-30-05-2022

- DAY 1: Introduction and Environment Setup
- DAY 2: Cisco Use Cases
- DAY 3: Juniper Use Cases
- DAY 4: Q&As and Others

# DAY 1: Introduction and Environment Setup

- Presentation: Automation Motivations and AAP basics
- Create an Execution Environment (EE)
    - To support network collection 
- Create Inventory with Cisco and Juniper Nodes
    - PoC Inventory
    - Groups: cisco, cisco_sw, cisco_rtr, juniper, juniper_sw, juniper_rtr
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
            ansible_connection: netconf
- Create Credentials for the Managed Nodes
    - Set priviledge escalation
- Create a GIT Repository (GitHub) with a basic Playbook 
    - basic_playbook.yml
- Create a Project Pointing to GitHub (basic Playbook)
- Create a Template, with Project/Inventory/Credentials
- Run a Basic Job Template for all Management Nodes


# DAY 2: Cisco Use Cases

- Add/Run a Cisco Gather Facts Playbook/Template
    - cisco_gather_facts.yml
- Add/Run a Cisco VLAN Playbook/Template
    - cisco_config_vlan_survey.yml
- Add/Run a Survey to the VLAN Template
    - cisco_config_vlan_survey.yml
- Add/Run a Cisco multi-VLANs Playbook/Template
    - cisco_config_vlans.yml
- Add/Run a Cisco IP config Playbook/Template
    - cisco_config_ips.yml
- Add/Run a Cisco BGP config Playbook/Template
    - cisco_config_bgp.yml


# DAY 3: Juniper Use Cases

- Add/Run Juniper Gather Facts Playbook/Template
    - juniper_gather_facts.yml
- Add/Run Juniper multi-VLANs Playbook/Template
    - cisco_config_vlans.yml
- Add/Run Juniper IP config Playbook/Template
    - cisco_config_ips.yml
- Add/Run Juniper BGP config Playbook/Template
    - juniper_config_bgp.yml


# DAY 4: Q&As and Others

- Conclude Pending Exercices
- Extend any Particular Automations of Interest
- Questions and Answers Session


# Juniper commands

> show configuration vlans 
> show configuration interfaces
> show configuration interfaces em2
> configure
- set interfaces xe-0/0/0:2 unit 0 family inet
- delete interfaces xe-0/0/0:2 unit 0 family inet
- set interfaces xe-0/0/0:0 unit 0 family ethernet-switching
- delete interfaces em2 unit 0 family inet address 172.16.1.214/24
- set interfaces em2 unit 0 family inet address 172.16.1.214/24
- commit
