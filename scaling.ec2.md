So we have a good idea now on the basics of EC2 and how it can help with any compute needs, like making coffee. Well, like metaphorically making coffee. The coffee represents the, whatever your instance is producing. The next thing we want to talk about is another major benefit of AWS, scalability and elasticity, or how capacity can grow and shrink, based on business needs.

Here is the on-prem data center dilemma. If your business is like 99% of all businesses out in the world, your customer workloads vary over time: perhaps over a simple 24 hour period, or you might have seasons where you're busy, and weeks that are not in demand. If you're building out a data center, the question is, what is the right amount of hardware to purchase? If you buy for the average amount, the average usage, you won't be wasting money on average. But when the peak loads come in, you won't have the hardware to service the customers, especially during the critical moments to expect to be making all your results.

Now, if you buy for the top max load, you might have happy customers, but for most of the year, you'll have idle resources. Which means your average utilization is very low. And I've seen data centers with average utilization under 10%, just out of fear of missing peak demand. So how do you solve the problem on-premises? Well the truth is, you can't. And here's where AWS changes the conversation entirely. 

What if you could provision your workload to exactly the demand, every hour, every day? Well, now you have happy customers, because they can always get the services they want. And you have a happy financial officer because they get the ROI your company needs. 

And here's how it works. Morgan is behind the counter. She's taking orders and we have a decoupled system. Morgan isn't doing all of the work here, so we need somebody making the drinks. It looks like Rudy's up. Now, the first problem I wanna solve, is the idea that we plan for a disaster. There's a great quote by Werner Vogels that says, "Everything fails all the time, so plan for failure and nothing fails." Or in other words, we ask ourselves what would happen if we lost our order taking instance? Well, we'd be out of business until we'd get another person to work the line, sorry, another instance up and running. 

So here is where AWS makes it really simple. Using the same programmatic method we used to create the original Morgan, we can create a second Morgan. So if one fails, we have another one already on the front line and taking orders. The customers never lose service. Well, don't forget about the backend. Let's make our processing instances redundant as well. So that gets our regular operating capacity. We now have a highly available system, with no single point of failure. And as long as the number of customers in line stays the same, we're good. But you know that's gonna change, right? So let's take a look at what's going to happen when we have a rush of customers, an increase in demand.

Scalability

Scalability involves beginning with only the resources you need and designing your architecture to automatically respond to changing demand by scaling out or in. As a result, you pay for only the resources you use. You don’t have to worry about a lack of computing capacity to meet your customers’ needs.

If you wanted the scaling process to happen automatically, which AWS service would you use? The AWS service that provides this functionality for Amazon EC2 instances is Amazon EC2 Auto Scaling.

Amazon EC2 Auto Scaling

If you’ve tried to access a website that wouldn’t load and frequently timed out, the website might have received more requests than it was able to handle. This situation is similar to waiting in a long line at a coffee shop, when there is only one barista present to take orders from customers.

Bar graph depicting demand and unused capacity over a 7-day period
Amazon EC2 Auto Scaling enables you to automatically add or remove Amazon EC2 instances in response to changing application demand. By automatically scaling your instances in and out as needed, you are able to maintain a greater sense of application availability.

Within Amazon EC2 Auto Scaling, you can use two approaches: dynamic scaling and predictive scaling.

Dynamic scaling responds to changing demand. 
Predictive scaling automatically schedules the right number of Amazon EC2 instances based on predicted demand.

TIP: To scale faster, you can use dynamic scaling and predictive scaling together.

Transcript 2:
Now there are two ways to handle growing demands. You can scale up, or scale out. Scaling up means adding more power to the machines that are running, which might make sense in a few cases but think about it. When you have an increase in customers, a bigger instance of Morgan really can't take a customer's order any faster. Because that depends on the customer more than Morgan.

"I'll take an espresso. Oh, wait, is that organic? Make it a soy latte? Actually, I don't know. Do you just have tea?"

What we need are, well, more Morgans. Customers? Oh, no! Looks like the processing instances are about to get overloaded. So let's scale them as well.

Obvious question is obvious. How come they are more order taking instances than order makers?

Well, in this case, the amount of work you can get done is still more than the order machines can send your way. You don't have a backlog. So no reason to add more worker instances. This is one of the great things about decoupling the system. You can end up with exactly the right amount of power for each part of your process, rather than over provisioning to solve a separate problem. Okay, looks like we just cleared that rush.

Now here is where AWS really makes a difference to your business. All these extra workers that are sitting around idle, if you don't need them, send them home or stop the instances. Amazon EC2 Auto Scaling. Adds instances based on demand and then decommissions instances when they are no longer needed. This means that every minute of the day, you always have the correct number of instances. Happy customers. Happy CFO. Happy architecture.

Example: Amazon EC2 Auto Scaling

In the cloud, computing power is a programmatic resource, so you can take a more flexible approach to the issue of scaling. By adding Amazon EC2 Auto Scaling to an application, you can add new instances to the application when necessary and terminate them when no longer needed.

Suppose that you are preparing to launch an application on Amazon EC2 instances. When configuring the size of your Auto Scaling group, you might set the minimum number of Amazon EC2 instances at one. This means that at all times, there must be at least one Amazon EC2 instance running.

Diagram of an Amazon EC2 instances scaling in and out as part of an Auto Scaling group
When you create an Auto Scaling group, you can set the minimum number of Amazon EC2 instances. The minimum capacity is the number of Amazon EC2 instances that launch immediately after you have created the Auto Scaling group. In this example, the Auto Scaling group has a minimum capacity of one Amazon EC2 instance.



Next, you can set the desired capacity at two Amazon EC2 instances even though your application needs a minimum of a single Amazon EC2 instance to run.

If you do not specify the desired number of Amazon EC2 instances in an Auto Scaling group, the desired capacity defaults to your minimum capacity.

The third configuration that you can set in an Auto Scaling group is the maximum capacity. For example, you might configure the Auto Scaling group to scale out in response to increased demand, but only to a maximum of four Amazon EC2 instances.

Because Amazon EC2 Auto Scaling uses Amazon EC2 instances, you pay for only the instances you use, when you use them. You now have a cost-effective architecture that provides the best customer experience while reducing expenses.