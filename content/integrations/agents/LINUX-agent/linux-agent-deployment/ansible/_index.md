---
title: "Ansible"
#date: 2018-12-11
draft: false
tags: ["#ansible", "#integrations", "#configuration management"]
author: Lawrence Lane
---
Ansible is a configuration management tool that can be used to automate setup of servers, databases, and more. The Agent playbook will help get the Linux Agent up and running in your environment quickly.

## Configuration
1. Copy the [Agent playbook](https://github.com/netuitive/ansible-netuitive-agent) to your Ansible directory.  
```
cd /ansible
git clone https://github.com/netuitive/ansible-netuitive-agent.git
```
2. In the Agent playbook (`netuitive-agent.yml`), update the hosts setting to use desired host or inventory file.
3. Replace **apikey** in the `metricly_linux_api` setting with the API key from the Linux integration in your CloudWisdom account. To find this API key, point to the user account menu in the bottom left-hand corner of CloudWisdom and select Integrations. Your Linux API key is found next to the integration listed as _INFRASTRUCTURE_.
4. Run the Agent playbook, replacing `hosts-file-name` with the name of your hosts file.  
```
ansible-playbook -i hosts-file-name netuitive-agent.yml
```
