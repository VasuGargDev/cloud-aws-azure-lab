AWS & IAM User || AWS to EC2 & SSH 

AWS acc and IAM user creation
EC2 create & lanuch
Connect from local using SSH






Creating AWS free tier acc.
https://aws.amazon.com/free/?trk=011f28e3-1dfa-405d-894f-3e05b14038a6&sc_channel=ps&trk=011f28e3-1dfa-405d-894f-3e05b14038a6&sc_channel=ps&ef_id=Cj0KCQjw-MDTBhCgARIsAKAkdlStxdq0FNwEgCDavBNXlGsZhHKeNLN6b_ExP7ApfLeYerBJ2IncR1IaAv5sEALw_wcB:G:s&s_kwcid=AL!4422!3!808712687436!p!!g!!aws%20account!23846236274!198027693282&gad_campaignid=23846236274&gclid=Cj0KCQjw-MDTBhCgARIsAKAkdlStxdq0FNwEgCDavBNXlGsZhHKeNLN6b_ExP7ApfLeYerBJ2IncR1IaAv5sEALw_wcB

https://us-east-1.signin.aws/platform/d-9067642ac7/login?workflowStateHandle=1e8cb763-78d0-4c2a-a6d9-43700443f129


These credentials for AWS console is different from the one just for the AWS profile


Account ID or alias: 
Account name:



AWS sign in to console Root user:
https://signin.aws.amazon.com/signin?redirect_uri=https%3A%2F%2Fus-east-1.console.aws.amazon.com%2Fbilling%2Fhome%3Fregion%3Dus-east-1%26state%3DhashArgs%2523%252Fbills%253Fyear%253D2026%2526month%253D3%26isauthcode%3Dtrue&client_id=arn%3Aaws%3Aiam%3A%3A934814114565%3Auser%2Fportal-aws-auth&forceMobileApp=0&oauth_region=us-east-1&code_challenge=0tluCSuuo0AF8bZ2bvpx08nnVhzOnly4qdfVHPUgTAE&code_challenge_method=SHA-256


Root user login using email and pass
Setup 2FA with MS Authenticator


Sign-in URL for IAM users in this account
https://<account ID>.signin.aws.amazon.com/console

Creating an IAM user: https://youtu.be/9YDB_q66ixI?si=9vTvLb6WqkX-2wpq&t=20


Console sign-in details
Email sign-in instructions 
Console sign-in URL
https://<account ID>.signin.aws.amazon.com/console
User name

Console password


NOTE:
Account ID: 
Region: ap-south-1 (Mumbai)









TRIVIA:
ROOT user is global at login
IAM user is region specific at login



NOTE:::

I was seeing access denied everywhere inside my newly created IAM user.


By default in AWS, a newly created IAM user starts with zero permissions. AWS enforces an "implicit deny" policy, meaning unless you explicitly attach a policy giving that user permission to view or manage resources, everything in the console will throw an Access Denied error.
To fix this, you need to log back in as the Root user and attach permissions to your new IAM user.
How to Fix "Access Denied" (Step-by-Step)
Step 1: Switch Back to the Root User
Log out of your IAM user session.
Go to the AWS Management Console login page and choose Root user.
Log in using your email address and password.

Step 2: Grant Permissions to the IAM User
Search for IAM in the top search bar and open the IAM Dashboard.
In the left navigation menu, click Users.
Click on the username of the IAM user you just created.
Under the Permissions tab, click Add permissions (on the right) $\rightarrow$ Add permissions from the dropdown.
Select Attach policies directly.

