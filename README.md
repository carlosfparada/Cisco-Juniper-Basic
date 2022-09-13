# POC-30-05-2022

- DAY 1: Introduction and Environment Setup
- DAY 2: Cisco Use Cases
- DAY 3: Juniper Use Cases
- DAY 4: Q&As and Others

# DAY 1: Introduction and Environment Setup

- Presentation: Automation Motivations and AAP basics
- Create Credentials for the Managed Nodes
    - Set priviledge escalation
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
- Create a Project Pointing to GitHub (basic Playbook)
- Create a GIT Repository (GitHub) with a basic Playbook 
    - basic_playbook.yml
- Create an Execution Environment (EE)
    - Create Credentials quay.io: rh_ee_cparada
    - To support network collection 
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

enter cli mode 
# cli

> show configuration vlans 
> show configuration interfaces
> show configuration interfaces em2

enter config mode
> configure

# show vlans

create/delete vlans
# set vlans Vlan_101 vlan-id 101
# delete vlans Vlan_101

create/delete vlans on an interface
# show interfaces
# delete interfaces xe-0/0/0:0
# set interfaces xe-0/0/0:0 unit 0 family inet

# set interfaces xe-0/0/0:0 unit 0 family ethernet-switching vlan members Vlan_101
# delete interfaces xe-0/0/0:0 unit 0 family ethernet-switching vlan members Vlan_101

create/delete inet config
# delete interfaces xe-0/0/0:0 unit 0 family inet
# set interfaces xe-0/0/0:0 unit 0 family inet

create/delete inet config
# delete interfaces xe-0/0/0:0 unit 0 family ethernet-switching
# set interfaces xe-0/0/0:0 unit 0 family ethernet-switching

set family to L2 (ethernet-switching) or IP (inet)
# set interfaces xe-0/0/0:2 unit 0 family inet
# delete interfaces xe-0/0/0:2 unit 0 family inet
# set interfaces xe-0/0/0:0 unit 0 family ethernet-switching

set/delete IPs
# delete interfaces em2 unit 0 family inet address 172.16.1.214/24
# set interfaces em2 unit 0 family inet address 172.16.1.214/24

show bgp commands
# show protocols bgp
# delete protocols bgp

always after any change
# commit
