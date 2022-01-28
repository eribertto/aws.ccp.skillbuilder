The Well-Architected Framework is designed to enable architects, developers, and users of AWS to build secure, high-performing, resilient, and efficient infrastructure for their applications. It's composed of five pillars, to ensure a consistent approach to reviewing and designing of architectures. 

The first pillar is Operational Excellence. And focuses on running and monitoring systems to deliver business value, and with that, continually improving processes and procedures. For example, automating changes with deployment pipelines, or responding to events that are triggered. 

Second, is Security. And as you know, security is priority number 1 at AWS. And this pillar exemplifies it, by checking integrity of data and, for example, protecting systems by using encryption. 

Third, is Reliability. And it focuses on recovery planning, such as recovery from an Amazon DynamoDB disruption. Or EC2 node failure, to how you handle change to meet business and customer demand. 

Fourth, is Performance Efficiency, and it entails using IT and computing resources efficiently. For example, using the right Amazon EC2 type, based on workload and memory requirements, to making informed decisions, to maintain efficiency as business needs evolve. 

Lastly, we have Cost Optimization. Which looks at optimizing full cost. This is controlling where money is spent. And, for example, checking if you have overestimated your EC2 server size. You can then lower cost by choosing a more cost-effective size. 

In the past, you'd need to evaluate these against your AWS infrastructure with the help of a Solutions Architect. Not that you can't, and aren't still encouraged to do that, but we listened to customer feedback, and decided to release the Framework as a self-service tool, the Well-Architected Tool. You can access it by the AWS Management Console. Create a workload and run it against your AWS account. To generate a report, showing areas that should be addressed. 

It kinda looks like a traffic light system, with green being A-okay captain, keep up the good work. Orange being, you should probably look into this 'cause there's room for improvement. And red being, okay, you should look at this, 'cause something is at risk. These are areas where the tool has detected potential issues, and it presents you with a plan on how to architect, using established best practices. It should be noted that you can always override these settings if the questions don't apply to your scenario. It's very customizable. Interesting side note, where I'm from, South Africa, we call traffic lights robots. 

If we take a look at the tool itself, you'll see something similar to the following screenshot. As I mentioned, we name our workload and that appears in Section One. Section Two shows you the pillars and drop-downs into the questions for each. Section Three shows the actual questions themselves, Four is the pillar and question stem. Five is a bit of background, and the recommendation. Six is the answer you provide with a toggle to designate whether the question is applicable or not. This is important as it affects your overall score. Oh, and I can't forget Section Seven, where you'll be presented with short videos explaining how to answer a particular question. 

Anyhow, that's the Well-Architected Framework and tool. Hope you have enjoyed learning how to evaluate your workloads.