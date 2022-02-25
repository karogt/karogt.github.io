---
layout: post
title:  "Blog 2 Spring"
date:   2022-02-26 09:55:51 -0700
categories: jekyll update
---

Blog 2

This week I was able to work out why grafana was not showing my provisioned data sources and dashboard. I had discovered a line within my ansible script that was not properly transferring the files into the right directory.

- name: Copy grafana dashboard file
  copy: src=/home/ubuntu/roles/grafana/provisioning/dashboards/dashboard.yml dest=/etc/grafana/provisioning/dashboards

I had accidentally inputted datasource instead of dashboards for the bolded text, therefore I was never able to see my dashboard as grafana did not know where to look for it. 

After restarting grafana, I ran into a new issue where my datasource was not working and the dashboard was unpopulated. I found that the way I was telling grafana to look for the data was incorrect.

apiVersion: 1
 
datasources:
  - name: Prometheus
    type: prometheus
    access: proxy
    url: http://localhost:9090

For the access portion, I had originally placed direct instead of proxy. What that did was cause grafana to access directly from the server instead of the browser. I found that the proxy option worked and allowed me to access the datasource along with query errors in the Grafana logs.

After I worked out this error, I did a final test by setting up a fresh EC2 Instance and cloning my git repository to make sure there were no leftover configs that could cause me to have my configs working falsely. 
