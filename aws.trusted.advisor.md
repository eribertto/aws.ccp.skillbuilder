When running a business, you might need some advisers who can come in from the outside and say, hey, this process should be streamlined. Or, hey, I have some good tips on how to save money on your overhead. Or even, hey, I noticed I was able to waltz right in, go behind your cash register, and open the drawer without anyone noticing. Not good. 

The point I'm trying to make is, sometimes it's nice to have someone who knows the industry best practices, and knows what to look for, come in, and tell you what you need to change in order to run more efficiently, be more secure, or to save some money.

AWS has an automated advisor called AWS Trusted Advisor. This is a service that you can use in your AWS account that will evaluate your resources against five pillars. The pillars are cost optimization, performance, security, fault tolerance, and service limits. Trusted Advisor in real time runs through a series of checks for each pillar in your account, based on AWS best practices, and it compiles categorized items for you to look into, and you can view them directly in the AWS console. 

Some checks are free and are included in your AWS account, and others are available depending on the level of your support plan. Some examples of checks are, if you don't have multi-factor authentication turned on for your root user, it's going to let you know. If you have underutilized EC2 instances that might be able to be turned off in order to save money, or if you have EBS volumes that haven't been backed up in a reasonable amount of time, it will let you know that, too. To get a better idea, let's look at AWS Trusted Advisor in my own account. 

I'm already logged into the console, and I'm going to type in Trusted Advisor into the search. This brings me to the Trusted Advisor dashboard and I'm going to click on the Cost Optimization pillar first to view what it has found. You can see right away there are three levels of items it is showing me. There was the red circle, which means action recommended. The orange triangle, which means investigation recommended. And the green square, which means that there were no problems detected. 

Lucky for me, I don't have any red items for Cost Optimization, but I do have some orange items. Under Cost Optimization checks, I can read more about each check that Trusted Advisor ran. In this account, I do have some RDS instances that are idle, as well as some underutilized EC2 instances and EBS volumes. I could decide to scale these instances down vertically to save on cost, or if they aren't being used at all I could decide to delete those instances and those EBS volumes altogether. It would require some investigation for me to determine what to do here. 

Now, let's click on the Performance pillar. On this one, I don't have any warnings, but we can still read what checks Trusted Advisor performed. Like this one, for example, which checks for EBS volumes whose performance might've been affected by the throughput capability of the EC2 instance that it's attached to. 

Next, let's select the security pillar. In this demo account, you can see there are four alerts that are at the action recommended level. Trusted Advisor is trying to alert me, telling me I have weak password policies for IAM users, multi-factor authentication is not turned on for the root user, and there are security groups allowing public access to EC2 instances. All of these items are putting the resources in this account at risk, and should be dealt with as soon as possible. 

Now let's move on to fault tolerance. For this, there were a few things that are found to be insufficient. First, Trusted Advisor is telling me that there are EBS volumes without snapshots in this account. Remember, a snapshot is a backup. So without backups, if I had an EBS volume fail, I would lose that data. 

Another alert we have here is that my EC2 AZ balance is at the action recommended level. This means that my EC2 instances are not properly launched across AZs. So if one AZ has trouble, my application might incur an outage. Deploying across AZs would be the answer to this one.

Finally, let's check out Service Limits. This pillar will tell you when you are approaching or hitting AWS service limits. A lot of service limits are soft limits, meaning they are restrictions that can be lifted to some degree. It's good to know when you are approaching one of those limits, and when it's time to turn in a Support ticket with AWS to get them changed. In this account, I can see that I have five VPCs, which is the regional limit. So I've hit that specific service limit. 

Trusted Advisor can help point you in the right direction when it comes to the five pillars. You can set up email alerts that go out to billing, operations, and security contacts, as checks get run in your account. Make sure you have Trusted Advisor turned on so that you too can start taking action to optimize your AWS account.