Step 3: Choose the Right Policy
Search for and select the appropriate policy based on what you want this user to do:
For Full Administrative Access (Recommended for personal learning/testing):
Search for AdministratorAccess.
Select the checkbox next to it. (This gives the IAM user complete control over services so you don't keep running into permission blocks while learning).
For Power User Access (Everything except IAM user/billing management):
Search for PowerUserAccess and select it.
For Specific Services Only (Least Privilege):
Search for service-specific policies like AmazonEC2FullAccess or AmazonS3FullAccess.
Click Next, review the selection, and click Add permissions.


I selected Power user access for now to avoid any unsolicited charges 

PowerUserAccess (
Why choose it:
Full Cloud Control: Gives you complete, unrestricted access to virtually all AWS services (EC2, VPC, S3, RDS, Lambda, CloudWatch, EKS, Terraform setups, etc.) needed for Linux administration and DevOps automation.
Safety Net: Prevents modifying IAM permissions, users, roles, or billing settings.


But I might have to switch to go back and give full Administrative Access    if I get error while connecting to this instance




---------------------------------------------------FIN---------------------------------------------



Creating an AWS EC2 instance:
STOP STRUGGLING VID:    https://www.youtube.com/live/yzhACp-7T54?si=iEKvzF2HMkql2_ee&t=108

AWS class1: https://www.youtube.com/live/NoHNQtRpEog?si=yG2R-7TOuHTPofpx&t=5388




Region: (Mumbai) ap-south-1
Account ID:

Launch instance:

Name: Pathnex


OS-
Amazon linux

Architecture-
64-bit (x86)

T.3 micro


Create key-pair (only first time) 
{
Name: Pathnex-ec2-key
Type: RSA
Private key format:
.pem (for use with open Ssh)
.ppk (PuTTY windows)
click”Create key pair” and save the file on finder
}

Make sure “Auto-assign public IP is enabled by default”


Network settings: {
leave most settings at default

Security group: Select existing security group > default VPC:
}

Configure storage 
1x 8 | gp3


File system: None


TOP RIGHT::
No. of instances :1 
ONE LAST TIME note down the IAM user account (ID) and region that you are creating this instance in

++++++
click LAUNCH INSTANCE

Successfully launched instance




Terminate(delete)/STOP instance :
https://www.youtube.com/live/7woKL0UZu3Q?si=KaZEjf-_tbLvZAb4&t=7932
(02:12:12)


=====
====
===
==
=

---------------------------------------------------FIN---------------------------------------------

Connect from local using SSH


TRIVIA:
4 Methods of Connecting to EC2 instance:::
EC2 Instance connect (error)
SSM Session manager (error)
Ssh Client ***
EC2 serial console (launched a console on the browser window but since we did not set a password it cannot run)


Annexure 1:
{
Now we have to connect to the instance
First trying to launch from AWS console UI using EC2 Instance connect
Connect using public IP | Username ec2-user (default)
we will be getting error- “Failed to connect to your instance
}

Follow the troubleshooting starting here: https://www.youtube.com/live/yzhACp-7T54?si=zWFzkvhyLgmLMKDr&t=364
(Timestamp 6:02)
….
“Will have to Enable SG (security group)”
Steps:
Go to instance
Actions > security > Modify IAM role
Select “Instance role” from the drop down and click “Update IAM role”

Annexure 1:
{
Still the same error…
}

Tried troubleshooting using GPT
Finally stopped this troubleshooting and directed to login using SSH is the solution

*** 34:00 Discussion on unsolicited charges on account
Advised to get a ticket raised with AWS support if unable to find charges!!!

Successful Trobleshooting ending here: https://www.youtube.com/live/yzhACp-7T54?si=Gwf8sb7No-xHaZsE&t=2193
(Timestamp 36:34)
…….
EC2
Left carousal 
Network and Security > Security groups > 
Click on the link of “default” security group>
Edit inbound rules > Add rule
Type: All traffic/SSH only
Source: My IP

SAVE RULE


NOW STEPS TO SSH INTO YOUR EC2
ssh -i “path where your KEY pair is saved” ec2-user@<public ipv4 of ec2 instance>


ERRORs while SSH into ec2 for the first time

ERROR: "Operation timed out"
Solution:
made sure I have alread set the inbound rule in security group
Edited the inbound rule from myIP to 0.0.0.0/0 just for the first time

vasugarg@Vasus-MacBook-Pro Downloads % ssh -i "pathnex-ec2-key.pem" ec2-user@3.111.42.51

ERROR:
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@         WARNING: UNPROTECTED PRIVATE KEY FILE!          @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
Permissions 0644 for 'pathnex-ec2-key.pem' are too open.
It is required that your private key files are NOT accessible by others.
This private key will be ignored.
Load key "pathnex-ec2-key.pem": bad permissions
ec2-user@3.111.42.51: Permission denied (publickey,gssapi-keyex,gssapi-with-mic).
Solution:
vasugarg@Vasus-MacBook-Pro Downloads % chmod 400 pathnex-ec2-key.pem

SUCCEXXFUL:::
vasugarg@Vasus-MacBook-Pro Downloads % ssh -i "pathnex-ec2-key.pem" ec2-user@3.111.42.51
   ,     #_
   ~\_  ####_        Amazon Linux 2023
  ~~  \_#####\
  ~~     \###|
  ~~       \#/ ___   https://aws.amazon.com/linux/amazon-linux-2023
   ~~       V~' '->
    ~~~         /
      ~~._.   _/
         _/ _/
       _/m/'
[ec2-user@ip-172-31-13-90 ~]$ 
