he Cash Register, one of the world's first self-auditing devices. The principle is simple: trust but verify. You have your entire store being run by a clerk that you trust, but you want to make sure that the cash in the drawer matches the actual sales. So every transaction then is recorded and tabulated. So at the end of the day, you know exactly what should be there. 

Being able to audit transactions in IT is a critical element in most compliance structures. But in a physical data center, there are so many places where a human can, even by accident, make changes without any record of that change getting recorded. At AWS, that problem goes away because everything is programmatic. 

Introducing AWS CloudTrail, the comprehensive API auditing tool. The engine is simple, every request made to AWS, it doesn't matter if it's to launch an EC2 instance, or add a row to a DynamoDB table, or change a user's permissions. Every request gets logged in the CloudTrail engine. The engine records exactly who made the request, which operator, when did they send the API call? Where were they? What was their IP address? And what was the response? Did something change? And what is the new state? Was the request denied? 

From an auditing perspective, well, this is fabulous. So imagine that you're dealing with an auditor who is checking to make sure that nobody from the outside can access your database. That's a good thing. Well, okay, you build a security group that locks out external traffic. But remember that a root-level administrator still has permissions to change those settings, right? 

Well, so how do you prove to the auditor that the security group settings never changed? The answer is CloudTrail. And then CloudTrail can save those logs indefinitely in secure S3 buckets. In addition, with tamper-proof methods like Vault Lock, you then can show absolute provenance of all of these critical security audit logs.