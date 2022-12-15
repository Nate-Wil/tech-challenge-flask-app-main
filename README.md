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
```
There is a user data script that updates the instaces, preps the environment and starts the application. The application will start automatically once the ec2 instances are created. It will take a few minutes after the instances start for the application to be ready for testing. Once it is ready, we can test to see if it is working by using the IP of an instance and running several route commands on it. 

```<ip_address>:8000 # for instances
   <DNS_ADDRESS> # for Application Load Balancer
```   

[GET] /gtg

Simple healthcheck - returns HTTP 200 OK if everything is working
Empty return
[GET] /gtg?details

Advanced healthcheck - returns HTTP 200 OK if everything is working and some service details
JSON return
[POST] /candidate/str:name

Adds a new string (candidate name) to a list, returns HTTP 200 OK if working

JSON return

optional parameter ?party=

will assign to a political party

empty/unsupplied or ind: none/independent (default)
dem: democratic
rep: republican
will error if supplied with something other than the three parameters above

[GET] /candidate/str:name

Gets candidate name from the list, returns HTTP 200 OK and data
JSON return
[GET] /candidates

Gets list of all candidates from a list, returns HTTP 200 OK and data
JSON return
