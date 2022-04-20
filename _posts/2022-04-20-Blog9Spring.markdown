---
layout: post
title:  "Blog 9 Spring"
date:   2022-04-20 08:08:51 -0700
categories: jekyll update
---
For our group project, We are using terraform and aws cli in order to create our infrastructure. My task this week was to get these installed on my own computer so that I can test my ansible code to see if it will deploy. Installing terrafrom was pretty simple on the bash terminal.

First I downloaded the zip file from https://www.terraform.io/downloads
After, I unzipped the file and moved it to /usr/local/bin/
Then I verified the install with terraform -help

The next step was to download and configure aws cli in order to execute the terraform code and create a key pair. 

First I had to log into my aws account and create a IAM user in order to get access keys.

After creating the account and getting the access keys, I downloaded aws cli and began the configuration. 

After typing aws configure, we are given 4 options that we need to input. 

AWS Access Key ID [None]: AKIAIOSFODNN7EXAMPLE
AWS Secret Access Key [None]: wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
Default region name [None]: us-west-2
Default output format [None]: json

After inputting these values, we are then able to gain access from the cli to create an ec2 and install our playbooks. This is basically a way to show the management console that we are authorized to access our account without logging in with the web browser. 
