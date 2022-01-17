Amazon S3 storage classes

With Amazon S3, you pay only for what you use. You can choose from a range of storage classes to select a fit for your business and cost needs. When selecting an Amazon S3 storage class, consider these two factors:

How often you plan to retrieve your data
How available you need your data to be
To learn more about the Amazon S3 storage classes select the + symbol next to each category.

S3 standard:
Designed for frequently accessed data
Stores data in a minimum of three Availability Zones
S3 Standard provides high availability for objects. This makes it a good choice for a wide range of use cases, such as websites, content distribution, and data analytics. S3 Standard has a higher cost than other storage classes intended for infrequently accessed data and archival storage.

S3 standard Infrequent access
Ideal for infrequently accessed data
Similar to S3 Standard but has a lower storage price and higher retrieval price
S3 Standard-IA is ideal for data infrequently accessed but requires high availability when needed. Both S3 Standard and S3 Standard-IA store data in a minimum of three Availability Zones. S3 Standard-IA provides the same level of availability as S3 Standard but with a lower storage price and a higher retrieval price.

S3 One Zone IA
Stores data in a single Availability Zone
Has a lower storage price than S3 Standard-IA
Compared to S3 Standard and S3 Standard-IA, which store data in a minimum of three Availability Zones, S3 One Zone-IA stores data in a single Availability Zone. This makes it a good storage class to consider if the following conditions apply:

You want to save costs on storage.
You can easily reproduce your data in the event of an Availability Zone failure.

S3 Intelligent Tiering
Ideal for data with unknown or changing access patterns
Requires a small monthly monitoring and automation fee per object
In the S3 Intelligent-Tiering storage class, Amazon S3 monitors objects’ access patterns. If you haven’t accessed an object for 30 consecutive days, Amazon S3 automatically moves it to the infrequent access tier, S3 Standard-IA. If you access an object in the infrequent access tier, Amazon S3 automatically moves it to the frequent access tier, S3 Standard.

S3 Glacier
Low-cost storage designed for data archiving
Able to retrieve objects within a few minutes to hours
S3 Glacier is a low-cost storage class that is ideal for data archiving. For example, you might use this storage class to store archived customer records or older photos and video files.

S3 Glacier Deep Archive
Lowest-cost object storage class ideal for archiving
Able to retrieve objects within 12 hours
When deciding between Amazon S3 Glacier and Amazon S3 Glacier Deep Archive, consider how quickly you need to retrieve archived objects. You can retrieve objects stored in the S3 Glacier storage class within a few minutes to a few hours. By comparison, you can retrieve objects stored in the S3 Glacier Deep Archive storage class within 12 hours.