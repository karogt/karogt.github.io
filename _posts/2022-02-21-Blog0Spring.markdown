---
layout: post
title:  "Blog 0 Spring"
date:   2022-02-08 08:53:51 -0700
categories: jekyll update
---
I've been working on our senior project and finding ways to implement the installation of the app with ansible. Currently I have set up the monitoring of the web server with prometheus, node exporter, and grafana. After testing locally and on an ec2, I can successfully monitor the web server but now I want to find a way to install the application as well within one command of the playbook. After installing python and pip, I was able to run the application locally as well and was able to see covid-19 information. 

	At first I had some syntax errors within my tasks where my spacing was not correct due to the systemd structure. After adding two spaces my playbook began running

	I then ran into an issue where ansible was not reading a role within my main.yml playbook. My current setup for the main.yml file is…

- name: run roles on ec2
  hosts: all
  become: true
  roles:
  - app
  - prometheus
  - node_exporter
  - grafana

However, the playbook will install all other roles without error, i discovered that because my playbook within my task directory was not named as main.yml, ansible skipped it. I solved the error by placing my roles within the main yml file for the application. 

