```cloud computing```
Cloud Computing is the ***on*-*demand* *delivery*** of computer power, database storage, applications, and other **IT*** resources

`Characteristics`
**On-demand self service**,
**Broad network access**,
**Multi-tenancy and resource pooling**,
**Rapid elasticity and scalability**,
**Measured service**.

```example```
![](https://i.imgur.com/pXjfec3.png)
Guys as you can see in the Above Image there is a connection between the PC, tablet to the cloud which provides the **Storage*** on demand by the user.

```about```  
Through a cloud services platform with **pay**-**as**-**you**-**go** **pricing**.
We can ***provision exactly the  right type and size of computing*** resources we may needed, as many as we required, that to be almost instantly.

```AWS```   

![](https://i.imgur.com/YC1dBMm.png)
In the **Cloud market AWS is one of prominent player***, which owns and maintains the network-connected hardware required for these application services.

```WHY```
As Maintaining and owning a data center, cost you a lot. like owning of Hardware component like **GPU, SSD, CPU***. renting the place, electricity bill, maintaining them would cause a headache. so
to solve all the above problem the Cloud platform like AWS, Azure, Google cloud. provides the services you required on demand with the offer of ***pay-as-you-go***. 

```Usecase```
As many of us use Gmail which store our email in google cloud.
***Dropbox*** provides *cloud* *storage* *services*. [originally built on AWS](https://aws.amazon.com/solutions/case-studies/dropbox-s3/)
***NETFLIX*** provide *Video on demand*. [Built on AWS](https://aws.amazon.com/solutions/case-studies/innovators/netflix/)  

```Models of cloud```
***Private Cloud*** : Cloud services used by a single organization, not exposed to the public. **complete control**, **security for sensitive applications**, **meet specific business needs**. ex-[rackspace](https://www.rackspace.com/en-in)

***Public cloud*** : Cloud resources owned and operated by a third-party cloud service provider delivered over the internet.  ex-[AWS](https://aws.amazon.com/), [Azure](https://azure.microsoft.com/en-in),[Google](https://cloud.google.com/).

***Hybrid Cloud*** : Keep some servers on site and extend some capabilities to the cloud, **control over sensitive assets**, **Flexibility and cost effectiveness of the public cloud**. 

`advatage`
***CAPEX* for operational expense**,
**Benefit from massive economies of scale**,
**Stop guessing capacity**,
**Increase speed and agility**,
**Go global in minutes**.

`Problem solved`
**Flexibility**,
**Cost-Effectiveness**,
**Scalability**,
**Elasticity**,
**Agility**.
`AWS-MAP`
![](https://i.imgur.com/DwO0ons.png)
Above image shows the AWS Infrastructure Region.
So The question will be how to choose the region, 
it all depends on three major Factor:
***The governence rule***- Some government want the data to be local then you have to choose the local region.
***Service availability***- The AWS doesn't provide all its service to all the region, so choose the region if AWS of that region provide the service you needed.
***Proximity***- So to reduce lag between the customer and your application which means([providing low latency](https://www.mirrorfly.com/blog/what-is-low-latency/)) choose the region based on targeted user/customer region
***Pricing***- So each region has different pricing range.

`AWS Global services`
***Identity and Access Management***,
***Route 53(DNS service***,
***Web Application Firewall***.

`AWS Region-scoped services`
***[Amazon EC2](https://aws.amazon.com/ec2/) (IFaaS)***: 
Provide buildig block for cloud IT.
Provides networking, computers, data storage.
Highest level of flexibility.
easy parallel with traditional on premises IT.
[***Elastic Beanstalk](https://aws.amazon.com/elasticbeanstalk/) (PaaS)***:
Removes the need for your organization to manage the underlying infrastructure.
Focus on the deployment and management of your application.
[***Lambda](https://aws.amazon.com/lambda/) (FaaS)***, 
***[Rekognition](https://aws.amazon.com/rekognition) (SaaS)***.
  
`As-a-Services`
![](https://i.imgur.com/DCnzJKY.png)
Blue-Managed by local system
Orange-Managed by AWS