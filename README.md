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


AWS Public and Private Services

Image in local storage

Public Internet is connected with Amazon DynamoDB ,,,Amazon S3,,,,Amazon Route S3,,,, Amazon CloudFront and is connected to VPC through Internet Gateway.

Day - 5

If EC2 instance want to collect data from Amazon S3 then it will connect through internet gateway.and is protected by VPC(Private Cloud).

INSTALL AWS COMMAND LINE INTERFACE

Section - 2  ----   Amazon Elastic Compute Cloud(EC2)

This is one of the oldest service in AWS standing till today.(To launch virtual services)

Amazon EC2 Overview

There will be lot of ec2 instances in EC2 Host Server.
Instances are virtual server or virtual machine which contains application or website running and Operating System(Windows or Linux) and also contains certain amount of CPU,RAM,Drive Space and Network Interface Bandwidth.

EC2 Instance need a IP address.

EC2 hosts are managed by AWS.

Public,Private and Elastic IP addresses.

If instance is in Public Subnet that instance will get public IP address.

Public IP address:
1.Lost when instance is stopped.
2.Used in Public Subnets
3.No charge
4.Associated with private IP address on instance.

Private IP address:
1.Retained when instance stopped
2.Used in Public and Private Subnets

Elastic IP address:
1.Static Public IP address
2.You are charged if not used
3.Associated with private IP address on instance
4.Can be moved between instances and Elastic Network Adapters.


Public Subnets details can be get in issues in the form of image.

Private subnets will have Private IP for both instances.

(Network Access Translation Gateway) ----  forwards connections to internet.

Launching an Amazon EC2 instance

Amazon Machine Image(AMI) will generate EBS snapshot in Linux or Windows.

Instance Type:

Family              Type           vCPUs       Memory(GiB)
General Purpose     t2.micro       1           1
Compute optimized   c5n.large      2           5.25
Memory optimized    r5ad.large     2           16
Storage optimized   d2.xlarge      4           30.5
GPU instances       g2.2xlarge     8           15

AWS Management Console ---- Services ---- Compute ---- EC2 ----- Limits/AMIs/Launch Templates 

everything in the dashboard. try everything.

Launch Instance......   -----  choose a Amazon Machine Image(AMI)
1.RedHat Linux
2.SUSE Linux
3.Amazon Linux
4.Ubuntu Server
5.Microsoft Windows Server
6.Microsoft Windows with SQL server installed
                   Lot Of Options..............
                   
My AMIs --- you can create your own AMI
MarketPlace or u can use Community AMIs

Go to Quick Start and Choose -----  Amazon Linux 2 AMI --- select ---- Default is General Purpose /t2.micro  -----  free tier ---- Next configure ---- Add storage ---- By default it will create 8GB elastic Block Store having General Purpose SSD. ----- Next ----- Add Tag --- Dept --- Development --- now --- next configure security group ---  Name:Web Access ---- Review And Launch ---- Launch --------Create a new Key Pair ----  

Day - 6

Public key will genearated by AWS and private key should be we must download.Need to give private key when it is required.

Key pair name --- sydney-KP ---- download key pair --- launch instances --- view instances --- 

You can see that instance will have instance id etc etc,,,just analyze it..

You can monitor instance

-------------------------------

Connecting to Amazon EC2 Instance

so to check whether running instance is remote or not we can change region to singapore --- launch instance ---  Microsoft Windows Server 2019 Base --- t2.micro --- next -- security group --- Web-Access ---- review ---- launch --- create new key pair ---- keypairname: singapore-KP --- Download ---- Launch Instances --- 

Again change region to sydney --- instances --- connect ---- it will show command to be run on aws cli ---- chmod 400 Sydney-KP.pem ----- 

Go to Command Prompt ---- ls ----
it will list like
OLD       Sydney-KP.pem
chmod 400 Sydney-KP.pem    ---- succesfully
paste command seen in page 
It will ask are you sure you want to continue connecting (yes/no) -- yes

AMAZON LINUX 2 AMI WILL BE displayed...........................................

so we are logged innn to our instance------------ so we have done secure shell connection.

then run command  ---- sudo yum update -y
It will install all packages.

Back to AWS management console again change region to singapore.--connect it to windows instance --- then to linux instance.

Now we are going to learn how to connect from windows 2A instance.
now,get password for administrator. ---- choose file ---- singapore-KP.pem --- decrypt password --- use public DNS copy --- use RDP client --- 

PC name: add pc name

click on add        /////////////paste password u got from decrypting file
username: administartor
password: paste it here

continue

this is to connect to windows from his computer.

Now we are logging on to windows server using Amazon EC2.

He is located in australia but server instance working in singapore.

Download Putty  --- 64bit msi installer -- finish --- open puttygen from windows search --- we found key pair file for sydney --- open with --- notepad --- copy content----  save it as Sydney.kp.txt --- 

In puttygen --- load ---  all files --- sydney-KP --- save --- ok --- save private key --- save it as ppk file.-----------done.

Go to AWS managemeent console --- change region to sydney ----- copy DNS address from description board --- paste it in putty configuration --- in the begining specify ec2-user@DNS-naive

Because this is instance connected to aws console --- now go to auth --- browse -- ppk file --- so we are logged into amazon linux AMI.

Go to Actions ----instance state ---- terminate the instance ---- ***************------------ ALL DATA GONE

---------------------------------************--------------------

CREATE A WEBSITE USING USER DATA

This is the script we are going to launch websites using user data

yum update -y
yum install httpd -y
systemctl start httpd
systemctl enable httpd
cd /var/www/html
echo "This is a test page running on Apache on EC2 in the AWS cloud">index.html

# test with this command
curl http://169.254.269.354/latest/user-data


