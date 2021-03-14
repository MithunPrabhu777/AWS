# AWS
AWS BASICS FOR BEGINNERS COURSE BY FREECODECAMP

Day - 1

AWS BASICS ReFerence by FREECODECAMP

AWS OVERVIEW

launched in 2002
offering in 2003
SQS pubic launch 2004
re-launch with s3,sqs,ec2 in 2006
amazon.com retail sites migrated to AWS 2010
sales of $1.57B 2015
Revenue of $25B 2018,$40B 2019

started with services like 30 to 40 well its more than 200 services.

Gartner Magic Quadrant 2019

AWS is leader in Infrastructure as Service over 48% share.

AWS Global Infrastructure

1.Region -us-east-1 2.Region eu-west-1 3. ap-southeast-2
   has lot of availabity zones . and each availability zones are composed of one or more data centers.

Each Regions will have atleast 2 availabilty zone.
Each region is completely independent,,one region doesnt affect another.
There are 25 regions all over the world.
every region is connected via high bandwidth.

Go and check aws global infrastructure page.

AWS PRICING

Fundamentals of AWS Pricing

1.compute  // amount of cpu ram and duration
2.Storage  //Quantity of data stored
3.Outbound Data Transfer  // Quantity of data transferred from all services and for traffic.

Go and check aws pricing page

there click on aws ec2 from compute section

Amazon EC2

Instances are virtual servers which contains os and applications.

Amazon Storage

Amazon s3

you can change region can see pricing in each region.

AWS pricing calculator
Estimate the cost for your architecture solution.


Day-2

amazon ec2 configure in some region
finally total pricing will come for particular configuration then u can estimate amount for configuration.

AWS free-tier account
search for aws free tier in browser
if you particular service you can filter by checking box
create a free account

u can put billing alarms ,,,if u put $5 it will give alarm u are approaching $5.
 for self study can use account type as personal and fill form.
 then payment information then security check.then verify code using sms.
 support plans free.i.e basic
 then u can signin
 sign in using root user email
 next
 password then signup
 then u will get AWS Management Console.
 
 
Create a billing alarm

In aws management console

aws services ----- put billing  ---- go to billing preferences ---- then check receive billing alerts ---  receive free-tier usage alerts  ---- put email-address  --- it will send alram to that email about billing --- save preferences.

u can search services ---  then u select in management and governance select amazon cloudwatch ---- its a performance monitoring tool. alarm will be triggered when service reaches threshhold. U can select region where ur application wants to configure in. For billing always have to choose US-East North Verginia.

then choose alarm ----- select a metric ----- go to billing ----  total estimated charge --USD by the way ---- select metric --- mention $1 --- get notification in that mail --- next ----- amazon sms is a service --- create a topic --- send a notification to ----- Billing notification ----  open in sns console.  ---  confirm subscription in your mail ---- subscription confirmed.

Alarm name ---- Billing_Alarm  ---- next  ---- create alarm.....!!!!! thats it...



IAM OVERVIEW

AWS Identity and Access Management Service(IAM)
where IAM policy will be applied to IAM user or IAM group. ///entity person or service.

IAM only tells allow only amazon ec2 u can mention it,,,so u cant access other services without IAM permission.

If it is IAM group its very difficult to manage or giving access to diffeerent users in group.


Day - 3


Authentication Methods

1.access key for api ---- to manage resources.
2.IAM user ---- password ---- AWS management console.

Create IAM user and Group

IAM policy ----- user
IAM policy  ----- IAM group
IAM policy  ----- Each(IAM) role.

AWS Management Console  ----- services -----security,Identity and compliances ---- IAM --- chane signin link ---- customize ----Account --- dct-cloudbeginner 
AWS Management Console  ----- services -----security,Identity and compliances ---- IAM --- Groups --- create a group ---- Admins --- next --- Attach policy --- Administrator Access  ---- next ---  create group ---- check admins  --- Permissions  --- Show Policy  ---- small json policy will get 

AWS Management Console  ----- services -----security,Identity and compliances ---- IAM --- Users ---- add user --- user name  --- access type ----- AWS managemenyt console --- custom password ----  next  --- add user to group ---- check on  admins group ----  next  ---- review --- user created.

now user can access AWS management console using sign-in link https://asbk.kfdn/flkmked/f.kemkf

logout from root user

run that url   ----  IAM user name  ---- password  --- signin --- AWS management console --- if u try to access billing service --- You get warning that  --- You need permission.

Amazon Virtual Private Cloud(VPC)

REGION ---  VPC  -----  AVALABILITY ZONE  ---- PUBLIC SUBNET  ----  EC2 INSTANCE 
                                          ---- Private subnet -----
                                          
EACH AVAILABILITY ZONE CONNECTED WITH ROUTER.

REGION HAS INTERNET GATEWAY.

YOU CAN ACCESS PUBLIC EC2 INSTANCE THROUGH INTERNET GATEWAY
BUT CAN ACCESS PRIVATE EC2 INSTANCE THROUGH PRIVATE KEY ONLY.

MULTIPLE VPCs  /// You can create multiple VPCs within each region.

Each VPC has different block of IP addresses.   ---  CIDR 172.31.0.0/16   --- Classless InterDomain Routing 

Each subnet has block of IP adresses from CIDR block.

AWS Management console --- Services ---- Networking and Content Delivery ----  VPC ---- U will get Resources by region --- Your VPCs ---- default VPCs is created --- available --- CIDR blocks  --- address space  ----  172.31.0.0/16 ---- associated.


AWS Management console --- Services ---- Networking and Content Delivery ----  VPC ---- U will get Resources by region ---  subnets  --- analyze.

Resources will change for each region. u may have less subnets in other region.

AWS Management console --- Services ---- Networking and Content Delivery ----  VPC ---- U will get Resources by region ---  route tables ---- routes/subnet associates

Day -4 

SECURITY GROUPS AND NETWORK ACL'S

Images are uploaded in issue section for more details.

stateful and stateless firewalls:

webserver will be protected by firewall from client.

             Dest Port:80           Src Port:65188
Web Server <------------- Firewall <-------------- Client
           -------------->         --------------->
           Src Port: 80            Dest Port:65188
(10.2.1.10)                                     (10.1.1.1)  


stateful firewall allows return traffic automatically.           //////  In AWS world Security Group is stateful firewall
stateless firewall checks for allow rule for both connections.   //////  Network ACL is stateless firewall.

Security Group                          Network ACL
1.stateful                              stateless
2.Evaluates all rules                   Processes rules in order.
3.with a group                          subnets associated with
4.operates at instance                  opearates at subnet level




