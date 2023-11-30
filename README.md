# AWS-Route53
A website is hosted on AWS by using following resources:
*EC2 instance running a website
*ASG (Auto Scaling Group)
*ALB (Application Load Balancer)
*AWS Route 53
*ACM (AWS Certificate Manager)

## Auto Scaling Group
An Amazon EC2 Auto Scaling group (ASG) contains a collection of EC2 instances that share similar characteristics and are treated as a logical grouping for the purposes of fleet management and dynamic scaling.
* Launch Template - It is similar to a launch configuration, in that it specifies instance configuration information. It includes the ID of the Amazon Machine Image (AMI), the instance type, a key pair, security groups, and other parameters used to launch EC2 instances.
<img width="950" alt="launchtemplate" src="https://github.com/NavreetK/AWS-Route53/assets/46690891/df63d1b8-cdcb-46f5-b7c3-edcb84de023d">

In the screenshot below 2 New instances been created by using Launch Template of Master Server as a part of ASG.
<img width="950" alt="instaces" src="https://github.com/NavreetK/AWS-Route53/assets/46690891/2e82f229-c619-4081-96b6-d8ee18cd6b77">

The ASG is configured to have a maximum capacity of 4 and minimum of 2 instances, depending on the traffic more instances will be created.
<img width="960" alt="ASG" src="https://github.com/NavreetK/AWS-Route53/assets/46690891/30bbbdca-c9c6-4df4-b947-9970491bf644">

## Application Load Balancer
Elastic Load Balancing automatically distributes your incoming traffic across multiple targets, such as EC2 instances, containers, and IP addresses, in one or more Availability Zones.

* Target Group - Target groups route requests to individual registered targets, such as EC2 instances, using the protocol and port number that you specify. When you create each listener rule in your Load Balancer, you specify a target group and conditions. When a rule condition is met, traffic is forwarded to the corresponding target group.
<img width="960" alt="targetgroup" src="https://github.com/NavreetK/AWS-Route53/assets/46690891/95494c28-92ba-40b3-8c03-d748fd20d5da">

* Listener - A listener is a process that checks for connection requests.
* Listener Rule - The rules that you define for your listener determine how the load balancer routes requests to the targets in one or more target groups.
<img width="769" alt="listener" src="https://github.com/NavreetK/AWS-Route53/assets/46690891/99985ba2-a507-4e46-94fc-ff5bb7f6d361">

LOAD BALANCER is then created by using Target group and Listeners. It is attached to the EC2 instances and is configured with the SSL certificate created on AWS.
<img width="960" alt="LB" src="https://github.com/NavreetK/AWS-Route53/assets/46690891/872223bb-4eb5-457a-a246-4d1f7be9b0a6">

## Route 53
Before creating a certificate you have to registered your domain on Route53 along with hosted zone.
* Route 53 - Amazon Route 53 is a highly available and scalable Domain Name System (DNS) web service. Route 53 connects user requests to internet applications running on AWS or on-premises.
<img width="960" alt="registeredDomain" src="https://github.com/NavreetK/AWS-Route53/assets/46690891/dc202a49-3d6d-4643-957e-4d95b82c62c3">

* Hosted Zone - A hosted zone is analogous to a traditional DNS zone file; it represents a collection of records that can be managed together, belonging to a single parent domain name.
<img width="960" alt="hostedzones" src="https://github.com/NavreetK/AWS-Route53/assets/46690891/baa9d4b8-57b3-4eb7-881b-a729f2facde2">

* Records in hosted zone:
<img width="945" alt="records" src="https://github.com/NavreetK/AWS-Route53/assets/46690891/1af8299e-aeb1-4515-9cf1-4cf1e4b360e3">

* SSL Certificate - SSL/TLS certificates allow web browsers to identify and establish encrypted network connections to web sites using the SSL/TLS protocol.
<img width="960" alt="certificate" src="https://github.com/NavreetK/AWS-Route53/assets/46690891/1a36a8d0-769d-476f-b3af-6c0920408fd8">

Once SSL certificate is created and attached to Load Balancer and Hosted Zone your website is ready and can be accessed by using domain - "ns99dev.link"
## FINAL RESULT
<img width="945" alt="finalapp" src="https://github.com/NavreetK/AWS-Route53/assets/46690891/ee1ef891-c1f1-4793-ac4a-7bc060231b21">


  

