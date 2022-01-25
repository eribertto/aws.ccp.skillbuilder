Module 6 security

Tuesday, January 25, 2022

3:35 PM

Learning objectives

In this module, you will learn how to:

Explain the benefits of the shared responsibility model.

Describe multi-factor authentication (MFA).

Differentiate between the AWS Identity and Access Management (IAM) security
levels.

Explain the main benefits of AWS Organizations.

Describe security policies at a basic level.

Summarize the benefits of compliance with AWS.

Explain additional AWS security services at a basic level.

Shared responsibility model

![Machine generated alternative text: AWS Shared Responsibilitv Model Customer 
Responsible for security "in" the cloud AWS Responsible for security "of" the
cloud Customer Data Platform, applications, identity and access management 
Operating system, network and firewall configuration Client-side encrypt Compute
AWS global torage r-side data encryption Foundation Services ata Regions Edge
locations Network traffic protection Networking
](https://lh5.googleusercontent.com/dsceavO6s38F5QYhfq6gw8NdeoZGSejGcj-r-g2T7Roq_bl0VwOvqEAJookWYd1wzpeItrNXIuIgH-2CJzt3nD9ek4sfY_sNvBxNFgqEStkY4VMVGwpa6BPakcxP1t_K72emPbvu)

Shared responsibility model

When it comes to securing your business on AWS, it's important to ask the
question: Who is ultimately responsible for the security? Is it A: You, the
customer? or B: AWS? And the correct answer is: yes. Both. Both are ultimately
responsible for making sure that you are secure.

Now, if there's any security experts watching this right now you're probably
shaking your head saying you can't have two different entities with the ultimate
responsibility over a single object. That's not security, that's wishful
thinking. At AWS, we agree completely. But for us, we don't look at your
environment as a single object. Instead we see it as a collection of parts that
build on each other. AWS is responsible for the security of some of the objects.
Responsible 100% for those. The others, you are responsible 100% for their
security. This is what's known as the shared responsibility model.

It's no different than securing a house. The builder constructed the house with
four walls and a door. It's their responsibility to make sure the walls are
strong and the doors are solid. It's your responsibility, the homeowner, to
close and lock the doors.

It really is that simple on AWS as well. Take EC2, for instance. EC2 lives in a
physical building, a data center that must be secured. It has a network and a
hypervisor that supports your instances and their individual operating systems.
On top of that operating system, you have your application, and that supports
your data. So for EC2 and every service AWS offers, there's a similar stack of
parts that build on top of each other. AWS is 100% responsible for some, you are
responsible for the others.

So, starting with the physical layer. This is iron and concrete and fences and
security guards. Someone has to own the concrete. Someone has to staff the
physical perimeter, 24/7. This is AWS. On top of the physical layer we have our
network and our hypervisor. Now, I'm not gonna go into details on how this is
all secured, but basically we have reinvented those technologies to make them
faster, stronger, tamper-proof.

But you don't have to just take our word for it. We have numerous third party
auditors who have gone through the code and the way we build our infrastructure,
and can provide the right documentation you need for your security compliance
structures. Now, on top of all that, on EC2, you now get to pick what operating
system you want to run.

This is the magic dividing line that separates our responsibility. AWS'
responsibility and your responsibility. This is your operating system. You're
100% in charge of this. AWS does not have any backdoor into your system here.
You and you alone have the only encryption key to log onto the root of this OS
or to create any user accounts there. I mean, no more than a construction
company would keep copies of your front door key, AWS cannot enter your
operating system. And here's a hint. If someone from AWS calls and asks you for
your OS key, it is not AWS.

Now that means your operations team is 100% responsible for keeping the
operating system patched. If AWS discovers there are some new vulnerabilities in
your version of Windows, let's say, we can certainly notify your account owner
but we cannot deploy a patch. This is a really good thing for your security.
This means no one can deploy anything that might break your system without your
team being the ones that do it. Now, on top of that OS, you can run whatever
applications you want. You own them. You maintain them.

Which takes us to the most important part of the stack, your data. Data. This is
always your domain to control. And sometimes you might want to have your data
open for everyone to see, like pictures on a retail website. Other times like
banking or healthcare, yeah, not so much, not so much. AWS provides everyone
with the tool set they need for their data to open it up to some authorized
individuals, to everyone, to just a single person under specific conditions, or
even lock it down so no one can access it. Plus, the ability to have ubiquitous
encryption. That way even if you accidentally left your front door open, all
anyone would see is unreadable encrypted content.

The AWS shared responsibility model is about making sure both sides understand
exactly what tasks are ours. Basically, AWS is responsible for the security of
the cloud and you are responsible for the security in the cloud. Together, you
have an environment you can trust.

Shared responsibility model

Throughout this course, you have learned about a variety of resources that you
can create in the AWS Cloud. These resources include Amazon EC2 instances,
Amazon S3 buckets, and Amazon RDS databases. Who is responsible for keeping
these resources secure: you (the customer) or AWS?

The answer is both. The reason is that you do not treat your AWS environment as
a single object. Rather, you treat the environment as a collection of parts that
build upon each other. AWS is responsible for some parts of your environment and
you (the customer) are responsible for other parts. This concept is known as the
shared responsibility model.

The shared responsibility model divides into customer responsibilities (commonly
referred to as “security in the cloud”) and AWS responsibilities (commonly
referred to as “security of the cloud”).

You can think of this model as being similar to the division of responsibilities
between a homeowner and a homebuilder. The builder (AWS) is responsible for
constructing your house and ensuring that it is solidly built. As the homeowner
(the customer), it is your responsibility to secure everything in the house by
ensuring that the doors are closed and locked.

![Machine generated alternative text: Shared res onsibili mode Customer 
Responsible for security •in" the cloud AWS Responsible for security •of' the
cloud Data Application Operating System Hypervisor Network Physical
](https://lh4.googleusercontent.com/GF6Jnx8_H-9RiqY1xkj_WLvugu5jti2U6_lZW5Y7S5KWANasXgAIAmwBQeYGtDNYCcpYItP7KdCsaNsraRmQ5vyVzTYA7m20Q1sICvu7HROtkbHvFSZR7T0SQLhTHSmF4qN9GbaP)

User permissions and access

In the coffee shop, every employee has an identity. They come into work in the
morning and they'd log into the system to clock in, use the registers and manage
the systems, running the coffee shop, day to day. We have the cash registers,
the computers helping run the whole operation. Each person has unique access to
these systems based on who they are.

If I have Rudy at the register taking orders and Blaine in the back, checking on
the inventory levels on the computer, they have two different logins and two
different sets of permissions. Rudy can run the cash register, but if he went to
log into the inventory system, he wouldn't be allowed to do that.

You will want to scope your users permissions in AWS in a similar way. When you
create an AWS account, you are given what is called the root account user. This
root user is the owner of the AWS account and has permission to do anything they
want inside of that account. This is like being the owner of the coffee shop.

In this situation, let's say I am the owner of the coffee shop. I can come into
the shop, use my credentials to work the register, work the inventory system or
any other system in the coffee shop. I cannot be restricted. With the AWS root
user, you can access and control any resource in the account. You can spin up
databases, EC2 instances, blockchain services, or literally whatever you want.
Because that user is so powerful, we recommend that as soon as you create an AWS
account and log in with your root user, you turn on multi-factor authentication,
or MFA, to ensure that you need not only the email and password, but also a
randomized token to log in.

That is great. But even with MFA turned on, in reality you don't want to use the
root user for everything. I, as the coffee shop owner, don't give my level of
access to all employees. Rudy on the cash register cannot access the inventory
system, remember? You control access in a granular way by using the AWS service,
AWS Identity and Access Management, or IAM.

In IAM, you can create IAM users. When you create an IAM user, by default, it
has no permissions. The user can't even log into the AWS account at first, it
has absolutely zero permissions. It can not launch an EC2 instance. It can not
create an S3 bucket. Nothing. You have to explicitly give the user permission to
do anything in that account. Remember, by default, all actions are denied. You
have to explicitly allow any action done by any user. You give people access
only to what they need and nothing else. This idea is called the least privilege
principle.

The way that you grant or deny permission is to associate what is called an IAM
policy to an IAM user. An IAM policy is a JSON document that describes what API
calls a user can or cannot make. Let's look at this quick example. In this
example, you can see we have a permission statement that has the effect as
Allow, the action as s3:ListBucket. And the resource is a unique ID for an S3
bucket. So if I attach this policy to a user and that user could view the bucket
"coffee_shop_reports" but perform no other action in this account. There were
only two potential options for the effect on any policy. Either allow or deny.
For action, you can list any AWS API call and for resource, you would list what
AWS resource that specific API call is for. Now, as a business person, you
wouldn't need to write these policies, but they are used all over in your AWS
accounts.

One way to make it easier to manage your users and their permissions is to
organize them into IAM groups. Groups are, well, they are groupings of users.
You can attach a policy to a group and all of the users in that group will have
those permissions. If you have a bunch of cashiers in the coffee shop, instead
of individually granting them all access to the register. Instead, you can grant
all cashiers access then just add each individual cashier to the group. Same
idea with groups in IAM.

All right, so far with IAM, you have the root user, they can do anything. You
have users which can be organized into groups. And you also have policies which
are documents that describe permissions that you can then attach to users or
groups. There is one other major identity in IAM, and it's called a role.

To understand the idea of roles, let's think about the coffee shop. As we know,
Blaine works in the shop and depending on the staffing of the shop day to day,
he might work the register or the inventory system or he might be the one
cleaning up at the end of the day with access to no systems. I, as the owner,
have the authority to assign these different roles to Blaine. His
responsibilities and access are variable and change from day to day. Just
because he worked on tracking inventory in the system yesterday, doesn't mean
that he should be at any time. His role at work changes and is temporary in
nature. The same type of idea exists in AWS. You can create identities in AWS
that are**called roles**.

Roles have associated permissions that allow or deny specific actions. And these
roles can be assumed for temporary amounts of time. It is similar to a user, but
has no username and password. Instead, it is an identity that you can assume to
gain access to temporary permissions. You use roles to temporarily grant access
to AWS resources, to users, external identities, applications, and even other
AWS services. When an identity assumes a role, it abandons all of the previous
permissions that it has and it assumes the permissions of that role.

You can actually avoid creating IAM users for every person in your organization
by federating users into your account. This means that they could use their
regular corporate credentials to log into AWS by mapping their corporate
identities to IAM roles. AWS IAM authentication and authorization as a service.

AWS root account

![Machine generated alternative text: AWS account root user When you first
create an AWS account, you begin with an identity known as the root user.  The
root user is accessed by signing in with the email address and password that you
used to create your AWS account You can think of the root user as being similar
to the owner of the coffee shop. It has complete access to all the AWS services
and resources in the account Create an AWS account.  This establishes your root
user identity.  Create your first IAM user and give it permissions to create
other users.  Log in as the new IAM user and continue to create other users. 
Only access the root user for a limited number of tasks.
](https://lh5.googleusercontent.com/8vk40FU8EmmoLc87RpuevhoUgMgo5d4rMFw42xVt94hjEKGnDarWTMeVnVgvOlpk5-2cf7IzTFjISJXWEL8bJasTdvHN_k9iECNF8t8nYyrcwsh4GCOzyncAxa9v8vsxtaT4Bk-G)

Aws organizations

Suppose that your company has multiple AWS accounts. You can use AWS
Organizations to consolidate and manage multiple AWS accounts within a central
location.

When you create an organization, AWS Organizations automatically creates a root,
which is the parent container for all the accounts in your organization.

In AWS Organizations, you can centrally control permissions for the accounts in
your organization by using service control policies (SCPs). SCPs enable you to
place restrictions on the**AWS services, resources**, and**individual API
actions** that users and roles in each account can access.

Organizational units

In AWS Organizations, you can group accounts into organizational units (OUs) to
make it easier to manage accounts with similar business or security
requirements. When you apply a policy to an OU, all the accounts in the OU
automatically inherit the permissions specified in the policy.

By organizing separate accounts into OUs, you can more easily isolate workloads
or applications that have specific security requirements. For instance, if your
company has accounts that can access only the AWS services that meet certain
regulatory requirements, you can put these accounts into one OU. Then, you can
attach a policy to the OU that blocks access to all other AWS services that do
not meet the regulatory requirements.

Root organizational unit

![Machine generated alternative text: AWS l: Finance AWS 2: Step 1 Root AWS
account 3: HR AWS 4: Legal Imagine that your company has separate AWS accounts
for the finance, information technology (IT), human resources (HR), and legal
departments. You decide to consolidate these accounts into a single organization
so that you can administer them from a central location. When you create the
organization, this establishes the In designing your organization, you consider
the business, security, and regulatory needs of each department. You use this
information to decide which departments group together in OUs\_ 2 3
](https://lh5.googleusercontent.com/I-oYQiwjiIoLjyk9feqY6087fKf1hAoyj5VjD6CgawWYuFe7pDod9aISNJxiWFpgNPJ7lWU6XoASHtaCyNpKLZh4ULCeLgHMu8jetjEbphEGztORMF50FjPrQCgYnJXicxt7cNwH)

![Machine generated alternative text: AWS account 1: Finance AWS account 2: IT 
Step 2 Root AWS account 3: HR AWS account The finance and IT departments have
requirements that do not overlap with those of any other department. You bring
these accounts into your organization to take advantage of benefits such as
consolidated billing, but you do not place them into any OUs\_ 2 3
](https://lh6.googleusercontent.com/bUHwWD-j0XM1fOiDo8carHdMQBzRE45KBy_v-FVg7pAl4FK_8wZx0HpXGdXp3n-l3cmh1HHdYJ22iTk2NzKcWB6dh746BPRfFN_yABPXZI-Irz1K7dRMXSeRK-3W26F7Rp3C8-mP)

![Machine generated alternative text: AWS account 1: AWS account 2: Step 3 Root 
OU AWS account 3: AVE account 4: The HR and legal departments need to access the
same AWS services and resources, so you place them into an OU together. Placing
them into an OU enables you to attach policies that apply to both the HR and
legal departments' AWS accounts.  2 3
](https://lh4.googleusercontent.com/iOem2dJbcAlZunUPehruKKvVIIWNuGt8q83wqMpMYQDx3KsF8SNVpUpQp0xlBbXyIkdMQtJJk4PJtmoulCR-du-NURokDfiR4QXqTGxVs-MYubeeoQ3WrXZqeX8RWkZZYUesaI13)

AWS compliance

For every industry, there are specific standards that need to be upheld, and you
will be audited or inspected to ensure that you have met those standards. For
example, for a coffee shop, the health inspector will come by and check that
everything is up to code and sanitary. Similarly, you could be audited for taxes
to see that you have run the back office correctly and have followed the law.
You rely on documentation, records and inspections to pass audits and compliance
checks as they come along.

You'll need to devise a similar way to meet compliance and auditing in AWS.
Depending on what types of solutions you host on AWS, you will need to ensure
that you are up to compliance for whatever standards and regulations your
business is specifically held to. If you run software that deals with consumer
data in the EU, you would need to make sure that you're in compliance with GDPR,
or if you run healthcare applications in the US you will need to design your
architectures to meet HIPAA compliance requirements.

Whatever your compliance need is, you'll need some tools to be able to collect
documents, records and inspect your AWS environment to check if you meet the
compliance regulations that you're under. The first thing to note is, AWS has
already built out data center infrastructure and networking following industry
best practices for security, and as an AWS customer, you inherit all the best
practices of AWS policies, architecture, and operational processes.

AWS complies with a long list of assurance programs that you can find online.
This means that segments of your compliance have already been completed, and you
can focus on meeting compliance within your own architectures that you build on
top of AWS. The next thing to know in regards to compliance and AWS, is that the
Region you choose to operate out of, might help you meet compliance regulations.
If you can only legally store data in the country that the data is from, you can
choose a Region that makes sense for you and AWS will not automatically
replicate data across Regions.

You also should be very aware of the fact that you own your data in AWS. As
shown in the AWS shared responsibility model, you have complete control over the
data that you store in AWS. You can employ multiple different encryption
mechanisms to keep your data safe, and that varies from service to service. So,
if you need specific standards for data storage, you can devise a way to either
reach those requirements by building it yourself on top of AWS or using the
features that already exist in many services. For a lot of services, enabling
data protection is a configuration setting on the resource.

AWS also offers multiple whitepapers and documents that you can download and use
for compliance reports. Since you aren't running the data center yourself, you
can essentially request that AWS provides you with documentation proving that
they are following best practices for security and compliance.

One place you can access these documents is through a service called AWS
Artifact. With AWS Artifact, you can gain access to compliance reports done by
third parties who have validated a wide range of compliance standards. Check out
the AWS Compliance Center in order to find compliance information all in one
place. It will show you compliance enabling services as well as documentation
like the AWS Risk and Security Whitepaper, which you should read to ensure that
you understand security and compliance with AWS.

To know if you are compliant in AWS, please remember that we follow a shared
responsibility. The underlying platform is secure and AWS can provide
documentation on what types of compliance requirements they meet, through
services like AWS Artifact and whitepapers. But, beyond that, what you build on
AWS is up to you. You control the architecture of your applications and the
solutions you build, and they need to be built with compliance, security, and
the shared responsibility model in mind.

Distributed Denial of Service attacks (DDOS)

D-D-o-S, DDoS, the distributed denial-of-service. It's an attack on your
enterprise's infrastructure, and you've heard of it. Your security team might
have written a plan for it, and you know that many businesses have been
devastated by it. But what exactly is it, and more importantly, how can you
defend against it?

Now to be clear, this is a 14-hour discussion to really understand it all, but
you need to at least know the fundamentals of how the attacks are carried out,
and how AWS can automatically defend your infrastructure from these crippling
assaults. Now we don't have a lot of time to cover all this, and the clock
starts now. The objective of a DDoS attack is to shut down your application's
ability to function by overwhelming the system to the point it can no longer
operate.

In normal operations, your application takes requests from customers and returns
results. In a DDoS attack, the bad actor tries to overwhelm the capacity of your
application, basically to deny anyone your services. But a single machine
attacking your application has no hope of providing enough of an attack by
itself, so the distributed part is that the attack leverages other machines
around the internet to unknowingly attack your infrastructure. The bad actor
creates an army of zombie bots, brainlessly assaulting your enterprise. The key
to a good attack, and I call it that when I should call it powerful. I mean,
it's definitely chaotic evil, but the key is to have the assault commander do
the smallest amount of work needed, and have the targeted victim receive an
unbearable load of resulting work they must process through.

So let me cherry-pick a few specific attack examples that work really well. The
UDP flood. It is based on the helpful parts of the internet, like the National
Weather Service. Now anyone can send a small request to the Weather Service, and
ask, "Give me weather," and in return, the Weather Service's fleet of machines
will send back a massive amount of weather telemetry, forecasts, updates, lots
of stuff. So the attack here is simple. The bad actor sends a simple request,
give me weather. But it gives a fake return address on the request, your return
address. So now the Weather Service very happily floods your server with
megabytes of rain forecasts, and your system could be brought to a standstill,
just sorting through the information it never wanted in the first place. Now
that is one example of half a dozen low-level, brute force attacks, all designed
to exhaust your network.

Some attacks are much more sophisticated, like the HTTP level attacks, which
look like normal customers asking for normal things like complicated product
searches over and over and over, all coming from an army of zombified bot
machines. They ask for so much attention that regular customers can't get in.

They even try horrible tricks like the Slowloris attack. Mm-hmm. Imagine
standing in line at the coffee shop, when someone in front of you takes seven
minutes to order their whatever it is they're ordering, and you don't get to
order until they finish and get out of your way. Well, Slowloris attack is the
exact same thing. Instead of a normal connection, I would like to place an
order, the attacker pretends to have a terribly slow connection. You get the
picture. Meanwhile, your production servers are standing there waiting for the
customer to finish their request so they can dash off and return the result. But
until they get the entire packet, they can't move on to the next thread, the
next customer. A few Slowloris attackers can exhaust the capacity of your entire
front end with almost no effort at all. I could go on monologuing for hours just
talking about the elegantly evil architecture of these attacks, but we are on
the clock here, and it is time to stop these attacks cold. And here's the cool
solution: You already know the solution.

Everything we've been talking about over this entire course is not only good
architecture, but it also helps solve almost all DDoS attack vectors with zero
additional effort or cost. First attack, the low level network attacks like the
UDP floods. Solution, security groups. The security groups only allow in proper
request traffic. Things like weather reports use an entirely different protocol
than the ones your customers use. Not on the list, you don't get to talk to the
server. And what's more, security groups operate at the AWS network level, not
at the EC2 instance level, like an operating system firewall might.

So massive attacks like UDP floods or reflection attacks just get shrugged off
by the scale of the entire AWS Regions capacity, not your individual EC2's
capacity. This is a case where our size is a huge advantage in your protection.
I won't say it's impossible to overwhelm AWS, but the scale it would take, it
would be too expensive for these bad actors. Slowloris attacks? Look at our
elastic load balancer. Because the ELB handles the http traffic request first,
so it waits until the entire message, no matter how fast or slow, is complete
before sending it over to the front end web server. I mean, sure, you can try to
overwhelm it, but remember how the ELB is scalable and how it runs at the region
level?

To overwhelm ELB, you would once again have to overwhelm the entire AWS region.
It's not theoretically impossible, but too massively expensive for anyone to
pull off. For the sharpest, most sophisticated attacks, AWS also offers
specialized defense tools called AWS Shield with AWS WAF. AWS WAF uses a web
application firewall to filter incoming traffic for the signatures of bad
actors. It has extensive machine learning capabilities, and can recognize new
threats as they evolve and proactively help defend your system against an
ever-growing list of destructive vectors.

All right, that's it, the clock is almost up. The takeaway is a well-architected
system is already defended against most attacks. And by using AWS Shield
Advanced, you can turn AWS into your partner against DDoS attacks. Oh, oh.

Other security services

With all the comings and goings on in your coffee shop, you'll want to increase
security to your coffee beans, equipment, and even money in the till. For your
beans, this could be when they're sitting in your store room, or even when
you're transporting them between shops. After all, we don't want unwanted
visitors with access to our coffee beans, or even running off with precious
equipment.

To start off, let's chat about how you can secure your coffee beans, or your
data whether it's at rest, or in transit. For our beans, the simple way to do it
would be to lock the door when we'd leave at night. That's the notion of
encryption, which is securing a message or data in a way that can only be
accessed by authorized parties. Non-authorized parties are therefore less likely
to be able to access the message. Or not able to access it at all. Think of it
as that key and door example. If you have the key, you can unlock the door. But
if you don't, then you cannot unlock that door.

At AWS, this comes in two variations. Encryption at rest and encryption in
transit. By at rest, we mean when your data is idle. It's just being stored and
not moving. For example, server-side encryption at rest is enabled on all
DynamoDB table data. And that helps prevent unauthorized access. DynamoDB's
encryption at rest also integrates with AWS KMS, or Key Management Service, for
managing the encryption key that is used to encrypt your tables. That's the key
for your door, remember? And without it, you won't be able to access your data.
So make sure to keep it safe.

Similarly, in-transit means that the data is traveling between, say A and B.
Where A is the AWS service, and B could be a client accessing the service. Or
even another AWS service itself. For example, let's say we have a Redshift
instance running. And we want to connect it with a SQL client. We use secure
sockets layer, or SSL connections to encrypt data, and we can use service
certificates to validate, and authorize a client. This means that data is
protected when passing between Redshift, and our client. And this functionality
exists in numerous other AWS services such as SQS, S3, RDS, and many more.

But speaking of other services, the next service we want to highlight is called
Amazon Inspector. Inspector helps to improve security, and compliance of your
AWS deployed applications by running an automated security assessment against
your infrastructure. Specifically, it helps to check on deviations of security
best practices, exposure of EC2 instances, vulnerabilities, and so forth. The
service consists of three parts a network configuration reachability piece, an
Amazon agent, which can be installed an EC2 instances, and a security assessment
service that brings them all together. To use it, you configure Inspector
options, run the service, out pops a list of potential security issues. The
resulting findings are displayed in the Amazon Inspector console, and they are
presented with a detailed description of the security issue, and a
recommendation on how to fix it. Additionally, you can retrieve findings through
an API. So as to go towards the best practice of performing remediation to fix
issues.

Another service dimension is our threat detection offering known as Amazon
GuardDuty. It analyzes continuous streams of metadata generated from your
account, and network activity found on AWS CloudTrail events, Amazon VPC Flow
Logs, and DNS logs. It uses integrated threat intelligence such as known
malicious IP addresses, anomaly detection, and machine learning to identify
threats more accurately. The best part is that it runs independently from your
other AWS services. So it won't affect performance or availability of your
existing infrastructure, and workloads.

They are so many other security services like Advanced Shield and Security Hub.
So please check out the Resources section to learn more. Thanks for following
along.


