# Uturn-Tech-Challenge-2022 Nate Wilson
# 

This is an AWS infrastructure built in Terraform to deploy a python flask app that works with DynamoDB to hold data. It runs in a VPC with an internet gateway to 2 public subnets in two separate availability zones through a load balancer.

The script to test it is found in root folder ".." -  To access it from SSH you will have to sudo -s to assume root privileges to "cd" into the "tech-challenge-flask-app-main.git" directory.  

To run the script use the command

```python3 ./test_candidates.py <ip/dns address>:8000```

The script should produce 4 checks

```
good to go passed 
insert passed
verification passed
candidate list passed

There is a user data script that updates the instaces, preps the environment and starts the application. The application will start automatically once the ec2 instances are created. It will take a few minutes after the instances start for the application to be ready for testing. Once it is ready, we can test to see if it is working. 
