- [AWS](https://aws.amazon.com/)
  id:: 6463499e-9096-4ccf-8af2-96569e23c33b
  AKA Amazon Web Services
	- Documentation
		- Giving AWS Access to Freelancers
			- Create new users via IAM. Assign to a group (e.g. 1Freelancers) which has a policy (e.g. 1View_RDS-CW)
			- You can designate the ARN as * in the Policy Generator
			- Use AWS prebuilt policies eg ReadOnly ones
	- _By AWS Software_
		- [AWS Products](https://aws.amazon.com/products)
		  id:: 6463499e-7e3f-4d66-89b4-cf300a0dcda7
			- Meta
				- Amazon - Instance Network Configuration
				  collapsed:: true
					- To allow secure shell access from any IP address into the WordPress application, ensure that the "SSH Source" field is set to "0.0.0.0/0". The default setting for the template is set to "127.0.0.1/32" which disables remote SSH access; you must change this value to be able to SSH into the application server.
					- To allow public access from any IP address to the WordPress application, ensure that the "Application Source" field is set to "0.0.0.0/0". The default configuration is set to this, but if you would like to constrain access of the application to a specific IP range, please edit this value. Click "Next" to proceed.
			- _Frequently accessed links_
				- ((6544c9ef-05f1-41f8-8062-a6f5dc3cc6ad))
				- ((6463499e-bd2d-4c48-b05b-bdddeb7d8bba))
				- ((6463499e-42ab-4a58-8911-df6138dfee8f))
				- ((6457bcad-7919-46a4-a9c0-8bb0ddf40189))
			- Priority to learn
				- ((6620d4c0-1c5f-4f16-bfee-cf33e7cf5ffd))
			- All categories
			  [[2023-07-19 Wednesday]]
				- ### Analytics
				  id:: 64b7b95b-88f7-45f1-b190-6681ad28725b
				  collapsed:: true
					- Amazon Athena
					  collapsed:: true
					  Query data in S3 using SQL
						- {{embed ((64aec89f-45fa-4e04-92c7-6b5e98334647))}}
					- Amazon CloudSearch
					  Managed search service
					- Amazon DataZone (Preview)
					  Unlock data across organisational boundaries with built-in governance
					- Amazon EMR
					  collapsed:: true
					  AKA Elastic Map Reduce | Hosted Hadoop framework
						- {{embed ((64aec848-b92e-472c-9ce1-80fbd7b547bf))}}
					- Amazon FinSpace
					  Store, catalog, prepare and analyse financial industry data in minutes
					- [Amazon Kinesis](https://aws.amazon.com/kinesis/)
					  id:: 64b7ba97-a707-4786-a823-3a0ca7b2d177
					  collapsed:: true
					  Multiple services related to streaming (AKA real-time) data e.g. data analytics, data firehouse to load data into storage, analyse real-time video, data streams
						- [Amazon Kinesis Data Analytics](https://aws.amazon.com/kinesis/data-analytics/)
						  collapsed:: true
						  SQL queries against time-series analytics (uses Apache Flink). Can be processed into ((64b7f40b-fa53-4f71-969f-3cfe64407747)) and ((6463499e-42ab-4a58-8911-df6138dfee8f))
							- Creates an overall summary of data analytics through a conceptual perspective. This process uses native SQL to view all the different forms of streaming data, and it lets you process and aggregate data into live dashboards. You can process this data into ((64b7f40b-fa53-4f71-969f-3cfe64407747)) and ((6463499e-42ab-4a58-8911-df6138dfee8f)). Finally, you can create advanced metrics using triggers for changing live data and sending out different alarms and notifications.
						- [Amazon Kinesis Video Streams](https://aws.amazon.com/kinesis/video-streams)
						  collapsed:: true
						  Capture, process, and store video streams for playback, analytics, and machine learning. Can use many ((6463499e-7e3f-4d66-89b4-cf300a0dcda7))
							- Uses live data from video feeds that can be streamed directly into the Amazon cloud infrastructure. These video feeds can come from several different sources, including smartphones, webcams, and security cameras. This service does not use native SQL for analytical purposes. Video streams can use other services besides Amazon Redshift and Amazon S3.
						- [Amazon Kinesis Data Streams](https://aws.amazon.com/kinesis/data-streams)
						  id:: 64be4f03-3f36-4a12-8bab-2da48da56049
						  collapsed:: true
						  Collect streaming data at any scale
							- Allows you to take in and collect large amounts of streaming data. The type of data includes application logs, marketing feeds, clickstream data, and other forms of log data. This service does not allow you to create time-series analytics.
						- [Amazon Kinesis Data Firehose](https://aws.amazon.com/kinesis/data-firehose)
						  collapsed:: true
						  Reliably load real-time streams into data lakes, warehouses, and analytics services e.g. ((64b7f40b-fa53-4f71-969f-3cfe64407747)), ((6463499e-42ab-4a58-8911-df6138dfee8f)), ((64b7bb5c-7776-4e14-a1ed-befbc7c766b8))
							- Allows you to functionally manage live streaming data and process the data into several Amazon environments. These environments include Amazon OpenSearch Service, Splunk, Amazon Redshift, and Amazon S3. This service does not provide a form of SQL-driven analytics.
					- Amazon Managed Streaming for Apache Kafka (MSK)
					  id:: 64b7bb46-67a7-438e-9cef-11d2ce9f4162
					  Fully managed Apache Kafka service
					- [Amazon OpenSearch Service](https://aws.amazon.com/opensearch-service/)
					  id:: 64b7bb5c-7776-4e14-a1ed-befbc7c766b8
					  Search, visualise, and analyse up to petabytes of text and unstructured data
					- Amazon QuickSight
					  Fast business analytics service
					- Amazon Redshift
					  Fast, simple, cost-effective data warehousing
					- AWS Clean Rooms (Preview)
					  Match, analyse and collaborate on datasets - without sharing or revealing underlying data
					- AWS Data Exchange
					  Find, subscribe to and use 3rd-party data in the cloud
					- [AWS Data Pipeline](https://docs.aws.amazon.com/datapipeline/latest/DeveloperGuide/what-is-datapipeline.html)
					  Being deprecated | Orchestration service for periodic, data-driven workflows
					- [AWS Glue](https://aws.amazon.com/glue/)
					  Simple, scalable and serverless data integration
					- AWS Lake Formation
					  Build a secure data lake in days
				- ### Application Integration
				  id:: 64b7b96a-d3b7-416b-9c76-2f6f8ab6a4c1
				  collapsed:: true
					- Amazon AppFlow
					  No-code integration for SaaS apps and AWS services
					- [Amazon EventBridge](https://aws.amazon.com/eventbridge/)
					  id:: 64b7bc1b-9bf1-4590-a835-6f42a199d644
					  collapsed:: true
					  AKA formerly ((6463499e-5ffa-47d2-aeb5-b9a8bce9bc64)) Events | Serverless event bus for SaaS apps & AWS services
						- Need to choose a destination for events, either:
							- ((64b7c5bd-a765-4700-8546-43162a29aea8))
							- ((64b7c595-93d7-46b1-9900-853028feed64))
							- ((6457bcad-7919-46a4-a9c0-8bb0ddf40189))
					- Amazon Managed Workflows for Apache Airflow (MWAA)
					  Highly available, secure and managed workflow orchestration for Apache AirflowA
					- Amazon MQ
					  Managed message broker service
					- [Amazon SNS](https://aws.amazon.com/sns/)
					  id:: 64b7c595-93d7-46b1-9900-853028feed64
					  AKA Amazon Simple Notification Service | Pub/Sub, SMS, email and mobile push notifications
						- Related: ((64b7ed98-c4a6-422a-89da-31ef57526783))
					- [Amazon SQS](https://aws.amazon.com/sqs/)
					  id:: 64b7c5bd-a765-4700-8546-43162a29aea8
					  collapsed:: true
					  AKA Simple Queue Service | Managed message queues
						- ((6544c9ef-05f1-41f8-8062-a6f5dc3cc6ad)) API:
							- Viewing the contents of a SQS queue
								- Meta
									- Can’t be done via AWS Management Console
									- Removes item from queue unless you add the flag `–attribute-names All`
								- `aws sqs receive-message --queue-url <SQS-URL> --attribute-names All --max-number-of-messages 1 --profile <PROFILE-NAME>`
									- Example
										- `aws sqs receive-message --queue-url https://sqs.eu-west-2.amazonaws.com/823398324985/Test1.fifo --attribute-names All --max-number-of-messages 1 --profile sandbox`
						- Alternatives
							- [Show HN: An SQS Alternative on Postgres | Hacker News](https://news.ycombinator.com/item?id=40307454)
							-
					- [AWS Step Functions](https://aws.amazon.com/step-functions/)
					  id:: 64b7c5ea-fc23-4c8f-bba3-40309679cf7d
					  Coordination for distributed applications
						- ((64aeb5a0-c8b0-447a-89db-d4f0b653b337))
				- ### Blockchain
				  collapsed:: true
					- Amazon Managed Blockchain
					  Create and manage scalable blockchain networks
					- [Amazon QLDB](https://aws.amazon.com/qldb/)
					  id:: 64b7c61e-8603-4409-8977-bddabbc8d595
					  AKA Quantum Ledger Database | Fully managed ledger database
				- ### Business Applications
				  collapsed:: true
					- Alexa for Business
					  Empower your organisation with Alexa
					- Amazon Chime
					  Frustration-free meetings, video calls, and chat
					- Amazon Chime SDK
					  Real-time messaging, audio, video, and screen-sharing
					- Amazon Connect
					  Omnichannel cloud contact center
					- Amazon Honeycode
					  Build mobile & web apps without programming
					- [Amazon Pinpoint](https://aws.amazon.com/pinpoint)
					  id:: 64b7ed81-acc4-49fb-94b2-f0ef254b9018
					  Multichannel marketing communications
					- [Amazon SES](https://aws.amazon.com/ses)
					  id:: 64b7ed98-c4a6-422a-89da-31ef57526783
					  AKA Simple Email Service | High-scale inbound and outbound email
					- Amazon WorkDocs
					  Secure enterprise document storage and sharing
					- Amazon WorkMail
					  collapsed:: true
					  Secure email and calendaring
						- AWS SNS for bounce/complaint notifications
						  https://aws.amazon.com//blogs/ses/handling-bounces-and-complaints/
					- AWS Supply Chain (Preview)
					  Mitigate risks and lower costs with an ML-powered supply chain application
					- AWS Wickr
					  Protect enterprise communications with end-to-end encryption
				- ### Cloud Financial Management
				  collapsed:: true
					- Amazon EC2 Spot Instances
					  Run workloads for up to 90% off
					- AWS Budgets
					  Set custom cost and usage budgets
					- AWS Cost and Usage Report
					  Access comprehensive cost and usage information
					- AWS Cost Explorer
					  Analyse your AWS cost and usage
					- Reserved Instance (RI) Reporting
					  Dive deeper into your reserved instances (RIs)
					- Savings Plans
					  Save up to 72% on computer usage with flexible pricing
				- ### Compute
				  collapsed:: true
					- [Amazon EC2](https://aws.amazon.com/ec2)
					  id:: 6463499e-bd2d-4c48-b05b-bdddeb7d8bba
					  collapsed:: true
					  AKA Amazon Elastic Compute Cloud | Virtual servers
						- Provides virtual servers in the AWS cloud.
						- T2 Instances
						  collapsed:: true
							- CPU Credits
							  collapsed:: true
							  https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/t2-instances.html#t2-instances-cpu-credits
								- http://i.imgur.com/1s39P6i.png
							- What happens if I use all of my credits?
							  collapsed:: true
								- If your instance uses all of its CPU credit balance, performance remains at the baseline performance level. If your instance is running low on credits, your instance’s CPU credit consumption (and therefore CPU performance) is gradually lowered to the base performance level over a 15-minute interval, so you will not experience a sharp performance drop-off when your CPU credits are depleted.
							- If your instance consistently uses all of its CPU credit balance, we recommend a larger T2 size or a fixed performance instance type such as M3 or C3.
							- Monitoring CPU Credits (in ((6463499e-5ffa-47d2-aeb5-b9a8bce9bc64)) )
							  https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/t2-instances.html#t2-instances-monitoring-cpu-credits
						- [How to give permissions for SFTP actions (edit, download etc)](https://stackoverflow.com/a/19648802)
						- Instance types
							- On-Demand
							  collapsed:: true
								- On-Demand Instances are good solutions for application workloads that are considered spiky, short term, and not predictable. This option is considered flexible and low cost because there are no long contacts and no upfront payment. For On-Demand Instances, you are paying per second or per hour based on the instance configuration you choose. When your application workload spikes, your system will dynamically allocate your pre-determined On-Demand Instance to help alleviate your total CPU and memory workload concerns. So, the price will vary based on overall workload activity.
							- Dedicated Hosts
							  collapsed:: true
								- Dedicated Hosts are physical servers that are owned and supported by Amazon. One of their main benefits is the reduction in licensing costs of traditional systems related to software licenses. These systems are good for compliance requirements for external vendors and other internal support needs. They are purchased on an hourly basis, which is similar to On-Demand solutions. Finally, they can be acquired as reserved servers at a greatly reduced price.
							- Spot Instances
							  collapsed:: true
								- Spot Instances are viable for any type of workload that is classified as non-time sensitive, meaning the workload does not have to start or stop at a specific time. This is different from On-Demand Instances because they will be used during times that, although spiky, are used during key times of the day. This type of instance is also good for security testing, developing, integration and validating overall loads on a system.
							- Reserved Instances
							  collapsed:: true
								- Reserved Instances are good for environments that need to use an Amazon Elastic Compute Cloud (EC2) instance between one and three years. These instances should support applications that are online 24/7 and have an anticipated and well-known workload pattern. These instances are classified as supporting the base workload. Any abnormal increase in workload should be managed by Spot Instances or On-Demand Instances.
								- ((649d9949-930d-4e57-8257-3b0f859f7b65))
									- {{embed ((649d9949-930d-4e57-8257-3b0f859f7b65))}}
						- ((64634999-0677-495a-a974-39c697065b37)) : ((665f0a8a-cf17-4aab-9831-fb4b70f5c454))
						- ((649d9901-5e4b-4deb-88a9-40d0043e2a66))
						- Bootstrapping
						  id:: 64ba9532-ffd9-4f28-8237-5ed6f1c6fd7b
						  collapsed:: true
							- Allows you to install security patches or service packs beyond the patch level from an AMI
							- Bootstrapping is the name for a set of common applications that apply service packs, security patches, and security updates, and has the ability to register Amazon Elastic Compute Cloud (EC2) instances to execute security monitoring remotely and to manage other systems. Some bootstrapping applications include Cfn-Init, Cloud-Ini, Capistrano, Chef, and Puppet. When you deploy AWS Cloud Development Kit (CDK) apps into an AWS account and Region (collectively called an environment), you need to provision resources that AWS CDK needs for making deployments. Bootstrapping is the process of provisioning initial resources for deployment which include an Amazon Simple Storage Service (S3) bucket and Identity and Access Management (IAM) roles.
						- ((654a3c6b-660d-401f-b707-0dff67e75c41))
						- Related:
							- ((6463499e-177d-4f57-a6c6-9c947d98a39a))
					- ((6463499e-bd2d-4c48-b05b-bdddeb7d8bba)) Auto Scaling
					  id:: 6463499e-1f1d-4439-ac9b-26c7fb1bd86f
					  collapsed:: true
					  Scale computer capacity to meet demand
						- Automatically scales your set of virtual servers based on changes in demand.
						- http://i.imgur.com/Yw2FqWk.png
						- Options
						  id:: 64ba8f54-9b77-497a-8931-018453acf40a
							- Dynamic Scaling
								- Dynamic scaling adds or subtracts Amazon EC2 instances based on changes in demand.
							- Manual Scaling
								- Manual scaling is when you manually customize adding or subtracting Amazon EC2 instances within the Amazon EC2 console. This option is based on adding or subtracting instances that is typically done in earlier configurations or later on after the application has been up and running and experiences an increase in customer workloads or new processes.
							- Scheduled Scaling
								- Scheduled scaling manages EC2 instances based on workload patterns that are created at predetermined times.
							- Maintain Current Level
							  id:: 64ba8f73-1500-4b75-845c-4aa04f343296
								- only utilizes a minimum number of instances and does not change based on demand.
								- lf you want a specific or minimum number of instances to be executing 24/7, then you would use a maintain current level type of Auto Scaling plan. A sporadic health check is performed on all executing instances. When it finds an unhealthy or sick instance, it terminates that instance and creates a new instance automatically. These notifications can be generated from Amazon Elastic Block Store (EBS), a customer health check script, or Amazon Elastic Compute Cloud (EC2).
						- Types of instances used
						  id:: 64be49bd-8041-491c-a18d-d65b9f866c88
							- On-Demand Instances
							- Spot Instances
							- **Not**
								- On-premises
					- ((6463499e-bd2d-4c48-b05b-bdddeb7d8bba)) Spot Instances
					  Run workloads for up to 90% off
					- [Amazon ECS](https://aws.amazon.com/ecs)
					  id:: 64b7eede-2e9c-445d-b566-71db85dfa49c
					  AKA Elastic Container Service | Highly secure, reliable, and scalable way to run containers
					- [Amazon EKS](https://aws.amazon.com/eks)
					  id:: 64b7efa1-ae9e-4219-ae5d-b5f52ffc4251
					  AKA Elastic Kubernetes Service | The most trusted way to run Kubernetes
					- Amazon Lightsail
					  Launch and manage virtual private servers
					- AWS App Runner
					  Production web applications at scale made easy for developers
					- AWS Auto Scaling
					  Scale multiple resources to meet demand
					- AWS Batch
					  Run batch jobs at any scale
					- AWS Compute Optimiser
					  Identify optimal AWS Computer resources
					- [AWS Elastic Beanstalk](https://aws.amazon.com/elasticbeanstalk/)
					  id:: 6463499d-63a1-485e-bf7e-1bae513fd542
					  Run and manage web apps
					- [AWS Fargate](https://aws.amazon.com/fargate)
					  id:: 64b7f03d-286f-4845-9cbb-765cb4e9653b
					  Severless computer for containers
					- [AWS Lambda](https://aws.amazon.com/lambda/)
					  id:: 6457bcad-7919-46a4-a9c0-8bb0ddf40189
					  collapsed:: true
					  Serverless computing
						- [Documentation](https://docs.aws.amazon.com/lambda/)
							- [Runtimes supported](https://docs.aws.amazon.com/lambda/latest/dg/lambda-runtimes.html)
							  Node.js, Python, Java, .NET, Ruby, Linux-only
							- [Invoking Lambda](https://docs.aws.amazon.com/lambda/latest/dg/lambda-invocation.html) (triggering it)
							  id:: 66434390-e70f-4dda-8141-2cbfe223db56
							  collapsed:: true
								- Allowed triggers
								  collapsed:: true
									- ![image.png](../assets/image_1671458245229_0.png)
								- You can invoke it in several ways:
									- [The Lambda console](https://docs.aws.amazon.com/lambda/latest/dg/lambda-invocation.html./testing-functions.html) – Use the Lambda console to quickly create a test event to invoke your function.
									- [The AWS SDK](https://aws.amazon.com/developer/tools/) – Use the AWS SDK to programmatically invoke your function.
									- The [Invoke](https://docs.aws.amazon.com/lambda/latest/api/API_Invoke.html) API – Use the Lambda Invoke API to directly invoke your function.
									- ((6544c9ef-05f1-41f8-8062-a6f5dc3cc6ad)) [invoke](https://docs.aws.amazon.com/cli/latest/reference/lambda/invoke.html) – Use the `aws lambda invoke` AWS CLI command to directly invoke your function from the command line.
									- [A function URL HTTP(S) endpoint](https://docs.aws.amazon.com/lambda/latest/dg/lambda-invocation.html./lambda-urls.html) – Use function URLs to create a dedicated HTTP(S) endpoint that you can use to invoke your function.
								- [List of AWS services supported](https://docs.aws.amazon.com/lambda/latest/dg/lambda-services.html)
									- Commonly used
										- ((6529032b-bb04-4660-836b-f33e1ae727ba)) POST/GET/etc requests
										- ((64b7c5bd-a765-4700-8546-43162a29aea8)) messages
										- ((64b7c595-93d7-46b1-9900-853028feed64))
										- ((64b7ed98-c4a6-422a-89da-31ef57526783))
							- Cheatsheet
								- Basic template in different languages
								  collapsed:: true
									- [[Python]]
										- id:: 664c8afb-3f38-462c-820e-973f969a9a3a
										  ```python
										  import json
										  print('Loading function')
										  
										  def lambda_handler(event, context):
										    return {
										      'statusCode': 200,
										      'body': json.dumps('Hello from Lambda via API Gateway!')
										    }
										  ```
									- [[JavaScript]]
									  id:: 664c8c27-6372-4aa3-8908-209b6698625f
										- id:: 664c8c2f-38df-4b3d-9217-2573f87366d7
										  ```javascript
										  export const handler = async (event) => {
										      const response = {
										          statusCode: 200,
										          body: JSON.stringify('The API Gateway REST API console is great!'),
										      };
										      return response;
										  };
										  ```
											- ```js
											  // ??
											  export async function (event) => {
											    return {
											      
											    d}
											  }
											  ```
								- If struggling to make a working test event, then you can for example for a ((6463499e-42ab-4a58-8911-df6138dfee8f)) bucket go to Properties > set up an Event Notification for `event type:` `All object create events`, `Destination type`:`Lambda` and pick the new lambda. New Lambda only needs `print(event)` in the handler function and it'll log the event to ((6463499e-5ffa-47d2-aeb5-b9a8bce9bc64)) Logs
								  collapsed:: true
									- ```python
									  def handler_name(event, context):
									  	print(event)
									  ```
								- Entrypoint is an `exports.handler` function?
									- ```javascript
									  exports.handler = async (event) => { 
									  }
									  ```
						- [Learning Resources]
							- Utilise setting for  Permissions : Execution role : `Create a new role with basic Lambda permissions`. It includes permission to upload logs to Amazon CloudWatch Logs
							  id:: 664dd5dd-4e6c-4ffd-a63e-b6a70b8a7416
							- [Boto3 documentation](https://boto3.amazonaws.com/v1/documentation/api/latest/index.html#) (AWS SDK for Python)
								- e.g. S3 / Client / get_object
						- Related: ((663170e0-dd6d-43b6-b2a2-7159447ce0bd))
					- AWS Local Zones
					  Run latency sensitive applications closer to end zones
					- AWS Outposts
					  Run AWS infrastructure on-premises
					- AWS Serverless Application Repository
					  Discover, deploy and publish serverless applications
					- AWS SimSpace Weaver
					  Build dynamic, large-scale spatial simulations on AWS managed infrastructure
					- AWS Wavelength
					  Deliver ultra-low latency applications for 5G devices
					- VMware Cloud on AWS
					  Build a hybrid cloud without custom hardware
				- ### Containers
				  collapsed:: true
					- Amazon ECR
					  id:: 64b7f20b-d92b-49cc-a0ad-64e70eca6cff
					  AKA Elastic Container Registry | Easily store, manage and deploy container images
						- One important thing to note is that ECR’s pricing model is very different from Quay and Docker Hub. Instead of charging based on the number of private repositories, they charge strictly based on storage and bandwidth.
					- ((64b7eede-2e9c-445d-b566-71db85dfa49c))
					- ((64b7efa1-ae9e-4219-ae5d-b5f52ffc4251))
					- AWS App2Container
					  Containerise and migrate existing applications
					- AWS Copilot
					  Easiest way to launch and manage your containerised application
					- ((64b7f03d-286f-4845-9cbb-765cb4e9653b))
					- Red Hat OpenShift Service on AWS
					  Managed OpenShift in the cloud
				- ### Database
				  id:: 64b7b97b-7aaf-4b4e-aabe-39727e50151e
				  collapsed:: true
					- *Notable*
						- [Amazon RDS](https://aws.amazon.com/rds/)
						  id:: 6463499e-a669-4769-9e57-f3cb57e2c4f3
						  collapsed:: true
						  AKA Amazon Relational Database Service | Managed RDBMS for the 6 main RDBMS
							- Pros/Cons
								- Pros
								- Cons
								- Unclear
									- [source] [MySQL in the Cloud - Pros and Cons of Amazon RDS | Severalnines](https://severalnines.com/blog/mysql-cloud-pros-and-cons-amazon-rds)
								- Comparisons
									- ((64a2a0e9-aea9-46ec-82b7-cb4d199c94e0))
									  collapsed:: true
										- {{embed ((64a2a0e9-aea9-46ec-82b7-cb4d199c94e0))}}
							- Documentation
								- https://aws.amazon.com/rds/faqs
								- [Overview](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Welcome.html)
								- Cost
								  collapsed:: true
									- [Instance classes](https://aws.amazon.com/rds/mysql/details/) (specs)
									- 730 hours in a month
									- Cost is broken down by features
									  collapsed:: true
										- ~$15/month for 5GB storage space alone (minimum size)
										- 2x price for multi-AZ (duplication failover server)
									- Billed by running time - specifically by the hour
								- Backups
								  collapsed:: true
									- You can set the backup retention period to between 1 and 35 days.
									- Automated Backups
									  collapsed:: true
										- The automated backup feature of Amazon RDS enables point-in-time recovery of your DB instance. When automated backups are turned on for your DB Instance, Amazon RDS automatically performs a full daily snapshot of your data (during your preferred backup window) and captures transaction logs (as updates to your DB Instance are made). When you initiate a point-in-time recovery, transaction logs are applied to the most appropriate daily backup in order to restore your DB instance to the specific time you requested. Amazon RDS retains backups of a DB Instance for a limited, user-specified period of time called the retention period, which by default is one day but can be set to up to thirty five days. You can initiate a point-in-time restore and specify any second during your retention period, up to the Latest Restorable Time.
										- With Single-AZ deployment the latest recovery time is usually max 5 mins from the failure time
									- Disabling Automated Backups
									  collapsed:: true
										- You may want to temporarily disable automated backups in certain situations; for example, while loading large amounts of data.
										- Important
										  collapsed:: true
											- We highly discourage disabling automated backups because it disables point-in-time recovery. Disabling automatic backups for a DB instance deletes all existing automated backups for the instance. If you disable and then re-enable automated backups, you are only able to restore starting from the time you re-enabled automated backups.
									- https://stackoverflow.com/questions/9815612/should-i-stick-only-to-aws-rds-automated-backup-or-db-snapshots
								- Read Replicas
								  collapsed:: true
								  Async replication
									- https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ReadRepl.html#USER_ReadRepl.Overview
									- Requires automatic backups turned on
									- You can enable automatic backups on a MySQL or MariaDB Read Replica.
									- You can create up to five Read Replicas from one DB instance. You can specify it as the source DB instance for another Read Replica.  You cannot have more than four instances involved in a replication chain
									- Creating a Read Replica
									  collapsed:: true
										- When you initiate the creation of a Read Replica, Amazon RDS takes a DB snapshot of your source DB instance and begins replication. As a result, you experience a brief I/O suspension on your source DB instance as the DB snapshot occurs. The I/O suspension typically lasts about one minute and can be avoided if the source DB instance is a Multi-AZ deployment (in the case of Multi-AZ deployments, DB snapshots are taken from the standby).
									- Implementing failure recovery
									  collapsed:: true
										- You can use Read Replica promotion as a data recovery scheme if the source DB instance fails; however, if your use case requires synchronous replication, automatic failure detection, and failover, we recommend that you run your DB instance as a Multi-AZ deployment instead.
										- If you are aware of the ramifications and limitations of asynchronous replication and you still want to use Read Replica promotion for data recovery, you first create a Read Replica and then monitor the source DB instance for failures.
										- In the event of a failure, do the following:
										  collapsed:: true
											- Promote the Read Replica.
											- Direct database traffic to the promoted DB instance.
											- Create a replacement Read Replica with the promoted DB instance as its source.
								- Using phpmyadmin to administer
								  collapsed:: true
									- https://stackoverflow.com/questions/4402482/using-phpmyadmin-to-administer-amazon-rds
								- Importing a database backup
								  collapsed:: true
									- Upload the database onto EC2
										- Either:
											- ((64634999-0677-495a-a974-39c697065b37)) : ((665f0a8a-cf17-4aab-9831-fb4b70f5c454))
												- Example
													- Terminal 1
													  ```bash
													  aws ssm start-session --target i-0872323d23d3dqw --region eu-west-2 --document-name AWS-StartPortForwardingSession --parameters "localPortNumber-55678,portNumber=22" --profile sandbox
													  ```
													- Terminal 2
													  ```bash
													  ssh -i key1.pem ec2-user@localhost -p 55678
													  ```
											- ((663a57ae-8972-4c68-8624-a4b7e64b97ea))
												- #+BEGIN_WARNING
												  This took like 30 minutes for a 600MB file [[2024-06-04 Tuesday]] 
												  #+END_WARNING
											- `aws ssm send-command`
												- ```
												  # Upload the file to S3
												  aws s3 cp /home/localuser/myfile.txt s3://your-bucket-name/myfile.txt
												  
												  # Use SSM to download the file from S3 to the EC2 instance
												  aws ssm send-command \
												      --instance-ids "i-0123456789abcdef0" \
												      --document-name "AWS-RunShellScript" \
												      --parameters 'commands=["aws s3 cp s3://your-bucket-name/myfile.txt /home/ec2-user/myfile.txt"]' \
												      --region your-region
												  	--profile sandbox
												  ```
									- ((64b806d2-fdd2-4f63-84b8-4f0b76f20027)) : RDS console > Parameter groups tab > Create parameter group
										- Choose the Engine type and Parameter group family that matches that used by your RDS
									- ((6463499e-bd2d-4c48-b05b-bdddeb7d8bba))
										- Install MySQL CLI
											- `sudo dnf install mariadb105-server`
										- Login to RDS db
											- `mysql -h database-1.cw44dawda.eu-west-2.rds.amazonaws.com -P 3306 -u admin -p`
										- ((16e48ca5-10dd-4c45-986c-5f03be9328c7)) CLI
											- `source sakila-db.sql`s
								- [Encryption](http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Overview.Encryption.html)
								  collapsed:: true
									- [Encryption options included?](https://aws.amazon.com/blogs/aws/new-encryption-options-for-amazon-rds/)
								- Amazon Aurora for clustering (high availability)
								  collapsed:: true
									- https://aws.amazon.com/rds/aurora/faqs/
									- High Availability and Replication
									  collapsed:: true
									  http://i.imgur.com/SOTt37r.png
										- Q: How does Amazon Aurora improve my database’s fault tolerance to disk failures?
										  collapsed:: true
											- Amazon Aurora automatically divides your database volume into 10GB segments spread across many disks. Each 10GB chunk of your database volume is replicated six ways, across three Availability Zones. Amazon Aurora is designed to transparently handle the loss of up to two copies of data without affecting database write availability and up to three copies without affecting read availability. Amazon Aurora storage is also self-healing. Data blocks and disks are continuously scanned for errors and repaired automatically.
										- Q: How does Aurora improve recovery time after a database crash?
										  collapsed:: true
											- Unlike other databases, after a database crash Amazon Aurora does not need to replay the redo log from the last database checkpoint (typically 5 minutes) and confirm that all changes have been applied, before making the database available for operations. This reduces database restart times to less than 60 seconds in most cases. Amazon Aurora moves the buffer cache out of the database process and makes it available immediately at restart time. This prevents you from having to throttle access until the cache is repopulated to avoid brownouts.
									- Cons
									  collapsed:: true
										- when we were launching Aurora cluster in Amazon Services there is no option to set storage size. The default minimum storage value is 10Gb and as our database size increases, the storage space will grow up automatically by 10GB up to 64TB.
										- For Amazon Aurora DB clusters, the default backup retention period is one day regardless of how the DB cluster is created.
								- Note: [XtraBackup doesn't work with RDS (as there's no access to tablespace)](https://stackoverflow.com/a/20292868)
					- [Amazon Aurora](https://aws.amazon.com/rds/aurora/)
					  id:: 6463499e-0ca7-46e7-8632-237030c12357
					  collapsed:: true
					  High performance managed RDBMS (only MySQL or PostgreSQL)
						- Most managed database option, enterprise-class
						- Supported databases
							- MySQL
							- PostgreSQL
						- Features
							- 1/10th the cost of commercial databases
							- Data replication (up to 6)
							- Up to 15 read replicas for enhancing read performance. Under 200ms lag between primary and read replica
							- Continuous backups to Amazon S3
							- Point-in-time recovery
							- Up to 5x faster than standard MySQL and up to 3x faster than standard PostgreSQL
						- Amazon Aurora is a database solution that consists of an Aurora database cluster housing multiple volumes. It is created across multiple Availability Zones (AZs), where each AZ will have its own copy of the clustered data. There are two key types of database instances that make up an Aurora database. The primary database instance is where the main database will have all the direct reads and writes and other
						  modifications to the data within the database. The data changes are occurring within the cluster volume. The other type of database instance is the Aurora replica, also called the read replica. The Aurora DB can have up to 15 read replicas, not including the primary database.
					- [Amazon DocumentDB](https://aws.amazon.com/documentdb/)
					  collapsed:: true
					  Managed NoSQL document database (with ((63a9bb62-f035-405e-b4c9-633f8b95c38b)) compatibility)
						- Built on MongoDB
					- [Amazon DynamoDB](https://aws.amazon.com/dynamodb/)
					  id:: 6463499e-971f-49ad-9136-306a4377fe86
					  collapsed:: true
					  Managed NoSQL key-value database
						- Features
							- Serverless - no need to provision, patch or manage servers. No installation
							- Automatically scales
							- Highly performant - up to 45 million requests per second
							- ((64634999-f8bf-4650-9e69-f68bda7d4cd5)) : ((64634999-79da-4354-8f74-4a85427a1aa8))
							- Best suited for simple queries across one table, rather than complex and over multiple tables
							- Encrypts data at rest using ((64b81161-baf7-46dc-ab13-4755b196d0fb)). Can only be altered at time of new table creation
						- Comparing ((6463499e-a669-4769-9e57-f3cb57e2c4f3)) and ((6463499e-971f-49ad-9136-306a4377fe86))
						  id:: 64a2a0e9-aea9-46ec-82b7-cb4d199c94e0
						  collapsed:: true
							- RDS
							  collapsed:: true
								- Automatic high availability, recovery provided
								- Customer ownership of data, schema, network
							- DynamoDB
							  collapsed:: true
								- Key-value
								- Massive throughput
								- PB size potential
								- Granular API access
					- [Amazon ElastiCache](https://aws.amazon.com/elasticache/)
					  id:: 6463499e-529d-478c-822f-2ff43f26b6bf
					  collapsed:: true
					  Managed Redis or ((64634999-fc4a-4bf0-9d74-f8dc23708311)) (in-memory cache)
						- https://aws.amazon.com/elasticache/
						- Cons
						  collapsed:: true
							- Elasticache forces you to use a single instance of ((6607f722-b674-4037-af49-e03bafebc259)), which is sub-optimal.
							  https://stackoverflow.com/a/36813957
					- [Amazon Keyspaces](https://aws.amazon.com/keyspaces/)
					  id:: 663a5791-9f7e-43cd-b84a-6c225d586d86
					  Managed Apache Cassandra-compatible database
					- [Amazon MemoryDB for Redis](https://aws.amazon.com/memorydb/)
					  id:: 64b7f38a-d557-4a8d-8f77-d9a80e3ee23f
					  ((6607f722-b674-4037-af49-e03bafebc259)) -compatible, durable, in-memory database for ultra-fast performance
					- [Amazon Neptune](https://aws.amazon.com/neptune/)
					  id:: 663a5791-97bd-4716-98ae-69c5d9bd1a6e
					  Managed NoSQL graph database
					- [Amazon Redshift](https://aws.amazon.com/redshift/)
					  id:: 64b7f40b-fa53-4f71-969f-3cfe64407747
					  collapsed:: true
					  Data warehousing
						- Amazon Redshift is a petabyte-scaled infrastructure that is considered a data warehouse solution. Also better suited for terabytes than ((6463499e-a669-4769-9e57-f3cb57e2c4f3))
						- Amazon Redshift has the ability to process both structured and unstructured data. It uses columnar storage for query performance, which reduces the amount of data loaded from disk to memory, lessening the amount of I/O needed for processing.
					- [Amazon Timestream](https://aws.amazon.com/timestream/)
					  Managed NoSQL time series database
					- Related:
						- [Amazon Aurora Serverless](https://aws.amazon.com/rds/aurora/serverless/)
						  Autoscaling ((6463499e-0ca7-46e7-8632-237030c12357))
						- ((64b7c61e-8603-4409-8977-bddabbc8d595))
						- [Amazon SimpleDB](https://aws.amazon.com/simpledb/)
						  Managed NoSQL database. Superseded by ((6463499e-971f-49ad-9136-306a4377fe86))
				- ### Developer Tools
				  collapsed:: true
					- Amazon CodeCatalyst (Preview)
					  Unified software development service for faster development and delivery on AWS
					- [Amazon CodeGuru](https://aws.amazon.com/codeguru/)
					  id:: 64b7f523-88d6-4ec5-9251-ff9fd71f0512
					  Find your most expensive lines of code
					- Amazon Corretto
					  Production-ready distribution of OpenJDK
					- AWS Cloud Control API
					  Manage AWS and 3rd-party cloud infrastructure with consistent APIs
					- [AWS CDK](https://aws.amazon.com/cdk/)
					  id:: 64b7f615-66b0-4272-83e0-90ebbce92b48
					  AKA AWS Cloud Development Kit | Model cloud infrastructure using code
						- Pros/Cons
							- Pros
								- ((663d167c-3368-4382-b1e8-98a1d9a2177a))
								  id:: 663a5791-bcdd-44b3-a32f-2e51384ac226
								  collapsed:: true
									- {{embed ((663d167c-3368-4382-b1e8-98a1d9a2177a))}}
							- Cons
								-
							- Unclear
							- Downstream/Upstream Pros/Cons
								- ((6620d4c0-1c5f-4f16-bfee-cf33e7cf5ffd))
								- ((663d1c53-446f-45e6-9c59-9dc8344c6c20))
							- Comparisons
								- ((64b7f615-66b0-4272-83e0-90ebbce92b48)) vs ((6463499e-dc33-4af7-bbb7-33338a8a325b))
								  id:: 663cee91-26d7-47ea-8989-ab0ed0b22869
								  collapsed:: true
									- For ((64b7f615-66b0-4272-83e0-90ebbce92b48))
										- 2019 general availability, compared to 2011 for CloudFormation. It took until 2016 for YAML to be added in addition to original JSON format, which was being surpassed by ((638d061d-e696-4f04-933c-35f8836e125d)) which released in 2014
									- For ((6463499e-dc33-4af7-bbb7-33338a8a325b))
									- Similarities
									- Unclear
								- ((64b7f615-66b0-4272-83e0-90ebbce92b48)) vs Pulumi
						- Documentation
							- Built on top of [`jsii`](https://github.com/aws/jsii)
							  id:: 663e1e54-9adb-4ad1-9e5e-d51add84f734
								- jsii allows code in any language to naturally interact with JavaScript classes. It is the technology that enables the AWS Cloud Development Kit to deliver polyglot libraries from a single codebase!
								- Is itself written in 70% ((629ccb26-1eab-4686-a7b8-f9433a871440)), as well as small parts in the various other codebases
							- CDK compiles your code into either ((6463499e-dc33-4af7-bbb7-33338a8a325b)) template files or ((638d061d-e696-4f04-933c-35f8836e125d)) files
							- [Docs](https://docs.aws.amazon.com/cdk/index.html)
						- [Learning Resources]
							- [Getting started with the AWS CDK - AWS Cloud Development Kit (AWS CDK) v2](https://docs.aws.amazon.com/cdk/latest/guide/getting_started.html)
					- [AWS Cloud9](https://aws.amazon.com/cloud9/)
					  id:: 64b7f629-76b1-4695-9eec-3caea77b1452
					  Write, run and debug code on a cloud IDE
						- Available for existing accounts, not new accounts. It's being deprecated in favour of e.g. ((664efeb5-c282-4e74-a015-be6bc3f0faf3)) for ((63209272-1088-4824-a762-4ac7ded04b0a))
					- AWS CloudShell
					  id:: 663a5791-49d2-4403-a63a-2b12c34bd94d
					  Command line access to AWS resources and tools directly from a browser
					- [AWS CodeArtifact](https://aws.amazon.com/codeartifact/)
					  id:: 64b7f64c-8e70-4bf4-8680-2795cb1cc84f
					  Secure, scalable, and cost-effective artifact management for software development
					- [AWS CodeBuild](https://aws.amazon.com/codebuild/)
					  id:: 64b7f66c-86f0-443a-b53b-190d004e78e7
					  collapsed:: true
					  Build and test code
						- A fully managed build service that compiles source code, runs tests, and produces software packages that are ready to deploy. With CodeBuild, you don’t need to provision, manage, and scale your own build servers.
					- [AWS CodeCommit](https://aws.amazon.com/codecommit/)
					  id:: 64b7f676-aaa5-4351-aeee-dcc14b014bae
					  Store code in private Git repositories
					- [AWS CodeDeploy](https://aws.amazon.com/codedeploy/)
					  id:: 64b7f692-54e9-4bcf-95f9-301d3c298b1d
					  collapsed:: true
					  Automate code deployments
						- It gives you the ability to automate manual processes straight into ((6463499e-bd2d-4c48-b05b-bdddeb7d8bba)) instances using ((6457bcad-7919-46a4-a9c0-8bb0ddf40189)) functions and ((64b7eede-2e9c-445d-b566-71db85dfa49c)).
						- It gives you a serverless platform that allows you to promote or automate into hundreds and even thousands of EC2 instances. This service also offers the ability to stop and rollback deployments, if needed. You can also use this service while storing your application information (scripts, packages, web config files, and other code) in GitHub repositories, Bitbucket repositories, and even ((6463499e-42ab-4a58-8911-df6138dfee8f))
					- [AWS CodePipeline](https://aws.amazon.com/codepipeline/)
					  id:: 64b7f69c-6359-41e8-ae5d-bccf8b1f1a4d
					  collapsed:: true
					  Release software using continuous delivery
						- ((64aec668-6f11-4961-a756-812c86bf8a37))
					- AWS CodeStar
					  Develop and deploy AWS applications
					- ((64b7f74b-b66e-4fb5-a30a-b464666dcfae))
					- [AWS CLI](https://docs.aws.amazon.com/cli/)
					  id:: 6544c9ef-05f1-41f8-8062-a6f5dc3cc6ad
					  collapsed:: true
					  AKA Command Line Interface | Line Interface Unified tool to manage AWS services
						- Links
							- [GitHub - aws/aws-cli: Universal Command Line Interface for Amazon Web Services](https://github.com/aws/aws-cli)
							- [aws — AWS CLI 2.13.31 Command Reference](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/index.html)
						- Documentation
							- `aws sts get-caller-identity` = return login info. Quick easy way to check you're authenticated properly
							  id:: 659eabc0-f7e5-44a9-8c35-f09d569f923b
								- `aws sts get-caller-identity --profile sandbox` = works if your `~/.aws/credentials` file has value like:
									- ```
									  [sandbox]
									  output = json
									  region = eu-west-2
									  aws_access_key_id = A9DW9DAWD
									  aws_secret_access_key = 35KR3K3FEWF
									  ```
							- Usecases
								- ((6463499e-42ab-4a58-8911-df6138dfee8f))
					- ((64b7f707-0a4b-4c80-a6c2-7557f3174b75))
					  id:: 64b7f6f4-be63-4cf4-89b6-4d7076c02ecd
					- AWS Fault Injection Simulator
					  Improve resiliency and performance with controlled experiments
					- AWS Tools and SDKs
					  Tools and SDKs for AWS
					- [AWS X-Ray](https://aws.amazon.com/xray/)
					  id:: 64b7f73d-a5c9-4ec8-895e-ef8e5ab585d9
					  collapsed:: true
					  Analyse and debug your applications
						- Provides detailed data on requests that your application serves. It contains tools that allow you to gain insights into all the possible issues that may exist within the application as well as ways to further optimize it.
				- ### End User Computing
				  collapsed:: true
					- Amazon AppStream 2.0
					  Stream desltop applications securely to a browser
					- Amazon WorkSpaces Family
					  Virtual desktop services for every use case
				- ### Front-End Web & Mobile
				  collapsed:: true
					- ((6529032b-bb04-4660-836b-f33e1ae727ba))
					- Amazon Location Service
					  Securely and easily add location data to applications
					- ((64b7ed81-acc4-49fb-94b2-f0ef254b9018))
					- ((64b7ed98-c4a6-422a-89da-31ef57526783))
					- [AWS Amplify](https://aws.amazon.com/amplify/)
					  id:: 63904f39-6a5a-49aa-b6c5-f9811359b487
					  collapsed:: true
					  Build, deploy, host and manage scalable web and mobile apps
						- https://aws-amplify.github.io/ Have you checked out AWS AppSync and AWS Amplify? It’s Firebase + GraphQL and more with the advantages of AWS ecosystem and service availability
						- Seems similar to FCM Firebase - this dashboard can manage the entire backend
						- Documentation
							- ((bad0d08b-f295-4be9-9789-c335d33a2d90))
							- https://docs.amplify.aws/start/q/integration/react/
								- Pre-requisite steps
									- `npm install -g @aws-amplify/cli`
									- `amplify configure`
										- #+BEGIN_WARNING
										  This won't work in Visual Studio Code Flatpak due to sandboxing. Run in the native version, or a terminal
										  #+END_WARNING
								- The API you will be creating in this step is a GraphQL API using AWS AppSync (a managed GraphQL service) and the database will be Amazon DynamoDB (a NoSQL database).
								- Connect API
									- GraphQL endpoint: `https://ygo4qrcnobdljeo4hoc62c4fmq.appsync-api.eu-west-2.amazonaws.com/graphql`
									- GraphQL API KEY: `da2-luglb7ypnvccvl63d6w37gd7ha`
						- [Learning Resources]
							- [Intro to AWS Amplify | Amazon Web Services - YouTube](https://youtu.be/uRbGMZ9oPjw)
							  collapsed:: true
								- {{video https://youtu.be/uRbGMZ9oPjw}}
									- {{youtube-timestamp 47}} Looks like it easily connects to various other AWS services like Cognito, S3, CloudFront,
									- {{youtube-timestamp 130}} AWS Amplify Studio allows easily importing premade frontend components
									-
							- [What is AWS Amplify? Pros and Cons? - YouTube](https://www.youtube.com/watch?v=HkbjHtG_d7w)
							  collapsed:: true
								- {{video https://www.youtube.com/watch?v=HkbjHtG_d7w}}
									- {{youtube-timestamp 31}} It's a glue service that helps you build apps quickly
									- {{youtube-timestamp 39}} Supports JavaScript, Reactive, ((635fba79-b85e-4821-810a-ce45a268a6ad)), Android, iOS, Flutter, etc
									- {{youtube-timestamp 57}} Primarily a CLI tool (2021)
									- {{youtube-timestamp 68}} Quickly add storage, auth, monitoring, PubSub, etc. It's just CloudFormation behind the scenes. It shows easy to understand names, rather than the AWS names for different services
										- ![image.png](../assets/image_1671459959032_0.png)
									- {{youtube-timestamp 214}} Usage
										- `amplify configure`
										- `amplify add api` opens a wizard
									- {{youtube-timestamp 239}} Data model section allows you to use a drag-and-drop editor to create models you can quickly import into your project
									- {{youtube-timestamp 287}} CLI can do everything the GUI can do
									- Pros
										- Getting started quickly
										- Prototyping
										- Fast development cycles - easy to tear down
										- Simple - shields you from the complexity of AWS
									- Cons
										- You don't *really* learn how to use AWS
										- Collaboration can be frustrating
										- Difficult to go "outside the box"
										- Potential for surprise bills - recommended to watch this: [How to Setup AWS Billing Alerts - A Step by Step Guide - YouTube](https://www.youtube.com/watch?v=FVwdlJ8lM0Q)
										  collapsed:: true
											- {{video https://www.youtube.com/watch?v=FVwdlJ8lM0Q}}
					- AWS AppSync
					  Accelerate app devleopment with fully-managed, scalable GraphQL APIs
					- [AWS Device Farm](https://aws.amazon.com/device-farm/?did=ap_card&trk=ap_card)
					  id:: 64b7f707-0a4b-4c80-a6c2-7557f3174b75
					  Test Android, iOS, and web apps on real devices in the AWS cloud
				- ### Internet of Things
				  collapsed:: true
					- AWS IoT Core
					  Connect devices to the cloud
					- AWS IoT FleetWise
					  easily collect, transform and transfer vehicle data to the cloud in near-real time
					- AWS IoT SiteWise
					  IoT data collector and interpreter
					- AWS IoT TwinMaker
					  Customise operaitons by easily creating digital twins of real-world systems
					- AWS IoT Greengrass
					  Local compute, messaging and sync for devices
					- AWS IoT 1-Click
					  One-click creation of an ((6457bcad-7919-46a4-a9c0-8bb0ddf40189)) trigger
					- AWS IoT Analytics
					  Analytics for IoT devices
					- AWS IoT Button
					  Cloud programmable dash button
					- AWS IoT Device Defender
					  Security management for IoT devices
					- AWS IoT Device Management
					- AWS IoT EduKit
					- AWS IoT Events
					- AWS IoT RoboRunner
					- AWS Partner Device Catalog
					  Curated catalog of AWS-compatible IoT hardware
					- FreeRTOS
					  Real-time operating system for microcontrollers
				- ### Machine Learning
				  id:: 64b7b999-0ee4-4508-852d-2baf1a973c02
				  collapsed:: true
					- [Amazon Augmented AI](https://aws.amazon.com/augmented-ai/)
					  Easily implement human review of ML predictions
					- [Amazon Bedrock](https://aws.amazon.com/bedrock/)
					  id:: 64b7fb92-9922-4bb1-aa51-1972c348bfaa
					  collapsed:: true
					  Build with foundation models
						- Features
							- Foundation models
								- Llama by Meta
								- Claude by Anthropic
								- ((646349df-2813-49c9-a073-bdc5027e4877))
								- Titan by Amazon
								- Command by Cohere
								- etc
							- Agents for Amazon Bedrock
							  collapsed:: true
							  Enables GenAI apps to execute multi-step business tasks using natural language
								- Overview
									- Breaks down and orchestrates tasks
										- Steps are generated using available actions and Knowledge Bases
									- Completes tasks by dynamically invoking APIs
									- Surfaces chain-of-thought trace and underlying agent prompts
								- Detailed flow
									- Select the model to use
										- e.g. `anthropic.claude-v2:1`
									- Define instructions for agent
										- e.g. "you are a customer relationship management agent for
										  helping a sales person plan their work with customers.
										  you can provide a company overview. you have access to
										  customer interaction history (like meeting time and notes
										  about what was discussed) and customer preferences."
									- Select Knowledge Bases
									- Select Action Groups
										- OpenAPI schema in JSON which has different URL slugs give different data
											- e.g. "get customer profile info"
										-
								- {Archive}
									- [New Demo & description - Agents for Amazon Bedrock | Amazon Web Services - YouTube](https://youtu.be/JkDzZFTXeSw)
									-
									-
					- ((64b7f523-88d6-4ec5-9251-ff9fd71f0512))
					- [Amazon Comprehend](https://aws.amazon.com/comprehend/)
					  collapsed:: true
					  Discover insights and relationships in text
						- It analyzes the contents of documents and provides insights using natural language processing (NLP). Comprehend works with all text files in UTF-8 format and builds insights using various elements inside documents, including sentiments, language, key phrases, and entities. You can use Comprehend for creating new products by using it to understand the contents of
						  documents. Comprehend can also be used to search social media feeds for product mentions or extract topics contained inside documents.
					- Amazon DevOps Guru
					  ML-powered cloud operations service to improve application availability
					- Amazon Elastic Inference
					  Deep-learning inference acceleration
					- Amazon Forecast
					  Increase forecast accuracy using machine learning
					- Amazon Fraud Detector
					  collapsed:: true
					  Detect more online fraud faster
						- provides a fully managed service for automatically detecting possible online
						  fraudulent activities. These activities include the making of fake accounts and unauthorized transactions. Fraud Detector uses ML to analyze data and leverages 20 years of fraud detection experience at Amazon. You can create customized fraud detection models using Fraud Detector and build decision logic that interprets the evaluation of your fraud detection model. You can then set an outcome for each fraud
						  evaluation that can be either a pass or a send for review.
					- Amazon HealthLake
					  Securely store, transform, query and analyse health data in minutes
					- Amazon Kendra
					  Reinvest enterprise search with ML
					- [Amazon Lex](https://aws.amazon.com/lex/)
					  Build voice and text chatbots
					- Amazon Lookout for Equipment
					  Detect abnormal equipment behaviour by analysing sensor data
					- Amazon Lookout for Metrics
					  Automatically detect anomalies in metrics and identify their root cause
					- Amazon Lookout for Vision
					  Spot product defects using computer vision to automate quality inspection
					- Amazon Monitron
					  Reduce unplanned equipment downtime with predictive maintenance and machine learning
					- Amazon Omics
					  Transform omics data into insights
					- Amazon Personalise
					  Build real-time recommendations into your applications
					- [Amazon Polly](https://aws.amazon.com/polly/)
					  id:: 64b804b9-35d0-44c6-a7c6-d6908582a9a3
					  collapsed:: true
					  Turn text into life-like speech
						- provides text-to-speech capabilities that help you create more engaging and accessible applications. Polly has support for multiple languages and has a wide repository of lifelike voices, allowing you to create speech-enabled applications that can be used across many different locations with the right voice for each location. Polly has various neural text-to-speech (NTTS) voices that utilize machine learning (ML) technology, creating very natural human-like text-to-speech capabilities. This allows for creatina newscaster stvle voices that are ideal for news-narratina reauirements.
					- [Amazon Rekognition](https://aws.amazon.com/rekognition/)
					  id:: 64b804c0-e44f-4279-a3d1-1202b16c19f4
					  collapsed:: true
					  Analyse image and video
						- You can use Amazon Rekognition. Amazon Rekognition allows you to have video and image analysis capabilities in your applications. Images and videos to be analyzed are fed to the Amazon Rekognition Application Programming Interface (API), which then uses the Rekognition service to identify activities, people, text, scenes, and objects in the images and videos. It can also detect content that may be inappropriate. Amazon Rekognition provides face search, facial comparison, and facial analysis features, which can be used for applications like people counting, user verification, and public safety. The Rekognition API can analyze images and videos that are stored in Amazon S3.
					- [Amazon SageMaker](https://aws.amazon.com/sagemaker/)
					  Build, train and deploy machine learning models at scale
					- Amazon SageMaker Ground Truth
					  Build accurate ML training datasets
					- Amazon Textract
					  Extract text and data from documents
					- Amazon Transcribe
					  Automatic speech recognition
					- Amazon Translate
					  Natural and fluent language translation
					- Apache MXNet on AWS
					  Scalable, open-source deep learning framework
					- Unsorted
						- AWS Deep Learning AMIs
						  Deep learning on Amazon EC2
						- AWS Deep Learning Containers
						  Docker images for deep learning
						- AWS DeepComposer
						  ML-enabled musical keyboard
						- AWS DeepLens
						  collapsed:: true
						  Deep learning enabled video camera
							- Amazon DeepLens is a video camera that has deep learning enabled. It can perform inference locally using
							  deployed models that have been provisioned from AWS Cloud. With DeepLens, you can gain insight into the latest artificial intelligence (Al)
							  technology to create computer vision systems that utilize a deep learning model. DeepLens allows machine learning (ML) beginners to
							  understand deep learning through tutorials that are based on deep learning projects. For advanced users, DeepLens provides a development
							  environment where you can train your convolutional neural network (CNN) model and deploy the application project that contains the model to
							  the AWS DeepLens device.
						- AWS DeepRacer
						  Autonomous 1/18th scale race car, driven by ML
						- AWS Inferentia
						  Machine learning inference chip
						- AWS Panorama
						  Improve your operations with computer vision at the edge
						- PyTorch on AWS
						  Flexible open-source machine learning framework
						- TensorFlow on AWS
						  Open-source machine learning library
						- [Amazon Q Developer](https://aws.amazon.com/q/developer/)
						  id:: 64b7f74b-b66e-4fb5-a30a-b464666dcfae
						  AKA previously [Amazon CodeWhisperer](https://aws.amazon.com/codewhisperer) | Build apps faster with ML-powered coding companion
							- Implementations
								- CLI (MacOS-only?)
								- ((63209272-1088-4824-a762-4ac7ded04b0a)) [extension](https://marketplace.visualstudio.com/items?itemName=AmazonWebServices.amazon-q-vscode)
					- Generative AI
						- Amazon Q
						- Amazon Q Code Transformation
						- ((662b577a-b110-483f-aef4-eaa02f3c591d))
					- Related: ((63f8fe5a-e718-4363-aba5-549a93eec7a7))
				- ### Management & Governance
				  collapsed:: true
					- [Amazon CloudWatch](https://aws.amazon.com/cloudwatch/)
					  id:: 6463499e-5ffa-47d2-aeb5-b9a8bce9bc64
					  collapsed:: true
					  Monitor resources and applications
						- You will need to install the CloudWatch agent on both groups of servers. You will then configure system level metrics using the CloudWatch dashboard. The unified CloudWatch agent allows you to collect system-level metrics from an Amazon Elastic Compute Cloud (EC2) infrastructure. You can collect on-premises metrics, also called hybrid environments, where you have both on-premises and cloud-based solutions. Using the CloudWatch agent, you can collect logging information from on-premises systems and EC2 instances running on a Windows or a Linux server.
						- You do not have to migrate the on-premises systems to AWS because AWS CloudWatch gives you the ability to monitor both on-premises and AWS EC2 infrastructures.
						- Configure the metrics dashboard within ((6463499e-fe31-4613-8b61-e232816b6ddb)) is incorrect because it is not a standalone monitoring service, but only an API to monitor specific services.
						- Features
							- Access all your metrics from a central location
							- Gain visibility into your applications, infrastructure and services
							- Reduces MTTR (mean time to resolution) and improve TCO (total cost of ownership)
							- Alarm can generate alerts if certain metrics are reached
								- Integrated with SQS to easily notifying people
							- Dashboard can be show metrics in real-time
							- Expires after 15 months
						- ((64b7bc1b-9bf1-4590-a835-6f42a199d644))
						  id:: 65abbd11-6151-4bb0-a330-8d87919759d4
						  AKA formerly known as ((6463499e-5ffa-47d2-aeb5-b9a8bce9bc64)) Events. EventBridge now has more features
					- Amazon Managed Grafana
					  Scalable, secure and highly available data visualisation for your operational metrics, logs and taces
					- Amazon Managed Service for Prometheus
					  Highly available, secure and managed monitoring for your containers
					- AWS Chatbot
					  ChatOps for AWS
					- [AWS CloudFormation](https://aws.amazon.com/cloudformation/)
					  id:: 6463499e-dc33-4af7-bbb7-33338a8a325b
					  collapsed:: true
					  Create and manage resources with templates
						- Pros/Cons
							- Pros
								-
							- Cons
								-
							- Unclear
							- Downstream Pros/Cons
								- ((6620d4c0-1c5f-4f16-bfee-cf33e7cf5ffd)) vs ((6463499e-dc33-4af7-bbb7-33338a8a325b))
								  id:: 663cad07-a75f-4257-9e42-f1733f0f4bd0
								  collapsed:: true
									- For ((6620d4c0-1c5f-4f16-bfee-cf33e7cf5ffd))
										- Much more concise (at least 50% less code)
										- ((663c9e51-4706-42af-a785-973914c1a56d)) has a local development environment which speeds up the development cycle and makes it easier to iterate on serverless applications
										- ((663c9e51-4706-42af-a785-973914c1a56d)) has built-in deployment commands for deploying serverless apps. This handles zipping code, uploading it to S3, deploying the ((6463499e-dc33-4af7-bbb7-33338a8a325b)) stack, and is far simpler than using ((6463499e-dc33-4af7-bbb7-33338a8a325b)) directly
										- Integration with ((6457bcad-7919-46a4-a9c0-8bb0ddf40189))featurs such as defining environment variables, specifying event sources, configuring permissions
									- For ((6463499e-dc33-4af7-bbb7-33338a8a325b))
										- Allows defining almost any AWS resources using JSON or YAML templates. Rather than only serverless resources, it also is suitable for traditional application architectures
										- Granular control, customisation and flexibility
										- Large 3rd-party tooling and ecosystem
									- Similarities
									- Unclear
										- ((6620d4c0-1c5f-4f16-bfee-cf33e7cf5ffd)) is specifically designed for building serverless applications, so it gives you simplified syntax and model for serverless resources such as ((6457bcad-7919-46a4-a9c0-8bb0ddf40189)), ((6529032b-bb04-4660-836b-f33e1ae727ba)), ((6463499e-971f-49ad-9136-306a4377fe86)), etc
							- Comparisons
								- ((6463499e-dc33-4af7-bbb7-33338a8a325b)) vs ((638d061d-e696-4f04-933c-35f8836e125d))
								  id:: 663cedf6-f73b-48e6-ae2c-153ae86971f4
									- For ((6463499e-dc33-4af7-bbb7-33338a8a325b))
										- Deep integration with ((6463499e-9096-4ccf-8af2-96569e23c33b))
									- For ((638d061d-e696-4f04-933c-35f8836e125d))
										- Supports multiple cloud providers other than ((6463499e-9096-4ccf-8af2-96569e23c33b)) including ((663a5790-2e2f-4272-b816-924917da0a49)), ((663a5790-13e8-4491-8f8c-a314785db64b)), as well as other services like [[Docker]] and ((663a5790-fa61-4dc7-ac70-4471a6f30628))
										- It can manage resources that weren't provisioned initially by it. ((6463499e-dc33-4af7-bbb7-33338a8a325b)) on the other hand has poor support for resources not provisioned through it
										- Larger ecosystem and third-party tooling
									- Similarities
									-
									- Unclear
										- Terraform uses HCL configuration language which is user-friendly and expressive. CloudFormation uses JSON or YAML, which can offer more readability and conciseness
										- Terraform maintains a state file to record state of your infrastructure. CloudFormation maintains state too but it's managed internally by AWS
								- ((663cee91-26d7-47ea-8989-ab0ed0b22869))
									- {{embed ((663cee91-26d7-47ea-8989-ab0ed0b22869))}}
						- Provision your AWS resources using templates.
						- Examples
							- [Lambda template](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/quickref-lambda.html)
								- JSON
								  collapsed:: true
									- ```json
									  {
									    "AWSTemplateFormatVersion": "2010-09-09",
									    "Parameters" : {
									      "ExistingSecurityGroups" : {
									        "Type" : "List<AWS::EC2::SecurityGroup::Id>"
									      },
									      "ExistingVPC" : {
									        "Type" : "AWS::EC2::VPC::Id",
									        "Description" : "The VPC ID that includes the security groups in the ExistingSecurityGroups parameter."
									      },
									      "InstanceType" : {
									        "Type" : "String",
									        "Default" : "t2.micro",
									        "AllowedValues" : ["t2.micro", "m1.small"]
									      }
									    },
									    "Mappings": {
									      "AWSInstanceType2Arch" : {
									        "t2.micro"    : { "Arch" : "HVM64"  },
									        "m1.small"    : { "Arch" : "HVM64"   }
									      },
									      
									      "AWSRegionArch2AMI" : {
									        "us-east-1"        : {"HVM64" : "ami-0ff8a91507f77f867", "HVMG2" : "ami-0a584ac55a7631c0c"},
									        "us-west-2"        : {"HVM64" : "ami-a0cfeed8", "HVMG2" : "ami-0e09505bc235aa82d"},
									        "us-west-1"        : {"HVM64" : "ami-0bdb828fd58c52235", "HVMG2" : "ami-066ee5fd4a9ef77f1"},
									        "eu-west-1"        : {"HVM64" : "ami-047bb4163c506cd98", "HVMG2" : "ami-0a7c483d527806435"},
									        "eu-central-1"     : {"HVM64" : "ami-0233214e13e500f77", "HVMG2" : "ami-06223d46a6d0661c7"},
									        "ap-northeast-1"   : {"HVM64" : "ami-06cd52961ce9f0d85", "HVMG2" : "ami-053cdd503598e4a9d"},
									        "ap-southeast-1"   : {"HVM64" : "ami-08569b978cc4dfa10", "HVMG2" : "ami-0be9df32ae9f92309"},
									        "ap-southeast-2"   : {"HVM64" : "ami-09b42976632b27e9b", "HVMG2" : "ami-0a9ce9fecc3d1daf8"},
									        "sa-east-1"        : {"HVM64" : "ami-07b14488da8ea02a0", "HVMG2" : "NOT_SUPPORTED"},
									        "cn-north-1"       : {"HVM64" : "ami-0a4eaf6c4454eda75", "HVMG2" : "NOT_SUPPORTED"}
									      }
									      
									    },
									    "Resources" : {
									      "SecurityGroup" : {
									        "Type" : "AWS::EC2::SecurityGroup",
									        "Properties" : {
									          "GroupDescription" : "Allow HTTP traffic to the host",
									          "VpcId" : {"Ref" : "ExistingVPC"},
									          "SecurityGroupIngress" : [{
									            "IpProtocol" : "tcp",
									            "FromPort" : 80,
									            "ToPort" : 80,
									            "CidrIp" : "0.0.0.0/0"
									          }],
									          "SecurityGroupEgress" : [{
									            "IpProtocol" : "tcp",
									            "FromPort" : 80,
									            "ToPort" : 80,
									            "CidrIp" : "0.0.0.0/0"
									          }]
									        }
									      },
									      "AllSecurityGroups": {
									        "Type": "Custom::Split",
									        "Properties": {
									          "ServiceToken": { "Fn::GetAtt" : ["AppendItemToListFunction", "Arn"] },
									          "List": { "Ref" : "ExistingSecurityGroups" },
									          "AppendedItem": { "Ref" : "SecurityGroup" }
									        }
									      },
									      "AppendItemToListFunction": {
									        "Type": "AWS::Lambda::Function",
									        "Properties": {
									          "Handler": "index.handler",
									          "Role": { "Fn::GetAtt" : ["LambdaExecutionRole", "Arn"] },
									          "Code": {
									            "ZipFile":  { "Fn::Join": ["", [
									              "var response = require('cfn-response');",
									              "exports.handler = function(event, context) {",
									              "   var responseData = {Value: event.ResourceProperties.List};",
									              "   responseData.Value.push(event.ResourceProperties.AppendedItem);",
									              "   response.send(event, context, response.SUCCESS, responseData);",
									              "};"
									            ]]}
									          },
									          "Runtime": "nodejs14.x"
									        }
									      },
									      "MyEC2Instance" : {
									        "Type" : "AWS::EC2::Instance",
									        "Properties" : {
									          "ImageId": { "Fn::FindInMap": [ "AWSRegionArch2AMI", { "Ref": "AWS::Region" }, { "Fn::FindInMap": [
									            "AWSInstanceType2Arch", { "Ref": "InstanceType" }, "Arch" ] } ]
									          },
									          "SecurityGroupIds" : { "Fn::GetAtt": [ "AllSecurityGroups", "Value" ] },
									          "InstanceType" : { "Ref" : "InstanceType" }
									        }
									      },
									      "LambdaExecutionRole": {
									        "Type": "AWS::IAM::Role",
									        "Properties": {
									          "AssumeRolePolicyDocument": {
									            "Version": "2012-10-17",
									            "Statement": [{ "Effect": "Allow", "Principal": {"Service": ["lambda.amazonaws.com"]}, "Action": ["sts:AssumeRole"] }]
									          },
									          "Path": "/",
									          "Policies": [{
									            "PolicyName": "root",
									            "PolicyDocument": {
									              "Version": "2012-10-17",
									              "Statement": [{ "Effect": "Allow", "Action": ["logs:*"], "Resource": "arn:aws:logs:*:*:*" }]
									            }
									          }]
									        }
									      }
									    },
									    "Outputs" : {
									      "AllSecurityGroups" : {
									        "Description" : "Security Groups that are associated with the EC2 instance",
									        "Value" : { "Fn::Join" : [ ", ", { "Fn::GetAtt": [ "AllSecurityGroups", "Value" ] }]}
									      }
									    }
									  }
									  ```
								- YAML
								  id:: 663cc66c-8008-43af-ad71-f62313f50b43
								  collapsed:: true
									- ```yaml
									  AWSTemplateFormatVersion: '2010-09-09'
									  Parameters:
									    ExistingSecurityGroups:
									      Type: List<AWS::EC2::SecurityGroup::Id>
									    ExistingVPC:
									      Type: AWS::EC2::VPC::Id
									      Description: The VPC ID that includes the security groups in the ExistingSecurityGroups
									        parameter.
									    InstanceType:
									      Type: String
									      Default: t2.micro
									      AllowedValues:
									      - t2.micro
									      - m1.small
									  Mappings:
									    AWSInstanceType2Arch:
									      t2.micro:
									        Arch: HVM64
									      m1.small:
									        Arch: HVM64
									        
									    AWSRegionArch2AMI:
									      us-east-1:
									        HVM64: ami-0ff8a91507f77f867
									        HVMG2: ami-0a584ac55a7631c0c
									      us-west-2:
									        HVM64: ami-a0cfeed8
									        HVMG2: ami-0e09505bc235aa82d
									      us-west-1:
									        HVM64: ami-0bdb828fd58c52235
									        HVMG2: ami-066ee5fd4a9ef77f1
									      eu-west-1:
									        HVM64: ami-047bb4163c506cd98
									        HVMG2: ami-0a7c483d527806435
									      eu-central-1:
									        HVM64: ami-0233214e13e500f77
									        HVMG2: ami-06223d46a6d0661c7
									      ap-northeast-1:
									        HVM64: ami-06cd52961ce9f0d85
									        HVMG2: ami-053cdd503598e4a9d
									      ap-southeast-1:
									        HVM64: ami-08569b978cc4dfa10
									        HVMG2: ami-0be9df32ae9f92309
									      ap-southeast-2:
									        HVM64: ami-09b42976632b27e9b
									        HVMG2: ami-0a9ce9fecc3d1daf8
									      sa-east-1:
									        HVM64: ami-07b14488da8ea02a0
									        HVMG2: NOT_SUPPORTED
									      cn-north-1:
									        HVM64: ami-0a4eaf6c4454eda75
									        HVMG2: NOT_SUPPORTED
									  Resources:
									    SecurityGroup:
									      Type: AWS::EC2::SecurityGroup
									      Properties:
									        GroupDescription: Allow HTTP traffic to the host
									        VpcId:
									          Ref: ExistingVPC
									        SecurityGroupIngress:
									        - IpProtocol: tcp
									          FromPort: 80
									          ToPort: 80
									          CidrIp: 0.0.0.0/0
									        SecurityGroupEgress:
									        - IpProtocol: tcp
									          FromPort: 80
									          ToPort: 80
									          CidrIp: 0.0.0.0/0
									    AllSecurityGroups:
									      Type: Custom::Split
									      Properties:
									        ServiceToken: !GetAtt AppendItemToListFunction.Arn
									        List:
									          Ref: ExistingSecurityGroups
									        AppendedItem:
									          Ref: SecurityGroup
									    AppendItemToListFunction:
									      Type: AWS::Lambda::Function
									      Properties:
									        Handler: index.handler
									        Role: !GetAtt LambdaExecutionRole.Arn
									        Code:
									          ZipFile: !Sub |
									            var response = require('cfn-response');
									            exports.handler = function(event, context) {
									               var responseData = {Value: event.ResourceProperties.List};
									               responseData.Value.push(event.ResourceProperties.AppendedItem);
									               response.send(event, context, response.SUCCESS, responseData);
									            };
									        Runtime: nodejs14.x
									    MyEC2Instance:
									      Type: AWS::EC2::Instance
									      Properties:
									        ImageId:
									          Fn::FindInMap:
									          - AWSRegionArch2AMI
									          - Ref: AWS::Region
									          - Fn::FindInMap:
									            - AWSInstanceType2Arch
									            - Ref: InstanceType
									            - Arch
									        SecurityGroupIds: !GetAtt AllSecurityGroups.Value
									        InstanceType:
									          Ref: InstanceType
									    LambdaExecutionRole:
									      Type: AWS::IAM::Role
									      Properties:
									        AssumeRolePolicyDocument:
									          Version: '2012-10-17'
									          Statement:
									          - Effect: Allow
									            Principal:
									              Service:
									              - lambda.amazonaws.com
									            Action:
									            - sts:AssumeRole
									        Path: "/"
									        Policies:
									        - PolicyName: root
									          PolicyDocument:
									            Version: '2012-10-17'
									            Statement:
									            - Effect: Allow
									              Action:
									              - logs:*
									              Resource: arn:aws:logs:*:*:*
									  Outputs:
									    AllSecurityGroups:
									      Description: Security Groups that are associated with the EC2 instance
									      Value:
									        Fn::Join:
									        - ", "
									        - Fn::GetAtt:
									          - AllSecurityGroups
									          - Value
									  ```
					- [AWS CloudTrail](https://aws.amazon.com/cloudtrail/)
					  id:: 6463499e-fe31-4613-8b61-e232816b6ddb
					  collapsed:: true
					  Track user activity and API usage
						- Track the usage history for your AWS resources by logging AWS API calls.
						- AWS Key Management Service provides audit trail information directly to AWS CloudTrail. These audit trails help you meet compliance and regulatory requirements by providing logs of who used which key to access which data and when that access occurred.
						- CloudTrail keeps a track of all API calls made in an AWS account and records the API caller's identity and source IP address, the time of the call, and other key information. CloudTrail records updated events 15 minutes after an API call is made. API calls are used in AWS for provisioning and managing resources. You can filter API calls in CloudTrail based on the date and time of the call, the user making the call, and the resources accessed by the call.
						- CloudTrail Insights is a CloudTrail feature that can be enabled for detecting unusual activity inside an AWS account. An example of such activity could be an unusually large number of EC2 instances launched in an account.
						- CloudTrail can save security logs indefinitely inside of 53 buckets and then further secured using tamper-proof technology like Vault Lock. This is useful for situations where an auditor needs to verify that your company’s database cannot be accessed from outside the company.
						- Monitoring is the process of watching a system, gathering its metrics, and analyzing them for taking key decisions and actions. Monitoring on AWS helps ensure that AWS resources are being utilized correctly and that the system is not running into any issues.
					- ((6544c9ef-05f1-41f8-8062-a6f5dc3cc6ad))
					- AWS Compute Optimiser
					  Identify optimal AWS Compute resources
					- [AWS Config](https://aws.amazon.com/config/)
					  id:: 663a5791-4799-4f97-a5f2-d2f5a78506c8
					  collapsed:: true
					  Track resources inventory and changes
						- View the current and previous configuration of your AWS resources, and monitor changes to your AWS resources.
						- It's for Compliance e.g. rules to ensure S3 buckets are tagged, that there's encryption, etc
					- AWS Control Tower
					  Set up and govern a secure, compliant multi-account environment
					- AWS Distro for OpenTelemetry
					  Secure, production-ready open-source distribution with predictable performance
					- AWS Launch Wizard
					  Easily size, configure and deploy 3rd-party applications on AWS
					- AWS License Manager
					  Track, manage and control licenses
					- AWS Managed Services
					  Infrastructure operations management for AWS
					- [AWS Management Console](https://aws.amazon.com/console/)
					  id:: 64b806d2-fdd2-4f63-84b8-4f0b76f20027
					  collapsed:: true
					  Web-based UI
						- [Docs](http://docs.aws.amazon.com/awsconsolehelpdocs/latest/gsg/getting-started.html)
						- Last read
						  https://docs.aws.amazon.com/awsconsolehelpdocs/latest/gsg/what-are-resource-groups.html
					- AWS Management Console Mobile App
					- AWS OpsWorks
					  collapsed:: true
					  Automate operations with Chef and Puppet
						- Configure and manage the environment for your application, whether in the AWS cloud or your own data center.
					- AWS Organisations
					  Central governance and management across AWS accounts
					- AWS Personal Health Dashboard
					  Personalised view of AWS service health
					- AWS Proton
					  Automate management for container and serverless deployments
					- AWS Resilience Hub
					  Prepare and protect your applications from disruptions
					- AWS Service Catalog
					  collapsed:: true
					  Create and use standardised products
						- Distribute servers, databases, websites, and applications to users using AWS resources.
					- AWS Service Management Connector
					  Provision, manage and operate AWS resources within Service Management Tools
					- [AWS Systems Manager](https://aws.amazon.com/systems-manager/)
					  id:: 64b80795-b0df-423c-a9f6-0b4e1cc37ff5
					  Gain operational insights and take action
						- Fleet Manager
						  id:: 661525a4-c9c5-4619-87c5-fe3e878f6760
							- SSM Agent
								- [It comes preinstalled on many AMIs including AlmaLinux, Amazon Linux, Ubuntu Server, etc](https://docs.aws.amazon.com/systems-manager/latest/userguide/ami-preinstalled-agent.html)
					- [AWS Trusted Advisor](https://aws.amazon.com/premiumsupport/technology/trusted-advisor/)
					  id:: 64b8079f-24fc-46b2-9015-d7bd15713de3
					  Optimise performance and security
						- Can monitor ((6463499e-ba62-451c-b295-387f10fcd780)) volumes, snapshots, provisioned input/output operations per second (lIOPS), and even magnetic volumes. It can also monitor ((6463499e-bd2d-4c48-b05b-bdddeb7d8bba)) components, Elastic IP addresses, and Reserved Instance limits. This tool helps implement best practices within your ((6463499e-bd2d-4c48-b05b-bdddeb7d8bba)) environment by advising on reducing costs, increasing system performance, and reducing security risks.
						  id:: 64ba5a3d-a4b6-483d-ac63-1accc15b8dd4
					- AWS Well-Architected Tool
					  id:: 64b807ad-09f4-4cc4-973b-76c953461e5a
					  Review and improve your workloads
				- ### Media Services
				  collapsed:: true
					- Amazon Elastic Transcoder
					  Easy-to-use scalable media transcoding
					- Amazon Interactive Video Service
					  Build engaging live stream experiences
					- Amazon Kinesis Video Streams
					  Process and analyse video streams
					- Amazon Nimble Studio
					  Accelerate content creation in the cloud
					- AWS Elemental Appliances and Software
					  On-premises media solutions
					- AWS Elemental MediaConnect
					  Reliable and secure live video transport
					- AWS Elemental MediaConvert
					  Convert file-based video content
					- AWS Elemental MediaLive
					  Convert live video content
					- AWS Elemental MediaPackage
					  Video origination and packaging
					- AWS Elemental MediaStore
					  Media storage and simple http origin
					- AWS Elemental MediaTailor
					  Video personalisation and monetisation
				- ### Migration & Transfer
				  collapsed:: true
					- AWS Application Migration Service (MGN)
					  Automate application migration and modernisation
					- AWS Application Discovery Service
					  Discover on-premises applications to streamline mgiration
					- AWS DMS
					  collapsed:: true
					  AKA Database Migration Service
						- https://eu-west-2.console.aws.amazon.com/dms/home?region=eu-west-2#
						- https://docs.aws.amazon.com/dms/latest/userguide/CHAP_GettingStarted.html#CHAP_GettingStarted.Welcome
					- AWS DataSync
					  Simple, fast, online data transfer
					- AWS Mainframe Modernisation
					  Migrate, modernise, operate and run mainframe workloads
					- AWS Migration Hub
					  Track migrations from a single place
					- AWS Transfer Family
					  Fully managed SFTP, FTPS, and FTP service
					- Migration Evaluator (formerly TSO Logic)
					  Create a business case for cloud migration
					- Related:
						- AWS Server Migration Service (high source prereqs)
						  collapsed:: true
						  [Page Not Found](https://console.aws.amazon.com/servermigration/home?region=eu-west-2)
							- Docs
							  https://docs.aws.amazon.com/server-migration-service/latest/userguide/server-migration.html
							- https://docs.aws.amazon.com/server-migration-service/latest/userguide/prereqs.html
							- Each server volume replicated is saved as a new Amazon Machine Image (AMI), which can be launched as an EC2 instance (virtual machine) in the AWS cloud.
							- Not available in London - deploy in Ireland then copy across regions
							  https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/CopyingAMIs.html#ami-copy-steps
				- ### Networking & Content Delivery
				  collapsed:: true
					- *Meta*
						- [AWS networking concepts](https://miparnisariblog.wordpress.com/2023/03/29/aws-networking-concepts/)
						  collapsed:: true
							- ![aws-networking-1.png](../assets/aws-networking-1_1698658431146_0.png)
					- [Amazon API Gateway](https://aws.amazon.com/api-gateway/)
					  id:: 6529032b-bb04-4660-836b-f33e1ae727ba
					  Build, deploy and manage APIs
						- Documentation
							- What
							  collapsed:: true
								- a fully managed service that makes it easy for developers to create, publish, maintain, monitor, and secure APIs at any scale. APIs act as the "front door" for applications to access data, business logic, or functionality from your backend services. Using API Gateway, you can create RESTful APIs and WebSocket APIs that enable real-time two-way communication applications. API Gateway supports containerized and serverless workloads, as well as web applications.
								  
								  API Gateway handles all the tasks involved in accepting and processing up to hundreds of thousands of concurrent API calls, including traffic management, CORS support, authorization and access control, throttling, monitoring, and API version management
							- API types
								- RESTful APIs
									- Meta
										- [Comparison](https://docs.aws.amazon.com/apigateway/latest/developerguide/http-api-vs-rest.html)
											- REST APIs and HTTP APIs are both RESTful API products. REST APIs support more features than HTTP APIs, while HTTP APIs are designed with minimal features so that they can be offered at a lower price. Choose REST APIs if you need features such as API keys, per-client throttling, request validation, AWS WAF integration, or private API endpoints. Choose HTTP APIs if you don't need the features included with REST APIs.
									- [HTTP APIs](https://docs.aws.amazon.com/apigateway/latest/developerguide/http-api.html)
									- [REST APIs](https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-rest-api.html)
									  Much more features
								- [WebSocket APIs](https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-websocket-api-overview.html)
							- ((64b806d2-fdd2-4f63-84b8-4f0b76f20027)) how-to
								- [Tutorial](https://docs.aws.amazon.com/apigateway/latest/developerguide/getting-started-rest-new-console.html) with ((6457bcad-7919-46a4-a9c0-8bb0ddf40189))
									- Intro
									  logseq.order-list-type:: number
									  collapsed:: true
										- First, you create a Lambda function using the Lambda console. Next, you create a REST API using the API Gateway REST API console. Then, you create an API method and integrate it with a Lambda function using a Lambda proxy integration. Finally, you deploy and invoke your API.
										  
										  When you invoke your REST API, API Gateway routes the request to your Lambda function. Lambda runs the function and returns a response to API Gateway. API Gateway then returns that response to you.
									- Create a Lambda function
									  logseq.order-list-type:: number
									  collapsed:: true
										- ((664dd5dd-4e6c-4ffd-a63e-b6a70b8a7416))
										- e.g. ((664c8afb-3f38-462c-820e-973f969a9a3a))
									- Create a REST API
									  logseq.order-list-type:: number
									  collapsed:: true
										- REST API > Build > New API
										- API endpoint type: `Regional`
									- Create a Lambda proxy integration
									  logseq.order-list-type:: number
									  collapsed:: true
										- In your API Gateway: select the `/` resource : `Create method`
										- For Method type, select ANY.
										  
										  For Integration type, select Lambda.
										  
										  Enable `Lambda proxy integration`
										  
										  For Lambda function, select the name of your newly created Lambda function
										- Choose Create method.
									- Deploy your API
									  logseq.order-list-type:: number
										- Next, you create an API deployment and associate it with a stage.
										- To deploy your API
											- Choose `Deploy API`.
											- For Stage, select New stage.
											- For Stage name, enter Prod.
											- (Optional) For Description, enter a description.
											- Choose Deploy.
										- Now clients can call your API. To test your API before deploying it, you can optionally choose the ANY method, navigate to the Test tab, and then choose Test.
									- Invoke your API
									  logseq.order-list-type:: number
										- From the main navigation pane, choose Stage.
										- Under Stage details, choose the copy icon to copy your API's invoke URL.
										- Enter the invoke URL in a web browser.
										  
										  The full URL should look like https://abcd123.execute-api.us-east-2.amazonaws.com/Prod.
										  
										  Your browser sends a GET request to the API.
										  
										  Verify your API's response. You should see the text "The API Gateway REST API console is great!" in your browser.
										-
							- ((6544c9ef-05f1-41f8-8062-a6f5dc3cc6ad)) how-to
						- [Learning Resources]
							- [Developer Guide](https://docs.aws.amazon.com/apigateway/latest/developerguide/welcome.html)
							- [API Reference](https://docs.aws.amazon.com/apigateway/latest/api/API_Operations.html)
						- Related: ((6648570e-7e6b-4513-8ddc-9f36dde4e403))
					- Amazon CloudFront
					  collapsed:: true
					  Global content delivery network
						- CloudFront
						  id:: 6463499e-2aac-4586-b149-63b9d1c9f1cd
						  collapsed:: true
							- https://aws.amazon.com/cloudfront/pricing/
							- A global content delivery network (CDN).
							- You store your content on an origin server, such as an Amazon S3 bucket or an HTTP server running on an EC2 instance. You create a CloudFront distribution, associate the distribution with the origin server, and then use a CloudFront URL to access your content:
							- http://distribution_id.cloudfront.net/file.ext
							- Alternatively, you can associate your own domain name with your CloudFront distribution.
							- When a user accesses an object that's part of a CloudFront distribution, CloudFront checks whether the object is already in a cache that's near the user. If it is, CloudFront serves the content from the cache; otherwise, CloudFront copies the requested content from the origin server to the cache.
					- Amazon Route 53
					  id:: 6463499e-fca2-4807-9bfe-2f64a56084d2
					  collapsed:: true
					  53 Scalable domain name system (DNS)
						- Routes traffic to your domain name to a resource, such as a virtual server or a load balancer.
						- DNS names
						  collapsed:: true
							- e.g. ec2-public_ip.region_code.compute.amazonaws.com
						- cli53 (https://github.com/barnybug/cli53) will allow you to export zones in zone file format.
						- Can download DNS Zone file via SES Domain management screen
						  http://i.imgur.com/GAZeiuc.png
					- [Amazon VPC](https://aws.amazon.com/vpc/)
					  id:: 6463499e-177d-4f57-a6c6-9c947d98a39a
					  collapsed:: true
					  Isolated cloud resources
						- Provides an isolated virtual network for your virtual servers.
						- VPCs and Subnets
							- VPCs are a virtual network dedicated to your AWS account. It is logically isolated from other virtual networks in the AWS cloud, providing security and robust networking functionality for your compute resources. A VPC closely resembles a traditional network that you'd operate in your own data center, with the benefits of using the scalable infrastructure of AWS.
							- A subnet is a segment of a VPC's IP address range that you can launch instances into. Subnets enable you to group instances based on your security and operational needs. To enable instances in a subnet to reach the Internet and AWS services, you must add an Internet gateway to the VPC and a route table with a route to the Internet to the subnet.
							- We recommend that you launch your EC2 instances into a VPC, either default one or nondefault
						- Security Groups
							- A security group acts as a virtual firewall for your instance to control inbound and outbound traffic. You can specify one or more security groups when you launch your instance. When you create a security group, you add rules that control the inbound traffic that's allowed, and a separate set of rules that control the outbound traffic. All other traffic is discarded. You can modify the rules for a security group at any time and the new rules are automatically enforced.
							- Stateful - which in this case means that requests sent from within the EC2 instance are allowed, regardless of any form of pre-specified inbound rule.
						- NACLs
						  AKA Network Access Control Lists
							- Stateless network component, which means data coming into an ((6463499e-bd2d-4c48-b05b-bdddeb7d8bba)) instance must be specifically allowed by creating the appropriate networking rule
						- Virtual Private Gateway (VPG)
							- To make a secure connection between an on-premises data center to a ((6463499e-177d-4f57-a6c6-9c947d98a39a)), you need to have a virtual private network (VPN) connection using a VPG.
							- Another dedicated connectivity option is ((64b80e82-4f75-432e-b04a-8d6ef2b72cbf))
						- 2 unique types of endpoints:
							- Gateway type endpoint
								- Does not require an Internet gateway and has a primary function to link communication between AWS services and your logical VPC. This particular endpoint only works with an ((6463499e-971f-49ad-9136-306a4377fe86)) and the ((6463499e-42ab-4a58-8911-df6138dfee8f)) services.
							- Interface type endpoint
								- Creates a private connection to AWS services on your side of the network that links your company resources to Amazon AWS using ((64b80e82-4f75-432e-b04a-8d6ef2b72cbf)). This type of endpoint uses more services than just ((6463499e-971f-49ad-9136-306a4377fe86)) and the ((6463499e-42ab-4a58-8911-df6138dfee8f)) services.
						- [AWS networking diagram](https://miparnisariblog.wordpress.com/2023/03/29/aws-networking-concepts/)
						  collapsed:: true
							- ![aws-networking-1.png](../assets/aws-networking-1_1690214033972_0.png){:height 725, :width 1188}
						- Related:
							- ((649d87bd-b447-4b9c-8883-bb8421140b89))
								- {{embed ((649d87bd-b447-4b9c-8883-bb8421140b89))}}
							- ((64a8146f-144f-4177-827c-83224b7f581c))
								- {{embed ((64a8146f-144f-4177-827c-83224b7f581c))}}
					- AWS App Mesh
					  Monitor and control microservices
					- AWS Cloud Map
					  Service discovery for cloud resources
					- [AWS Direct Connect](https://aws.amazon.com/directconnect/)
					  id:: 64b80e82-4f75-432e-b04a-8d6ef2b72cbf
					  collapsed:: true
					  Dedicated network connection to AWS
						- AWS Direct Connect, which allows for a dedicated high-speed fiber optic connection directly from a customer's data center to the AWS VPC. The advantages of using Direct Connect are reduced costs and higher throughput.
						- Private, physical fiber connection. Contact a local Direct Connect partner to set this up
					- AWS Global Accelerator
					  Improve global application availability and performance
					- AWS Private 5G
					  Easily deploy, manage and scale a private cellular network
					- AWS PrivateLink
					  Securely access services hosted on AWS
					- [AWS Transit Gateway](https://aws.amazon.com/transit-gateway/)
					  id:: 64b80fb8-db41-4dd8-9edd-b10a77a45104
					  collapsed:: true
					  Easily scale VPC and account connections
						- Alternatively, you can use these options for VPC to VPC connectivity:
							- ٠ VPC peering — AWS provides network connectivity between two VPCs. Transit Gateway scales much more easily when creating bigger networks
							- ٠ AWS Transit Gateway — AWS provides regional router connections between VPCs.
							- ٠ Software Site-to-Site VPN — VPN connections between VPCs using software appliances.
							- ٠ Software VPN-to-AWS Managed VPN - Connectivity between VPCs through software appliance to VPN connections.
							- ٠ AWS Managed VPN — Customer-managed VPC-to-VPC routing using IPSec VPN connections.
							- ٠ AWS PrivateLink — AWS uses interface endpoints to provide network connectivity between two VPCs.
					- AWS Verified Access (Preview)
					  Provide secure access to corporate applications without a VPN
					- AWS VPN
					  collapsed:: true
					  Securely access your network resources
						- [AWS VPN CloudHub](https://docs.aws.amazon.com/whitepapers/latest/aws-vpc-connectivity-options/aws-vpn-cloudhub.html)
						  id:: 64baba4c-1ea5-48a6-adb8-056e4591fda1
							- is a way of connecting local offices together in a specific networking configuration that is used as a primary network or a backup, depending on the architecture. The limitation with this is the level of Internet connectivity and upload and download speeds.
					- [AWS ELB](https://aws.amazon.com/elasticloadbalancing/)
					  id:: 6463499e-9ecf-4800-bf1f-65704c310016
					  collapsed:: true
					  AKA Elastic Load Balancing | Distribute incoming traffic across multiple targegts
						- https://eu-west-2.console.aws.amazon.com/ec2/v2/home?region=eu-west-2#LoadBalancers:
						- Info
							- Distributes network traffic across your set of virtual servers.
							- A load balancer distributes traffic to multiple instances. You can achieve even higher levels of fault tolerance by using your load balancer with instances in multiple Availability Zones. As instances are launched and terminated, the load balancer automatically directs traffic to the running instances. Elastic Load Balancing also performs health checks on each instance. If an instance is not responding, the load balancer can automatically redirect traffic to the healthy instances.
						- It acts as a barrier. It would hold the SSL certificate and EIP. The nginx/WordPress would be on port 80. And run on private address instead of EIP
						- It says it can balance the load across multiple EC2 instances as well
						  collapsed:: true
							- NFS shared filesystem
							  #Infrastructure-Containers https://workflowy.com/#/8281ea60abe9
							- rsync
							  https://serverfault.com/questions/683956/how-to-mirror-aws-ec2-instance-data
							- or container orchestration e.g. Rancher
							  #Infrastructure-Containers https://workflowy.com/#/8a01766881ce
						- Pricing
						  collapsed:: true
							- $21/month for full uptime
							- $0.0084 per GB of data processed by an Elastic Load Balancer
						- Load Balancer types:
							- [Application Load Balancer](https://aws.amazon.com/elasticloadbalancing/application-load-balancer/)
							  id:: 664c6a78-a3b6-4588-bc21-64a1b7d406b9
							- Network Load Balancer
							- Gateway Load Balancer
							- Classic Load Balancer
				- ### Quantum Technologies
				  collapsed:: true
					- Amazon Braket
					  Accelerate quantum computing research
				- ### Robotics
				  collapsed:: true
					- AWS RoboMaker
					  Develop, test, and deploy robotics applications
				- ### Satellite
				  collapsed:: true
					- AWS Ground Station
					  Fully managed ground station as a service
				- ### Security, Identity & Compliance
				  collapsed:: true
					- [Amazon Cognito](https://aws.amazon.com/cognito/)
					  id:: 6463499e-3bb4-49ea-90d5-2df420c0fb1e
					  collapsed:: true
					  Identity management for your apps
						- acts as a bridge between applications and AWS Services using ((224ff848-65b9-4eee-a3c5-f15131048264))
						  id:: 662a2de9-0665-42c2-916e-20503bb54acc
					- Amazon Detective
					  Investigate potential security issues
					- Amazon GuardDuty
					  Managed thread detection service
					- [Amazon Inspector](https://aws.amazon.com/inspector/)
					  id:: 64b81083-d55d-46c5-b58c-76342dc6a8ca
					  Automated and continual vulnerability management for Amazon EC2 and ((64b7f20b-d92b-49cc-a0ad-64e70eca6cff))
					- Amazon Macie
					  Discover and protect your sensitive data at scale
					- Amazon Security Lake (Preview)
					  Automatically centralise your security data with a few clicks
					- Amazon Verified Permissions (Preview)
					  Fine-grained permissions and authorisation for your applications
					- AWS Artifact
					  On-demand access to AWS' compliance reports
					- AWS Audit Manager
					  Continuously audit your AWS usage to simplify how you assess risk and compliance
					- AWS Certificate Manager
					  Manager Provision, manage, and deploy SSL/TLS certificates
					- AWS CloudHSM
					  Hardware-based key storage for regulatory compliance
					- AWS Directory Service
					  Host and manage active directory
					- AWS Firewall Manager
					  Central management of firewall rules
					- [AWS IAM Identity Center](https://aws.amazon.com/iam/identity-center)
					  Manage single sign-on access to AWS accounts and apps
					- [AWS IAM](https://aws.amazon.com/iam/)
					  id:: 64b81154-09ce-46c2-993a-0451497bcf3c
					  collapsed:: true
					  AKA Identity and Access Management | Securely manage access to services and resources
						- Policy types
						  id:: 6463499e-3cba-49b6-8dba-355fa353fe90
							- AWS inline policy
								- You would most commonly use an inline policy because it gives you the ability to control and maintain a strict correlation between the principal entity and the policy itself. When you use an inline policy, it limits the ability to make mistakes by accidentally attaching the wrong principal entity. It does this by associating the principal entity and the policy together so that when you delete the principal entity, the policy is also deleted.
							- AWS IAM user policy
								- This policy is for managing and administering AWS user access to the AWS infrastructure.
							- AWS bucket policy
								- You would use this type of policy for managing groups of users within ((6463499e-42ab-4a58-8911-df6138dfee8f)) rather than individual users.
							- AWS managed policy
								- AWS managed policy is not correct because this is a policy created by Amazon and is not a policy that is managed by the customer in any form.
						- Policy sections
						  id:: 64ba958e-226d-40bf-88ca-468dea441069
							- Effects e.g. Allow/Deny
							  collapsed:: true
								- Determines the behaviors and actions of what the policy will allow. You have to understand the effects of what occurs when a user might request access by either allowing or denying the request. Because the default option is to deny everything within the first type of requests, you have to grant specific permissions that you might need.
							- Actions - every AWS service consists of its own group of actions. If you do not specify an action, then those action options are always denied. This is a safeguard that protects the AWS infrastructure and is used as a separate security option.
								- e.g. `s3:GetObject`
							- Resources - this section is all about determining which resources are going to be associated with what actions.
							- IAM permission boundaries - these set permissions that limit users from doing anything outside of the dominion.
						- Visual policy editor
							- It'll ask for two key things: a Service, and an Action
						- User types
						- IAM user = a service, application or person
						- 4 types of principals which can request for an action/operation on an AWS resource:
							- Users
							- Role = allows for delegation so that services can gain access to other services
							- Federated Users = users from other sources such as Google accounts, Facebook, Amazon etc
							- Applications = these can also be identities
						- Service Control Policies (SCPs)
							- They limit the available permissions, they do not grant permissions
							- Basically a blacklist, unlike the whitelist approach of users/roles/groups
						- When accessing AWS via CLI you must use an access key rather than username + password
						- Multi-Factor Authentication
						  collapsed:: true
							- What if access code inaccessible?
								- If the authentication device associated with the AWS root account is damaged, lost, stolen, or stops working, you can contact us for help with disabling AWS MFA for the root account. This allows you to temporarily sign in to AWS using just the user name and password for the AWS account.
								- With virtual and hardware MFA, if your IAM users lose or damage their authentication device or if it is stolen or stops working, you can disable AWS MFA yourself using the IAM console or the AWS CLI. With SMS MFA, there is no disruption to MFA if you acquire a new mobile phone that retains the same phone number.
						- ((64b81161-baf7-46dc-ab13-4755b196d0fb))
						  id:: 6463499e-c1e7-44b4-91da-76dcbee8ca27
						- [Amazon Resource Names (ARNs) and AWS Service Namespaces](https://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html)
						  collapsed:: true
							- My
								- PMM Account Id: 447801116223
								- London: eu-west-2
							- arn:partition:service:region:account:resource
								- Where:
									- partition identifies the partition that the resource is in. For standard AWS regions, the partition is aws. If you have resourses in other partitions, the partition is aws-partitionname. For example, the partition for resources in the China (Beijing) region is aws-cn.
									- service identifies the AWS product. For ((64b81154-09ce-46c2-993a-0451497bcf3c)) resources, this is always `iam`.
									- region is the region the resource resides in. For IAM resources, this is always left blank.
									- account is the AWS account ID with no hyphens (for example, 123456789012).
									- resource is the portion that identifies the specific resource by name.
							- IAM Policies/permissions
							  collapsed:: true
								- Example
									- arn:aws:iam::447801116223:policy/1EBSmanagement
									- arn:aws:iam::447801116223:policy/1View_RDS-CW$serviceLevelSummary
									- Giving permissions for EC2
									  https://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html#arn-syntax-ec2
										- arn:aws:ec2:eu-west-2:447801116223:volume/*
											- arn:aws:ec2:eu-west-2:447801116223:volume/vol-0cf2e69a28bac6033
										- arn:aws:ec2:eu-west-2:447801116223:instance/*
										- arn:aws:ec2:eu-west-2:447801116223:security-group/*
							- Amazon Resource Names (ARNs)
							  id:: 6613fb1f-5b00-4a13-9958-7a99505c0403
					- [AWS KMS](https://aws.amazon.com/kms/)
					  id:: 64b81161-baf7-46dc-ab13-4755b196d0fb
					  collapsed:: true
					  AKA Key Management Service | Managed creation and control of encryption keys
						- [Docs](https://docs.aws.amazon.com/kms/)
							- Concepts
								- [KMS keys](https://docs.aws.amazon.com/kms/latest/developerguide/concepts.html#kms_keys)
								  id:: 654a39ef-23d1-4d89-811c-b7ad6c69c60e
								  AKA AWS KMS keys
								- *Types of KMS keys sorted by creation/ownership*
									- [Customer managed keys](https://docs.aws.amazon.com/kms/latest/developerguide/concepts.html#customer-cmk)
									  Keys that you create
									- [AWS managed keys](https://docs.aws.amazon.com/kms/latest/developerguide/concepts.html#aws-managed-cmk)
									  Keys that AWS services create in your account
									- [AWS owned keys](https://docs.aws.amazon.com/kms/latest/developerguide/concepts.html#aws-owned-cmk)
									  An AWS service owns and manages for use in multiple AWS accounts
								- Types of KMS keys sorted by encryption
									- [Symmetric encryption KMS keys](https://docs.aws.amazon.com/kms/latest/developerguide/concepts.html#symmetric-cmks)
									- [Asymetric KMS keys](https://docs.aws.amazon.com/kms/latest/developerguide/concepts.html#asymmetric-keys-concept)
									-
								- [Envelope encryption](https://docs.aws.amazon.com/kms/latest/developerguide/concepts.html#enveloping)
								  collapsed:: true
									- Envelope encryption is the practice of encrypting plaintext data with a data key, and then encrypting the data key under another key.
									- You can even encrypt the data encryption key under another encryption key, and encrypt that encryption key under another encryption key. But, eventually, one key must remain in plaintext so you can decrypt the keys and your data. This top-level plaintext key encryption key is known as the root key.
									- ![image.png](../assets/image_1699363414628_0.png)
									-
						- [How to import a key for AWS KMS](http://docs.aws.amazon.com/kms/latest/developerguide/importing-keys-create-cmk.html)
					- AWS Network Firewall
					  Deploy network security across your Amazon VPCs with just a few clicks
					- AWS Resource Access Manager
					  Simple, secure service to share AWS resources
					- AWS Secrets Manager
					  Rotate, manage and retrieve secrets
					- AWS Security Hub
					  Unified security and compliance center
					- AWS Shield
					  Protect vs DDoS attacks
					- AWS WAF
					  collapsed:: true
					  AKA Web Application Firewall | Filter malicious web traffic
						- collapsed:: true
						  1. What is AWS WAF?
							- AWS WAF is a web application firewall that helps protect web applications from attacks by allowing you to configure rules that allow, block, or monitor (count) web requests based on conditions that you define. These conditions include IP addresses, HTTP headers, HTTP body, URI strings, SQL injection and cross-site scripting.
						- How does AWS WAF protect my web site or application?
						  collapsed:: true
							- AWS WAF is tightly integrated with Amazon CloudFront and the Application Load Balancer (ALB), services that AWS customers commonly use to deliver content for their websites and applications. When you use AWS WAF on Amazon CloudFront, your rules run in all AWS Edge Locations, located around the world close to your end users. This means security doesn’t come at the expense of performance. Blocked requests are stopped before they reach your web servers. When you use AWS WAF on Application Load Balancer, your rules run in region and can be used to protect internet-facing as well as internal load balancers.
						- preconfigured rules
						  https://aws.amazon.com/waf/preconfiguredrules/
						- _See_
						  collapsed:: true
							- CloudFront
							  intralink2:: https://workflowy.com/#/9851d5af48e3
							- ((6463499e-9ecf-4800-bf1f-65704c310016))
				- ### Storage
				  collapsed:: true
					- [Amazon EBS](https://aws.amazon.com/ebs/)
					  id:: 6463499e-ba62-451c-b295-387f10fcd780
					  collapsed:: true
					  AKA Amazon Elastic Block Store | EC2 block storage volumes
						- provides network-attached storage (NAS) for use with your EC2 instances.
						- You can back up the data on your Amazon EBS volumes by creating snapshots, which are stored in Amazon S3. You can create a new Amazon EBS volume from a snapshot and then attach it to an EC2 instance.
						- Annual failure rate (complete loss) around 0.5%
						  collapsed:: true
							- The durability of your volume depends both on the size of your volume and the percentage of the data that has changed since your last snapshot. As an example, volumes that operate with 20 GB or less of modified data since their most recent Amazon EBS Snapshot can expect an annual failure rate (AFR) of between 0.1% – 0.5%, where failure refers to a complete loss of the volume. This compares with commodity hard disks that typically fail with an AFR of around 4%, making EBS volumes 10 times more reliable than typical commodity disk drives.
						- Snapshots are deltas
						  collapsed:: true
							- Amazon EBS Snapshots are stored incrementally: only the blocks that have changed after your last snapshot are saved, and you are billed only for the changed blocks. If you have a device with 100 GB of data but only 5 GB has changed after your last snapshot, a subsequent snapshot consumes only 5 additional GB and you are billed only for the additional 5 GB of snapshot storage, even though both the earlier and later snapshots appear complete.
							- Here is why you may stay secure when you delete one of your snapshots:
							  collapsed:: true
								- When you delete a snapshot, you remove only the data not needed by any other snapshot. All active snapshots contain all the information needed to restore the volume to the instant at which that snapshot was taken. The time to restore changed data to the working volume is the same for all snapshots.
					- [Amazon EFS](https://aws.amazon.com/efs/)
					  id:: 63a06e59-4078-4357-b478-dda42326daf4
					  AKA Elastic File System | Fully managed file system for EC2
					- Amazon FSx
					  Launch, run and scale feature-rich and highly-performant file systems with just a few clicks
					- Amazon S3 Glacier
					  collapsed:: true
					  Low-cost archive storage in the cloud
						- Low-cost archival storage.
						- Related: GCS Archive Storage. 1/3 the cost of glacier for storage ($0.0012/GB/Month lol), but more for retrieval. Has none of the annoyances of Glacier (you can download your files instantly, upload using normal APIs). Perfect for extremely cheap backups.
					- [Amazon S3](https://aws.amazon.com/s3)
					  id:: 6463499e-42ab-4a58-8911-df6138dfee8f
					  collapsed:: true
					  AKA Simple Storage Service | Object storage
						- Cons
							- Versioning can't be adjust for a time range (e.g. CrashPlan allows versioning over 1 week to be every 8 hours; after 1 week keep a version every day; after 90 days keep a version every week, after one year keep a version every month; remove deleted files every 6 months)
							  collapsed:: true
								- http://i.imgur.com/1aQd5ph.png
								- In Jan 2019 realised my current 8GB Titanium backup was now 160GB versioned
						- Features
						  id:: 6463499e-8216-4942-bd04-14d71330b7d6
						  collapsed:: true
							- It provides strong read-after-write consistency
							  id:: 7784e272-9ed7-43e2-bab4-a97b9ca6e46e
								- This means that whenever a new object is written or an existing object is deleted or overwritten, future read requests always get the newest version of the object. Additionally, list operations have strong consistency in Amazon S3. This ensures that you can perform a listing after a write operation and all changes that were done by the write operation will be displayed correctly.
							- Data is replicated to other AZs within the same Region
							- Bucket name CANNOT be changed after it has been created
							- You cannot use underscores or uppercase letters in bucket names
							- It can hold an unlimited amount of data
							- Max object size is 5 TB
							- Each object has a specific URL
							- Objects are private by default but can be changed to public
							- [Amazon S3 data lake](https://aws.amazon.com/big-data/datalakes-and-analytics/datalakes/)
							  id:: 64ba94e3-5952-4b86-ae72-5b57fb0092c2
								- When using the Amazon Simple Storage Service (S3) data lake, you utilize a broad perspective of data science, data analytics, and machine learning (ML), all in a centralized platform. It gives you the ability to house large amounts of data from a number of different resources in one central location. You can create unique catalogs and utilize tools to analyze, monitor, and focus on unique data patterns. You can also efficiently use other tools that might be needed in the future for data processing.
							- Bucket policies
								- Using a custom prefix can limit access to a specific object
								- A bucket policy can set limits for an IP address range, a custom prefix for certain objects, and an AWS
								  account. These limitations use JSON-based access policy rules for implementation, and the actual bucket policy
								  cannot be larger than 20 KB in size.
								- The Amazon S3 bucket policy cannot be limited to a company stock ticker or a network subnet. However, the limitation can work with IP address ranges, which would include network subnets.
						- ((64a284d3-ae41-4642-9112-1a99c4ea5d59))
							- {{embed ((64a284d3-ae41-4642-9112-1a99c4ea5d59))}}
						- Example URL
						  https://domain/bucket_name/object_key
						- ((6544c9ef-05f1-41f8-8062-a6f5dc3cc6ad)) usage
							- `get-bucket-notification-configuration`
						- Documentation
							- S3 Event Notifications
							  collapsed:: true
								- Tips
									- Make sure to enable `s3:ObjectCreated:CompleteMultipartUpload` if trying to copy/upload files bigger than 10MB (not sure the cutoff but it's less than 1GB). It won't trigger `s3:ObjectCreated:Put`, nor `s3:ObjectCreated:Post`, nor `s3:ObjectCreated:Copy`
									- If copying large files rather than uploading them into a bucket it'll trigger event notifications if you copy over into the same bucket to Lambda, but not to SQS. Best practice is to instead have a second bucket from which you copy files into the first bucket for testing (also might need to delete the originals in first bucket each time)
					- AWS Backup
					  Centralised backup across AWS services
					- AWS Snow Family
					  Physical edge computing and storage devices for rugged or disconnected environments
					- AWS Storage Gateway
					  Hybrid storage integration
					- AWS Elastic Disaster Recovery (DRS)
					  Scalable, cost-effective application recovery to AWS
				- Unsorted
					- [AWS Nitro System](https://aws.amazon.com/ec2/nitro/) - ((6463499e-bd2d-4c48-b05b-bdddeb7d8bba))
					  collapsed:: true
						- Components
							- Nitro Cards
							- Nitro Security Chip
							- Nitro Hypervisor
							- [AWS Nitro Enclaves](https://aws.amazon.com/ec2/nitro/nitro-enclaves/)
							  id:: 654a3c6b-660d-401f-b707-0dff67e75c41
							  collapsed:: true
							  CPU and memory isolation for ((6463499e-bd2d-4c48-b05b-bdddeb7d8bba)) instances
								- Pros/Cons
									- Pros
										- Theoretical privacy even from AWS (vendor) admins
										- Usecases
											- Securing private keys
											  collapsed:: true
												- Customers can now isolate and use private keys (e.g. SSL/TLS) in an enclave, while preventing users, applications, and libraries on the parent instance from viewing those keys. Normally, these private keys are stored on the EC2 instance in plain text.
												- [AWS Certificate Manager (ACM) for Nitro Enclaves](https://docs.aws.amazon.com/enclaves/latest/user/nitro-enclave-refapp.html) is an enclave application that allows you to use public and private SSL/TLS certificates with your web applications and servers running on Amazon EC2 instances with AWS Nitro Enclaves.
											- Tokenisation
											  collapsed:: true
												- Tokenization is a process that converts highly sensitive data such as credit card numbers or health care data into a token. With Nitro Enclaves, customers can run the application that does this conversion inside an enclave. Encrypted data can be sent to the enclave, where it is decrypted and then processed. The parent EC2 instance will not be able to view or access the sensitive data throughout this process.
											- Multi-party computation
											  collapsed:: true
												- Using the cryptographic attestation capability of Nitro Enclaves, customers can set up multi-party computation, where several parties can join and process highly sensitive data without having to disclose or share the actual data to each individual party. Multi-party computation can also be done within the same organization to establish separation of duties.
									- Cons
										-
									- Unclear
									- Comparisons
								- Documentation
									- What are they
									  collapsed:: true
										- Separate virtual machines - not a container, independent kernel using a lightweight Linux OS
										- Limitations - no external networking (just a local virtual socket ([vsock](http://man7.org/linux/man-pages/man7/vsock.7.html)) connection to host), no persistent storage, no interactive access for administrators or operators
										- Cryographic attestation means that you can ensure the enclave is running the software you want it to
											- The Nitro Hypervisor creates and then signs an attestation document as it creates each Nitro Enclave. The document contains (among other things), a set of Platform Configuration Registers (PCRs) that provide a cryptographically sound measurement of the boot process. These values, when attached to a KMS key policy, are used to verify that the expected image, OS, application, IAM role, and instance ID were used to create the enclave. After KMS has performed this verification step, it will perform the desired API action (decrypt, generate data key, or generate random value) requested by the code running in the enclave.
										- Used EIFs (Enclave Image Files) which are built from Dockerfiles
										- ((64b81161-baf7-46dc-ab13-4755b196d0fb)) can read attestation documents sent from the enclave to verify
									- [Nitro-CLI](https://github.com/aws/aws-nitro-enclaves-cli)
									  id:: 654a675d-1db3-4701-b640-154b8a330f79
									- [GitHub - aws/aws-nitro-enclaves-acm: AWS Certificate Manager for Nitro Enclaves allows the use of public and private SSL/TLS certificates with web applications and web servers running on Amazon EC2 instances with AWS Nitro Enclaves.](https://github.com/aws/aws-nitro-enclaves-acm)
										- [Nitro Enclaves application: AWS Certificate Manager for Nitro Enclaves - AWS](https://docs.aws.amazon.com/enclaves/latest/user/nitro-enclave-refapp.html)
									- [Docs](https://docs.aws.amazon.com/enclaves/latest/user/nitro-enclave.html)
									- How to deploy
									  collapsed:: true
										- 1) Launch a compatible Nitro-based EC2 instance with the `EnclaveOptions` parameter set to `true`
											- `aws ec2 run-instances ...  --enclave-options Enabled=true`
										- 2) Use the ((654a675d-1db3-4701-b640-154b8a330f79)) to convert your application from a Docker image to an enclave image file (`*.eif`)
											- e.g. `nitro-cli build-enclave --docker-uri hello:latest --output-file hello.eif`
										- 3) Using the EIF file as an input use the Nitro CLI to create an enclave
										-
									- [AWS Nitro Enclaves Workshop](https://catalog.workshops.aws/nitro-enclaves/en-US)
										- [GitHub - aws-samples/aws-nitro-enclaves-workshop: AWS Nitro Enclaves Workshop](https://github.com/aws-samples/aws-nitro-enclaves-workshop)
								- Ecosystem
									- [Edgebit Enclaver](https://edgebit.io/enclaver/)
									  id:: 6617d584-74d9-4f9a-bf0a-d36269cfb5f7
									  collapsed:: true
										- [GitHub - edgebitio/enclaver: Open source toolkit created to enable easy adoption of software enclaves](https://github.com/edgebitio/enclaver)
										-
								- Release date
									- Found an Amazon press release about it now being 36% faster in Dec 2019
							- NitroTPM
							  Conforms to TPM 2.0. Used for TPM attestation, cryptographic offload
					- [AWS SAM](https://aws.amazon.com/serverless/sam/)
					  id:: 6620d4c0-1c5f-4f16-bfee-cf33e7cf5ffd
					  collapsed:: true
					  AKA AWS Serverless Application Model
						- # Pros/Cons
						  id:: 663a5791-b96a-405b-8f8c-aa03a8dc946e
							- Pros
								-
							- Cons
								-
							- Unclear
							- Upstream/Downstream Pros/Cons
							- Comparisons
								- ((6620d4c0-1c5f-4f16-bfee-cf33e7cf5ffd)) vs [LocalStack](https://www.localstack.cloud/)
								  id:: 663e2b42-c666-4269-ba2b-ea23aab4e21d
									- For ((6620d4c0-1c5f-4f16-bfee-cf33e7cf5ffd))
									- For LocalStack
									- Similarities
										- Both released in 2017
									- Unclear
									- [GitHub - localstack/localstack: 💻 A fully functional local AWS cloud stack. Develop and test your cloud & Serverless apps offline](https://github.com/localstack/localstack)
									-
						- # How it works
							- AWS SAM consists of two parts, AWS SAM templates and the AWS SAM Command Line Interface (AWS SAM CLI).
								- AWS SAM templates provide a short-hand syntax, optimized for defining Infrastructure as Code (IaC) for serverless applications. An extension of ((6463499e-dc33-4af7-bbb7-33338a8a325b)), you deploy AWS SAM templates directly to ((6463499e-dc33-4af7-bbb7-33338a8a325b)), benefiting from its extensive IaC support on AWS.
								- The AWS SAM CLI is a developer tool that puts AWS SAM features at your fingertips. Use it to quickly create, develop, and deploy serverless applications.
								- Some of the many features of AWS SAM include SAM Accelerate, which speeds up local development and cloud testing, and SAM CLI integrations, extending AWS SAM to other tools such as the AWS CDK and Terraform.
						- An email I got said they wanted to build an AWS SAM clone and thus wanted "reusable microservice RESTful API framework providing authentication, authorisation, auditing and row-level security, leaving you to develop your application as Lambda functions"
						- CLI: sam build
						- # Docs for work
						  id:: 663c9df7-3979-42ee-9d86-2d453f96c946
							- ## Email notes
								- AWS CloudFormation (CF), AWS Server Application Model (SAM), AWS Cloud Development Kit (CDK), Terraform by Hashicorp and Cloud Development Kit for Terraform (CDKTF, an AWS + Hashicorp joint project) will be analysed here.
									- | Software | AWS CF | AWS SAM | AWS CDK | CDKTF | Terraform | Pulumi |
									  ---
									  | Provision AWS resources | Yes | Only serverless (e.g. Lambda) | Yes | Yes | Yes | Yes |
									  | Provision GCP, Azure, etc resources | No | No | No | Yes | Yes | Yes |
									  | GitHub Stars | N/A | 9k | 11k | 5k | 41k | 20k |
									  | 3rd-party Ecosystem | [Medium](https://github.com/aws-cloudformation/awesome-cloudformation) | Small | [Medium](https://github.com/kalaiser/awesome-cdk) | [Medium](https://github.com/kalaiser/awesome-cdk) | [Large](https://github.com/shuaibiyy/awesome-tf) | [Medium](https://github.com/pulumiverse/awesome-pulumi) |
									  | Deep AWS Integration | Yes | Yes | Yes | No | No | No |
									  | Language Support | JSON, YAML | YAML | 6 (incl TypeScript, JavaScript, C#, etc) | 6 | HCL | 10 (incl all .NET, YAML, etc) | 
									  | Verbosity | High | Low | Low | Low | Medium | ? |
									  | Initial Release | 2011 | 2016 | 2019 | 2022 | 2014 | 2017 |
									- Further Analysis
									- CDK ecosystem
										- Whilst CDK software are the newest options they also offer several significant advantages over most of the alternatives:
											- * They offer both deep integration with AWS via AWS CDK, as well as cloud-agnosticism via CDKTF
											- * CDK allows using general-purpose programming languages such as TypeScript, JavaScript, C#, Java, etc rather than the limited configuration languages used in CF's JSON or YAML, or Terraform's domain-specific language HCL. This allows for autocomplete in IDEs, control flow statements, reusable components, compile-time warnings, types, integration with much larger ecosystem of tooling, better testing, etc. And also GPLs are [preferable to DSLs](https://leebriggs.co.uk/blog/2023/09/04/dsl)
											- * CDK lets you write code in a more concise and powerful language, whilst on the backend it transpiles to rigorously tested templates which deploy the resources (YAML for CF if you're using AWS CDK or HCL for Terraform if you're using CDKTF).
										- TypeScript in particular seems to be best language to use with CDK because:
											- * CDK is powered by jsii, which transpiles code into JavaScript classes. Using a JavaScript dialect is therefore least likely to result in errors, and it's the best supported
											- * It supports types, which helps reduce errors and saves time debugging
											- * Our front end will be written in React and thus JavaScript or TypeScript also
										- AWS CDK in particular looks like the best choice of CDK for our usecase as we're building solely on AWS. The closest alternative is Pulumi which looks quite similar to CDK, but according to [even a Pulumi employee](https://leebriggs.co.uk/blog/2022/08/26/choosing-an-iac-tool) if you're only looking for AWS support then AWS CDK is sufficient for your usecase so it wasn't analysed further.
									- AWS SAM
										- This is a stack that offers several features that make provisioning certain AWS resources quicker and easier than AWS CF.
										- The first part is SAM transform, which is an CF macro that transforms SAM templates into CF templates. This allows you to write much more concise templates (at least 50% less code) which can deploy the same resources that a regular CF template would. Additionally it supports deep integration with Lambda by allowing configuration of environment variables, event sources, etc within the template. If we choose to use CDK then we won't need to use this part however, as AWS CDK offers similar conciseness and AWS integration with it's own transpiling to CF templates.
										- The second part is AWS SAM CLI, which provides tooling for local development, debugging, building, packaging and deployment for serverless applications. This has a local development environment powered by Docker for speeding up the development cycle for serverless applications, using `sam local` to run Lambda functions locally. It also has built-in deployment commands for serverless apps which handles zipping source code, uploading it to S3, creating IAM roles, deploying the CF stack, etc. This is much simpler than using CF directly. If we use CDK then this is the part that we'd still want to utilise, as including it in our framework helps to make serverless developers much more productive by allowing them to quickly iterate on serverless applications.
										- The main limitations of SAM however are that this more concise syntax only supports a few serverless resources, and that the local dev environment only supports Lambda. In contrast CDK offers conciseness for all resources, and there is another tool which can do local dev environments better.
									- LocalStack
										- This is an AWS SAM CLI alternative that [supports much more AWS services](https://docs.localstack.cloud/user-guide/aws/feature-coverage/) for the `sam local` command (i.e. running a local dev environment via Docker). It's support varies across each AWS service but generally they all have at least got minimal CRUD API support. The main differentiator is that AWS SAM CLI in comparison only supports Lambda functions locally. More comprehensive testing will be needed into LocalStack if we are to integrate it, but my initial thoughts are that either AWS SAM CLI or LocalStack should be included in our framework as they improve productivity for developers who use our framework.
							- # Repos
								- [GitHub - aws/serverless-application-model: The AWS Serverless Application Model (AWS SAM) transform is a AWS CloudFormation macro that transforms SAM templates into CloudFormation templates.](https://github.com/aws/serverless-application-model)
								- [GitHub - aws/aws-sam-build-images: AWS SAM build images](https://github.com/aws/aws-sam-build-images)
								- [aws-sam-cli-app-templates](https://github.com/aws/aws-sam-cli-app-templates)
								  id:: 663c9e43-344d-4138-9576-46d803ed93b2
								  Prebuilt templates for common usecases
								- [aws-sam-cli](https://github.com/aws/aws-sam-cli)
								  id:: 663c9e51-4706-42af-a785-973914c1a56d
								  collapsed:: true
								  CLI tool to build, test, debug, and deploy Serverless applications using AWS SAM
									- Installation
										-
									- Configuration
										-
							- # Docs
								- https://docs.aws.amazon.com/serverless-application-model/index.html
								- [AWS SAM CLI command reference](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-sam-cli-command-reference.html)
							- # Questions
								- What is SAM transform
									- Shorthand syntax used to generate ((6463499e-dc33-4af7-bbb7-33338a8a325b)) templates
							- # Notes
								- Workflows include build, package and test using ((6463499e-dc33-4af7-bbb7-33338a8a325b))
								- ((663c9e51-4706-42af-a785-973914c1a56d)) helps build and package it for all supported ((6457bcad-7919-46a4-a9c0-8bb0ddf40189)) runtimes
								- Test apps locally with ((663c9e51-4706-42af-a785-973914c1a56d)), which also supports ((64b7f615-66b0-4272-83e0-90ebbce92b48)) and ((638d061d-e696-4f04-933c-35f8836e125d))
								- Or use SAM Accelerate to test changes directly in the cloud without waiting for a full deployment
								- SAM pipelines create production-ready apps with many popular ((6463499d-76db-4797-a83f-4b9b7439743a)) tools
								- [AWS SAM Tutorial (with a Lambda Example!) - YouTube](https://youtu.be/MipjLaTp5nA)
								  collapsed:: true
									- Links
										- Code - [github.com/beabetterdevv/sam-app](https://github.com/beabetterdevv/sam-app)
										- How to install the AWS CLI - [youtube.com/watch?v=jCHOsMPbcV0&t=0s](https://www.youtube.com/watch?v=jCHOsMPbcV0&t=0s)
										- How to install Docker - [youtube.com/watch?v=rZbzvKMPFsY&t=0s](https://www.youtube.com/watch?v=rZbzvKMPFsY&t=0s)
										- What is CloudFormation? - [youtube.com/watch?v=0Sh9OySCyb4&t=0s](https://www.youtube.com/watch?v=0Sh9OySCyb4&t=0s)
										- CloudFormation Step by Step Tutorial - [youtube.com/watch?v=YXVCdGyHDSk&t=0s](https://www.youtube.com/watch?v=YXVCdGyHDSk&t=0s)
									- Example template
										- [`template.yaml`](https://github.com/beabetterdevv/sam-app/blob/master/template.yaml)
										  id:: 663cc079-aaae-47b6-a093-e692708959c9
										  collapsed:: true
											- ```yaml
											  AWSTemplateFormatVersion: '2010-09-09'
											  Transform: AWS::Serverless-2016-10-31
											  Description: >
											    sam-app
											  
											  Resources:
											    HelloWorldFunction:
											      Type: AWS::Serverless::Function 
											      Properties:
											        CodeUri: hello_world/
											        Handler: app.lambda_handler
											        Runtime: python3.8
											        Events:
											          HelloWorld:
											            Type: Api 
											            Properties:
											              Path: /helloWorld
											              Method: get
											  
											  Outputs:
											    HelloWorldApi:
											      Description: "API Gateway endpoint URL for Prod stage for Hello World function"
											      Value: !Sub "https://${ServerlessRestApi}.execute-api.${AWS::Region}.amazonaws.com/Prod/hello/"
											    HelloWorldFunction:
											      Description: "Hello World Lambda Function ARN"
											      Value: !GetAtt HelloWorldFunction.Arn
											    HelloWorldFunctionIamRole:
											      Description: "Implicit IAM Role created for Hello World function"
											      Value: !GetAtt HelloWorldFunctionRole.Arn
											  ```
										- 2
										  collapsed:: true
											- ```yaml
											  AWSTemplateFormatVersion: '2010-09-09'
											  Transform: AWS::Serverless-2016-10-31
											  Resources:
											  	CreateThumbnail:
											      	Type: AWS::Serverless::Function
											          Properties:
											          	Handler: handler
											              Runtime: runtime
											              Timeout: 60
											              Policies: AWSLambdaExecute
											              Events:
											              	CreateThumbnailEvent:
											                  	Type: S3
											                      Properties:
											                      	Bucket: !Ref SrcBucket
											                          Events: s3:ObjectCreated:*
											  
											  	SrcBucket: 
											      	Type: AWS::S£::Bucket
											  ```
										- It looks pretty similar to normal ((6463499e-dc33-4af7-bbb7-33338a8a325b)) : ((663cc66c-8008-43af-ad71-f62313f50b43))
									- Pre-requisites:
										- Install ((6544c9ef-05f1-41f8-8062-a6f5dc3cc6ad))
											- Test it's installed by using the command `aws`
										- Configure ((6544c9ef-05f1-41f8-8062-a6f5dc3cc6ad))
											- `aws configure` = this creates a config file in `~/.aws/config` ?
										- Install SAM
											- Test it's installed by using the command `sam`
										- Install Docker (if you wish to develop locally)
									- Steps
										- ((663cc079-aaae-47b6-a093-e692708959c9)) will create an ((6529032b-bb04-4660-836b-f33e1ae727ba)) + ((6457bcad-7919-46a4-a9c0-8bb0ddf40189))
										- `sam build`
										  This will pull down all the dependencies defined for your code (e.g. ((6457bcad-7919-46a4-a9c0-8bb0ddf40189)) Python modules) and compile it
										- `sam deploy --guided`
											- For our first time use the `--guided` flag as this will ask some one-off questions
												- Stack Name (default: `sam-app`)
												- AWS Region:
												- Confirm changes before deploy (default: `N`). Recommended to change to `y` because it'll show a preview of what'll actually change before you actually execute it
												- Allow SAM CLI IAM role creation (default: `Y`)
												- Function may not have authorisation defined, is this okay?
													- You can add auth via ((6463499e-3bb4-49ea-90d5-2df420c0fb1e)) if you want but not essential
											- During this process ((64b806d2-fdd2-4f63-84b8-4f0b76f20027)) : ((6463499e-dc33-4af7-bbb7-33338a8a325b)) will show the status of the Stack. It'll setup ((6463499e-42ab-4a58-8911-df6138dfee8f)) for source code, ((64b81154-09ce-46c2-993a-0451497bcf3c)). See `Resources` tab
										- `sam local start-api`
											- This will launch a local Docker container
											- Great way for testing ((6457bcad-7919-46a4-a9c0-8bb0ddf40189)) + ((6529032b-bb04-4660-836b-f33e1ae727ba)) locally for example
										- Define our template file in-browser
										- Use SAM to build source code and upload to S3
										- ((6463499e-dc33-4af7-bbb7-33338a8a325b)) which will create an ((6529032b-bb04-4660-836b-f33e1ae727ba)) + ((6457bcad-7919-46a4-a9c0-8bb0ddf40189))
								- [Using the AWS Serverless Application Model (AWS SAM) to Build Serverless Applications - YouTube](https://youtu.be/xQHgRgKquqQ)
								  collapsed:: true
									- 7 SAM serverless resources - Function
										- `AWS::Serverless::Function`
										  AKA ((6457bcad-7919-46a4-a9c0-8bb0ddf40189))
										- `AWS::Serverless::Api`
										  AKA ((6529032b-bb04-4660-836b-f33e1ae727ba))
										- `AWS::Serverless::HttpApi`
										- `AWS::Serverless::SimpleTable`
										  AKA ((6463499e-971f-49ad-9136-306a4377fe86))
										- `AWS::Serverless::LayerVersion`
										  AKA ((6457bcad-7919-46a4-a9c0-8bb0ddf40189)) layers
										- `AWS::Serverless::Application`
										  AKA
										- `AWS::Serverless::StateMachine`
										  AKA ((64b7c5ea-fc23-4c8f-bba3-40309679cf7d))
									- 16 supported ((6457bcad-7919-46a4-a9c0-8bb0ddf40189)) event sources
									  collapsed:: true
										- S3
										- SNS
										- Kinesis
										- DynamoDB
										- SQS
										- Api
										- HttpApi
										- Schedule
										- CloudWatchEvent
										- CloudWatchLogs
										- IoTRule
										- AlexaSkill
										- Cognito
										- EventBridgeRule
										- MSK
										- MQ
									- Parameters inline
									  collapsed:: true
										- ![image.png](../assets/image_1715274576253_0.png)
									- ((663c9e51-4706-42af-a785-973914c1a56d))
										- `sam init`
										  collapsed:: true
										  Create a new serverless application
											- Runtime: nodejs, dotnet, go, python, java, etc
										- `sam build`
										  id:: 663d098e-ff90-4d4b-8d99-d4ef880df61a
										  collapsed:: true
										  Generates deployment artifacts targeting ((6457bcad-7919-46a4-a9c0-8bb0ddf40189))'s execution environment
											- It downloads and compiles locally
										- `sam package`
										  collapsed:: true
										  Packages a SAM application
											- Copies the artifacts to a ((6463499e-42ab-4a58-8911-df6138dfee8f)) bucket
											- Outputs a YAML file with update CodeUri addresses
											- It's now built into `sam deploy` but is still available for CI/CD pipelines
										- `sam deploy`
										  collapsed:: true
										  Deploys or updates serverless application on ((6463499e-9096-4ccf-8af2-96569e23c33b)) cloud
											- Creates and manages ((6463499e-42ab-4a58-8911-df6138dfee8f)) bucket for deployment artifacts using zip format
											- Creates and manages ((64b7f20b-d92b-49cc-a0ad-64e70eca6cff)) repo for deployment artifacts using image format
											- Saves deploy options to a config file
											- `sam deploy --guided`
										- `sam local`
										  id:: 663d0c1b-cd02-4585-8443-6de6037c804f
										  collapsed:: true
										  Provides local development tools for serverless applications. Depends on [[Docker]]
											- `sam local generate-event`
											  Generates a JSON object representing the output from the given service and type
											- `sam local start-api`
											  Emulates ((6529032b-bb04-4660-836b-f33e1ae727ba)), allowing you to test ((6457bcad-7919-46a4-a9c0-8bb0ddf40189))
											- `sam local start-lambda`
											- etc
										- `sam logs`
										- `sam pipeline`
										  collapsed:: true
										  Generates resource and configuration required to build a continuous ((6463499d-76db-4797-a83f-4b9b7439743a)) pipeline
											- Supports
												- ((64b7f69c-6359-41e8-ae5d-bccf8b1f1a4d))
												- ((63a04b77-2247-4d65-87c2-8bad97d831fd))
												- ((6463499d-7235-4155-8c9d-78c9cf0e7367))
												- ((635fc546-4488-48a7-88e4-290264f0fb48))
												- ((6465fc27-2c3b-410a-ad7e-434da1cdf791))
												- Related: [Deployment](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-deploying.html) section of docs
											- `sam pipeline bootstrap`
											  Generates the required resources to connect to your pipeline
												- This step must be run for each deployment stage (e.g. staging, production) in your pipeline
											- `sam pipeline init`
											  Generates a pipeline configuration file that your CI/CD system can use to deploy serverless applications using SAM
										- `sam delete`
									- AWS SAM Accelerate
										- Aims to increase infrastructure accuracy for testing with incremental builds, sam sync and aggregated feedback for developers.
										- ((663d0c1b-cd02-4585-8443-6de6037c804f)) is only good enough for unit level testing, it's not accurate to whether the fully hosted resources will work the same way
										- ((663d098e-ff90-4d4b-8d99-d4ef880df61a)) has option for incremental builds - only the changed code is built, the rest is cached
										- `sam sync`
										  collapsed:: true
											- Two categories
												- Code specifically refers to:
													- Lambda function code
													  Lambda Layer code
													  Step Functions Amazon States Language (ASL)
													  API Gateway OpenAPI
												- Configuration = everything else
											- For code changes it'll only sync the specific services you changed, not every aspect of your deployment
											- For configuration changes it'll still do a full redeploy
											- `sam sync --watch`
											  It'll in realtime watch your code changes
										- Aggregated feedback for developers - ((6463499e-5ffa-47d2-aeb5-b9a8bce9bc64)) and ((64b7f73d-a5c9-4ec8-895e-ef8e5ab585d9))
										-
								- ((63904f39-6a5a-49aa-b6c5-f9811359b487))
								- [projen | projen](https://projen.io)
									- [GitHub - projen/projen: Rapidly build modern applications with advanced configuration management](https://github.com/projen/projen)
									- Framework for CDK or other language apps
								- [How to test AWS SQS Trigger Lambda Locally using SAM or LocalStack with CDK - YouTube](https://youtu.be/DwwiPd4xeP8)
									-
							- ((ba67650c-f474-4038-b234-99dd345a80ca))
					- AWS Dedicated Cloud
						-
	- Certifications
	  collapsed:: true
		- Learning Pathways
		  collapsed:: true
			- ![AWS-Certification-Current-Roadmap.png](../assets/AWS-Certification-Current-Roadmap_1688035267430_0.png)
			- id:: 649d5fc4-8e08-46fa-92ba-7e0eb6fb09fd
		- Paid courses
			- L1 - Foundational
				- [AWS Certified Cloud Practitioner](https://aws.amazon.com/certification/certified-cloud-practitioner/)
				  id:: 649d5e6a-1fa2-47f6-b3bb-84feb605ff05
				  collapsed:: true
					- Qualifications + weeks
						- AWS Business Accredited (week 1)
						- AWS Cloud Economics Accredited (week 2)
						- Cloud Practioner Certification (week 3-5)
					- Content
						- Week 1 - 3 hours self-study
						- Week 2 - 3 hours self-study
						- Week 3 - 1 virtual instructor led day
						- Week 4 - self study
						- Week 5/6 - virtual exam 1.5h
					- [Learning Resources]
						- ((64a40a28-baf2-428e-85d8-79ab03be1e6f))
						  5/10
						- [AWS Cloud Practitioner Essentials](https://explore.skillbuilder.aws/learn/course/134)
						  collapsed:: true
						  7/10
							- Modules
								- 1) Introduction to ((6463499e-9096-4ccf-8af2-96569e23c33b))
								  collapsed:: true
									- Client-server model
									- Cloud computing offers on-demand delivery of IT resources over the internet with pay-as-you-go pricing
										- no need to pay in advance, and easily stop paying when you want
										- Undifferentiated heavy lifting of IT - AWS specialises at these generic tasks like setting up a database, so you can focus on your USP e.g. the data in the database
										- On-premises AKA private cloud deployment
										- Pros/Cons of Cloud Computing
										  id:: 649d8c7c-8ec0-4ad2-868d-0b9b03abeec0
											- Pros
												- Trade upfront expense for variable expense (no need for heavy investent in data centers, physical servers etc)
												- Benefit from massive economies of scale
												- Stop guessing capacity - minimise risk of overprovisioning/underprovisioning
												- Increase speed and agility - faster deploying resources and products
												- Reduced costs of server maintenance
												- Go global in minutes
											- Cons
												-
											- Unclear
												-
											- Comparisons
											  collapsed:: true
												-
											- Related: ((63f4bf2e-0811-427e-a54b-1b9b38963017))
								- 2) Computer in the Cloud
								  collapsed:: true
									- Amazon EC2
									- YOu only pay for what you use - you don't pay for stopped or terminated instances. Though you may have EBS costs for stopped instances
									- Vertical scaling = increases size of instance
									- Networking - can be private or public
									- Instance types
									  collapsed:: true
										- General purpose
										- Compute-optimised
										- Memory optimised
										- Storage optimised
										- Accelerated computing e.g. floating point number calculations, graphics processing, data pattern matching, utilise hardware accelerators
									- Pricing options
									  collapsed:: true
										- On-Demand
										- Savings Plans - up to 72% discount by making a commitment to a consistent amount of usage, in USD per hour, for a 1 or 3 year term.
										  id:: 649d9901-5e4b-4deb-88a9-40d0043e2a66
										- Reserved Instances - up to 75% discount by making a commitment to a consistent instance configuration (steady state usage) for 1 or 3 year terms
										  id:: 649d9949-930d-4e57-8257-3b0f859f7b65
										  collapsed:: true
											- Pricing options
												- All Upfront paid
												- Partial Upfront
												- No Upfront
											- Subtypes
												- Standard Reserved Instance
													- Can only exchange for different instance size within the same instance family and generation
														- Allowed e.g. `t2.small` to `t2.large` as they're the same family and generation
														- Not allowed e.g. `t2` to `m2`, or `t2` to `t3`
												- Convertible Reserved Instance
													- Can be exchanged during the term for another Convertible Reserved Instance with new attributes, including instance family, instance type, platform, scope, or tenancy. For more information, see [Exchange Convertible Reserved Instances](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ri-convertible-exchange.html).
													- Can't be bought or sold in the Reserved Instance Marketplace
										- Spot Instances - up to 90% discount, but Amazon can reclaim those instances at any time with a 2 minute warning to save state
										- Dedicated Hosts - separate machine, usually to meet compliance requirements3
									- Scalability and Elasticity
									  collapsed:: true
										- Scalability
										  collapsed:: true
											- i.e. designing your architecture to automatically respond to changing demand by scaking out or in
											- Amazon EC2 Auto Scaling
											  id:: 649d9b65-1b7f-4e96-acae-91bcacd198d5
											  collapsed:: true
												- It's horizontal scaling
												- 2 approaches (can do both or one)
												  collapsed:: true
													- Dynamic scaling - adjusts to demand
													- Predictivee scaling - schedules the correct number of instances based on predicted demand
												- You set a minimum and maximum. Also can set desired capacity incase you don't want it to go as low as the minimum
										- ((6463499e-9ecf-4800-bf1f-65704c310016))
										  collapsed:: true
											- It's a regional construct, thus automatically highly available (it's in multiple locations?)
											- Decoupled architecture, it means frontend doesn't have to care about routing and just leaves it to the ELB
									- Messaging and Queueing
									  collapsed:: true
										- Queue AKA buffer
										- Tightly coupled architecture/monolithic - if one part fails, then other parts fails too
										- Loosely coupled archecture/microservices/modular - no single point of failure
										- Amazon Simple Queue Service (SQS) and Amazon Simple Notification Service (SNS) facilitate microservice communication
										  collapsed:: true
											- Amazon Simple Notification Service (SNS)
											  collapsed:: true
												- Topic - a channel for messages to be delivered
												- Subscribers follow a topic. They can be web servers, email addresses, Lambda functions, or more
												- Publish/subscribe service
											- Amazon Simple Queue Service (SQS)
											  collapsed:: true
												- Message queuing service (imagine it like an array)
												- You can send, store and receive messages between software components, without losing messages or requiring other services to be available
												- An app sends messages into the queue. Then a user or service retrieves a message from the queue, processes it, and then deletes it from the queue
									- Additional compute services
									  collapsed:: true
										- Serverless computing
										  collapsed:: true
											- You cannot see or access the underlying infrastructure. Management is handled by AWS
											- ((6457bcad-7919-46a4-a9c0-8bb0ddf40189))
											  collapsed:: true
												- Upload your code into a Lambda function, set a Trigger, and service waits for it
												- Automatic scaling
												- Meant for tasks with runtime <15 mins - unsuitable for deep learning. Suitable for web backend, expense reports, etc
											- *Container orchestration tools*
											  collapsed:: true
												- Meta
												  collapsed:: true
													- Containers are packages for your code, powered by OS-level virtualisation
													- These services run in EC2 instances. Allows you to interact with EC2 instances. But if you instead want it entirely managed, use AWS Fargate
												- Amazon Elastic Container Service (Amazon ECS)
												- Amazon Elastic Kubernetes Service (Amazon EKS)
											- AWS Fargate
											  collapsed:: true
												- Serverless compute platform for ECS + EKS
								- 3) Global Infrastructure and Reliability
								  id:: 649d87b0-9a8c-4fe8-8a4f-2c9491a0c041
								  collapsed:: true
									- AWS global infrastructure
										- Provides high availability and fault tolerance
										- Data centers are built in large groups called regions
										- data never leaves a single region unless you want it to
										- How to choose a region
										  collapsed:: true
											- Compliance (with governmental regulations)
											- Proximity - where are your customers based
											- Feature availability - some new features aren't available in some regions because they lack the novel hardware
											- Pricing - some locations are more than others
										- AWS cluster data centers are located in a Region
									- Availability Zones
									  collapsed:: true
										- Each region is made up of multiple physically separated AZs, and each AZ is made up of one or more data centers
										- Each AZ is 10s of miles separate, to ensure single-digit millisecond latency whilst also reducing the likelihood that multiple AZs or even the entire Region is affected
										- Best practice is to run across at least to AZs in a Region
										- There are some services which are already Highly Available (AKA Regionally Scoped Service) as they run across multiple AZs in a Region e.g. ((6463499e-9ecf-4800-bf1f-65704c310016))
									- Edge Locations
										- Use a CDN (Amazon CloudFront) to cache data closer to your customers. These are separate from Regions
										- Edge Locations also support DNS (Amazon Route 53)
										- Amazon Outposts start a mini-Region inside your own datacenter
									- How to provision AWS resources
									  collapsed:: true
										- Interacting with their API using either:
										  collapsed:: true
											- AWS Management Console
											- ((6544c9ef-05f1-41f8-8062-a6f5dc3cc6ad))
											- AWS Software Development Kits (SDKs)
											- Various other tools
										- Managed tools
										  collapsed:: true
											- ((6463499d-63a1-485e-bf7e-1bae513fd542))
											  collapsed:: true
												- Provisions EC2 instances
												- It can adjust capacity, load balance, automatically scale and application health monitoring
											- ((6463499e-dc33-4af7-bbb7-33338a8a325b))
											  collapsed:: true
												- Infrastructure-as-code tool to manage AWS using JSON or YAML templates. Works like Terraform
								- 4) Networking
								  id:: 649d87bd-b447-4b9c-8883-bb8421140b89
								  collapsed:: true
									- Intro
										- ((6463499e-177d-4f57-a6c6-9c947d98a39a)) allows you to create one or more public or private subnets (i.e. with internet access or without) in a single VPC
										- VPCs have one or more Internet Gateways which controls what do with internet traffic to your VPC
											- It can be a Virtual Private Gateway, that only allows in users from a private network
										- Problem with Virtual Private Gateway is that it can be DDOS'd even without authentication
											- Solution: ((64b80e82-4f75-432e-b04a-8d6ef2b72cbf))
										- One VPC might have multiple types of gateways attached to manage multiple different internal resources, all within different subnets
									- Subnets and network access control lists
										- AWS offers multiple types of security
											- Internet Gateways
											- Network hardening
											- Application security
											- User identity
											- Authentication and authorisation
											- Distributed denial of service prevention
											- Data integrity
											- Encryption
										- Every data packet that enters or exits a subnet gets checked against a "Network access control list" (Network ACL)
											- By default it allows all inbound and outbound traffic
										- Security Groups control communication between EC2 instances within a subnet
											- Unlike Network ACL, it only controls data entering, but not exiting
											- By default it denies all inbound traffic
										- Security Group is Stateful, Network ACL is Stateless
											- Stateful - memory of who to let in or out. This means it'll remember to accept a packet that originally exited it
											- Stateless - checks every packet regardless of circumstances
									- Global Networking
										- Amazon Route 53 is Amazon's Domain Name System (DNS)
										- Translates IP addresses to human-readable domain names
										- Routing policies
											- Latency-based routing
											- Geolocation DNS
											- Geoproximity routing
											- Weighted round robin
								- 5) Storage and Databases
								  collapsed:: true
									- Instances stores and Amazon Elastic Block Store (Amazon EBS)
									  collapsed:: true
										- Standard filesystems like ext4
										- Block-based storage
										- Instance Store Volumes can be written to like a normal hard drive
										- EBS persists between stops and starts of instances, whereas Instance Store Volumes are ephemeral
										- Amazon EBS snapshots are incremental backups
									- Amazon Simple Storage Service (Amazon S3)
									  collapsed:: true
										- Object-based storage
										- Store objects in buckets
										- Max object size = 5 TB
										- Objects can be versioned for incremental backup
										- Tiers
										  id:: 64a284d3-ae41-4642-9112-1a99c4ea5d59
										  collapsed:: true
											- Standard = 11 9's of reliability (9 decimal places)
											- Standard-Infrequent Access (S3 Standard-IA)
											  collapsed:: true
												- Rapid access when needed e.g. for backups
											- Glacier = doesn't need to be accessed rapidly e.g. files for archival and audit purposes. Takes several hours to recover data
											- One-Zone Infrequent Access (One Zone-IA)
											- Intelligent-Tiering
											  collapsed:: true
												- It'll monitor the objects' access patterns, and moves it as appropriate between Standard and Standard-IA
											- Glacier Instant Retrieval - same performance as S3 Standard
											- Glacier Flexible Retrieval - retrieval within minutes to hours
											- Glacier Deep Archive - retrieval within 12-48 hours
											- Outposts
										- S3 allows static website hosting
										- Amazon S3 Lifecycle management - move data automatically between tiers e.g. move to Glacier when it makes sense
										- Each object consists of data, metadata and a key (unique identifier)
										- When you modify a file in block storage, the updates are a delta. When a file in object storage is modified, the entire object is updated
									- Comparing Amazon EBS and Amazon S3
									  collapsed:: true
										- S3
										  collapsed:: true
											- Web enabled
											- Regionally distributed
											- Offers cost savings
											- Serverless
											- Better suited for video streaming
										- EBS
										  collapsed:: true
											- Better suited for video editing, complex read/write/change functions
									- ((63a06e59-4078-4357-b478-dda42326daf4))
									  collapsed:: true
										- Multiple instances can simultaneously access EFS data
										- Comparing EBS and EFS
										  collapsed:: true
											- EBS
											  collapsed:: true
												- Volumes attach to EC2 instances
												- Availability Zone level resource - it needs to be in the same AZ to be able to attach
												- Volumes do not automatically scale
											- EFS
											  collapsed:: true
												- Multiple instances can read and write simultaneously
												- Linux filesystem
												- Region level resource (stored across multiple AZs)
												- Auatomatically scales
									- Amazon Relational Database Service (Amazon RDS)
									  collapsed:: true
										- Relational database management system (RDBMS)
										- Supported databases
										  collapsed:: true
											- MySQL
											- PostgreSQL
											- Oracle
											- Microsoft SQL Server
										- Lift-and-shift migration can be used to migrate data to the cloud on EC2 from on-premises
										- Features
										  collapsed:: true
											- Automated patching
											- Backups
											- Redundancy
											- Failover
											- Disaster recovery
									- ((6463499e-0ca7-46e7-8632-237030c12357))
									  id:: 64a29582-72af-4110-a1a3-0cc0b34ceed1
									- ((6463499e-971f-49ad-9136-306a4377fe86))
									  id:: 64a2968b-a40c-4c53-9bce-58b30ebfcc91
									- Amazon Redshift
									  collapsed:: true
										- Data warehouses - able to query over multiple databases
										- Used to analyse historical analytics, as opposed to real-time operational analysis
									- AWS Database Migration Service
									  collapsed:: true
										- Features
										  collapsed:: true
											- Source database remains fully operational during migration
											- Source and target databases don't have to be of the same type
											  collapsed:: true
												- *Of the same type*
												  collapsed:: true
													- MySQL > Amazon RDS for MySQL
													- Microsoft SQL Server > Amazon RDS for SQL Server
													- Oracle > Amazon RDS for Oracle
												- *Of different types*
												  collapsed:: true
												  Heterogenous migrations
													- AWS Schema Conversion Tool used first to convert schema structures + database code
													- Next, for data types
											- Commonly used for migration development and test databases, database consolidation and continuous data replication
									- Additional database services
									  collapsed:: true
										- Amazon DocumentDB (with MongoDB compatibility)
										- Amazon Neptune 
										  Graph database - good for social media sites
										- Amazon Managed Blockchain
										  id:: 64a2c600-0d29-4957-8c68-316d77cfd54e
										- Amazon Quantum Ledger Database (Amazon QLDB)
										  Immutability of ((64a2c600-0d29-4957-8c68-316d77cfd54e)), but without decentralisation
										- *Database accelerators*
										  collapsed:: true
											- ((6463499e-529d-478c-822f-2ff43f26b6bf))
											- Amazon DynamoDB Accelerator (DAX)
											  In-memory cache
								- 6) Security
								  collapsed:: true
									- AWS Shared Responsibility Model
									  collapsed:: true
										- Customer is responsible for security "in" the cloud
										  collapsed:: true
											- Platform, applications, identity and access management
											- Operating system, network and firewall configuration
											- Client-side data encryption
											- Server-side data encryption
											- Network traffic protection
										- AWS is responsible for security "of" the cloud
									- User permissions and access
									  collapsed:: true
										- AWS account root user
										  collapsed:: true
											- Access and control any resource in the account
										- ((64b81154-09ce-46c2-993a-0451497bcf3c))
										  collapsed:: true
											- Used to manage permissions given to IAM user accounts
											- Default: no permissions (principle of least privilege - a user is granted access only to what they need)
											- IAM policies (JSON document) is associated with each user - a list of what actions user's can do, and on what resources
											- IAM groups used to grant multiple IAM accounts the same policy
											- Roles are basically standalone policies that can be temporarily associated with a user as needed
									- AWS Organisations
									  collapsed:: true
										- Features
										  collapsed:: true
											- Centralised management of all your AWS accounts
											- Consolidated billing
											- Hierarchical groupings of accounts
											  collapsed:: true
												- Group accounts into organisational units (OUs)
											- AWS service and API action access control
											  collapsed:: true
												- Service control policies (SCPs) used to centrally control permissions
												  collapsed:: true
													- Applied to Organisational Units (OUs) + individual member accounts + organisation root
									- Compliance
									  collapsed:: true
										- e.g. to meet regulations with GDPR, HIPAA, etc
										- AWS Artifact
										  collapsed:: true
											- Provides on-demand access to AWS security and compliance reports
											- 2 main sections
											  collapsed:: true
												- AWS Artifact Agreements
												  collapsed:: true
													- Allows signing an agreement with AWS e.g. HIPAA
												- AWS Artifact Reports
												  collapsed:: true
													- Provides compliance reports from 3rd-party auditors, which you can then provide these audits to your auditors or regulators
										- Customer Compliance Center
										  collapsed:: true
											- Whitepapers and documents to learn about AWS' compliance, etc
									- Denial-of-service attacks (DoS)
									  collapsed:: true
										- UDP flood - tricks big providers e.g. weather data services to instead return request data to your server address
										  collapsed:: true
											- Solution: security groups
										- HTTP level attacks - bots request traffic
										  collapsed:: true
											- Solution:
										- Slowloris attack - pretending to have a slow connection to keep your server busy for longer
										  collapsed:: true
											- Solution: ((6463499e-9ecf-4800-bf1f-65704c310016))
										- Strongest protection
										  collapsed:: true
											- AWS Shield with AWS WAF
										- AWS Shield Standard - everyone has this for free to protect against the most common DDoS attacks
										- AWS Shield Advanced - paid service, provides attack diagnostics and mitigation
									- Additional security services
									  collapsed:: true
										- Encryption
										  collapsed:: true
											- At rest e.g. DynamoDB table data
											- In-transit e.g. SSL used for Redshift to RDS connection
										- ((64b81161-baf7-46dc-ab13-4755b196d0fb))
										- Amazon Inspector - automated security assessments
										  collapsed:: true
											- Features
											  collapsed:: true
												- Network configuraiton reachability piece
												- Amazon agent which can be installed on EC2 instances
												- Security assessment service
										- Amazon GuardDuty - intelligent threat detection via continuous monitoring of network activity and account behaviour
								- 7) Monitoring and Analytics
								  collapsed:: true
									- ((6463499e-5ffa-47d2-aeb5-b9a8bce9bc64))
									  id:: 64a2d648-e7cc-4a61-aee5-f49ca31de290
									  collapsed:: true
									- ((6463499e-fe31-4613-8b61-e232816b6ddb))
									  collapsed:: true
										- Comprehensive API auditing tool
										- Every request to the AWS API is logged to allow audits
										- Vault Lock is tamper-proof so this can show you never tampered with the logs
										- CloudTail Insights - optional feature for detecting unusual API activities
									- AWS Trusted Advisor
									  collapsed:: true
										- Automated advisor which will evaluate your resources against 5 metrics:
										  collapsed:: true
											- Cost optimisation
											- Performance
											- Security
											- Fault tolerance
											- Service limits
								- 8) Pricing and Support
								  id:: 649d87db-e0f6-4fd3-b82c-22a095dba688
								  collapsed:: true
									- AWS Free Tier
									  collapsed:: true
										- Always free
										  collapsed:: true
											- e.g. ((6457bcad-7919-46a4-a9c0-8bb0ddf40189)) has 1 million free invocations, DynamoDB 25GB free storage per month
										- 12 months free
										  collapsed:: true
											- e.g, Amazon S3 is free for 12 months up to 5GB
										- Short-term trials
										  collapsed:: true
											- e,g, Amazon Inspector 90-day free trial
									- [AWS Pricing Calculator](https://calculator.aws)
									  id:: 64a2e353-ee45-4bc9-8328-dca5458f441c
									  collapsed:: true
									  Lets you provide all the necessary details for your cloud deployment use case and then gives you a cost estimate, which you can export or share as required.
										- Create Estimate > My Estimate (breadcrumb) > Create Group e.g. `Web Servers` > Add Service > Find Service e.g. `ec2` > Configure > Description e.g. `Web Server Estimate` > Location Type: `Region` > Region e.g. `US East` >
										  id:: 64a7e6a7-93f3-4e78-9a5e-03e83f1bb310
											- EC2 specifications
												- OS: `Linux` > Workloads: `Daily spike traffic` > Workload days: `All` > Baseline: `2` > Peak: `40` > Duration of peak: `8h`
											- EC2 instances
									- AWS Billing and Cost Management dashboard
									  id:: 64a2e35c-1eb3-445a-be03-860e13c1b4aa
									- Consolidated billing - central location to view bills, available for AWS Organisations
									- AWS Budgets
										- Set alerts when you reach e.g. 80% of a budget
									- [AWS Cost Explorer](https://aws.amazon.com/aws-cost-management/aws-cost-explorer/)
									  visually see what you're spending on, and see historical data | Shows costs associated with AWS resources like Amazon Elastic Compute Cloud (EC2), Managed Blockchain, etc. You can also view costs for resources grouped by tags. It provides historical cost data of 12 months. The default view is of the top 5 AWS services.
									- [AWS Support plans](https://aws.amazon.com/premiumsupport/plans/)
									  id:: 64a2ea92-920d-496d-9418-fd74d9bbded0
									  collapsed:: true
										- Types
											- Basic support
												- Everyone gets this for free
												- 24/7 customer service
												- Documentation
												- Whitepapers
												- Support forums
												- AWS Trusted Advisor
												- AWS Personal Health Dashboard
											- Developer support
												- Email access to customer support
											- Business suport
												- AWS Trusted Advisor provides the full set of best practice checks
												- Direct phone access to cloud support engineers
												- Infrastructure event management
											- Enterprise support
											  id:: 64a2eb13-7b47-4c07-bb96-753011d8c03c
												- 15 minute SLA for business critical workloads
												- Technical Account Manager (TAM)
													- The Enterprise support plan provides access to a TAM who is the main point of contact for you at AWS. A TAM provides feedback and guidance and also communicates with your company as you deploy and run applications with AWS.
												- The Concierge - billing and accounts team
												  collapsed:: true
													- The Concierge is a part of the Enterprise support plan on AWS. It is also available for the Enterprise On-Ramp support plan. The Concierge is a team of professionals who have expertise in the AWS Billing and Accounts with specialization in working on Enterprise accounts. The Concierge’s role is to provide assistance to AWS customers on all issues related to billing and accounts based on key best practices.
												- Access to AWS Managed Services (AMS) and Cloud Service Delivery Manager (CSDM)
												- The Enterprise On-Ramp support plan provides you with 24/7 support from engineers, technology, and tools for managing your system's health. It also provides architectural guidanc based on your applications. Enterprise support plans offer access to proactive reviews, deep dives, and workshops that are not available for Enterprise On-Ramp plans.
										- Support cases via ((64b806d2-fdd2-4f63-84b8-4f0b76f20027))
										  id:: 64be4a55-3db0-4849-ab3f-1e608063b1cb
											- You can create three customer support cases using AWS Support:
												- Account and billing
												- Service limit increase
												- Technical support (requires ((64a2eb13-7b47-4c07-bb96-753011d8c03c)) )
											- Related cases, which require different means:
												- Support plan change - instead access Support plans via ((64b806d2-fdd2-4f63-84b8-4f0b76f20027))
												- Closing your account - instead access the ((64a2e35c-1eb3-445a-be03-860e13c1b4aa))
												- Change root email account - instead access ((64a2e35c-1eb3-445a-be03-860e13c1b4aa))
									- AWS Marketplace
									  collapsed:: true
										- Curated marketplace for deploying curated applications
										- One-click deployment
										- Pay-as-you-go options instead of only subscription options
										- Enterprise-focused features
										  collapsed:: true
											- Custom terms and pricing
											- A private marketplace
											- Integration itno your procurement systems
											- Cost management tools
								- 9) Migration and Innovation
								  collapsed:: true
									- [AWS Cloud Adoption Framework (AWS CAF)](https://aws.amazon.com/cloud-adoption-framework/)
									  id:: 64a2ed7b-5edf-49b3-9619-9598f7df6139
									  collapsed:: true
										- Guidance for how to migrate successfully
										- 6 core perspectives:
											- *Business capabilities*
												- Business
													- Ensures that IT aligns with business needs and are linked to key business results
												- People
													- Supports development of an organisation-wide change management strategy, identity skill and process requirements, etc
												- Governance
													- Understand how ot update staff skills and processes necessary to ensure business governance in the cloud
											- *Technical capabilities*
												- Platform
													- Learning architectural models to communicate the relationship of IT systems and migrating on-premises workloads
												- Security
													- Ensures that the organisation meets security objectives for visibility, auditability, control and agility
												- Operations
													- Helps you to enable, run, use, operate and recover IT workloads. Define daily/quarterly/annual operations
										- 6 R's of migraiton
										  In order of increasing manual work required?
											- Rehosting (AKA lift-and-shift)
											- Replatforming (AKA lift-tinker-and-shift)
											- Retire
											  collapsed:: true
												- Some applications don't need to migrate because they're end-of-life
											- Retain
											  collapsed:: true
												- End-of-life soon, but for now keep them going
											- Repurchasing
												- Moving from traditional licenses to SaaS e.g. move from one CRM vendor to Salesforce
											- Refactoring
											  collapsed:: true
												- Requires rewriting code but has high upside too
									- AWS Snow Family
									  collapsed:: true
										- Physical devices to transfer legacy data to Amazon servers (usually a S3 bucket)
										- AWS Snowcone
										  collapsed:: true
											- Device that contains 8TB storage
										- AWS Snowball Edge
										  collapsed:: true
											- Up to 81 TB
										- AWS Snowmobile
										  collapsed:: true
											- For up to 100PB (100k TB)
									- Innovate with AWS Services
									  collapsed:: true
										- VMWare Cloud on AWS
										- AWS SageMaker - for machine learning
										- Amazon Augmented AI (Amazon A2I)
										- Amazon Lex - heart of Alexa, used for building interactive chatbots
										- Amazon Textract - taking text and data from documents
										- AWS DeepRacer - reinforcement learning
										- AWS Ground Station - satellite usage
								- 10) The Cloud Journey
								  collapsed:: true
									- [AWS Well-Architected Framework](((64a3dff5-efbe-4d9e-9baf-0106aae2dc78)))
									  id:: 64a2f372-f388-47a4-a7aa-e668a7f27a84
									- Advantages of cloud computing
									  collapsed:: true
										- Trade upfront expense for variable expense
										- Benefit from massive economies of scale
										- Stop guessing capacity
										- Increase speed and agility
										- Stop spending money running and maintaining data centers
										- Go global in minutes[]()
						- [AWS Partner: Well-Architected Best Practices (Technical)](https://explore.skillbuilder.aws/learn/course/2426)
						  id:: 64a3dff5-efbe-4d9e-9baf-0106aae2dc78
						  collapsed:: true
						  1/10 - out of date compared to the [official docs](https://aws.amazon.com/architecture/well-architected/)
							- The framework is made up of Questions, Design Principles and Pillars
								- General Design Principles
									- No guessing needed to understand capacity needs
									- Test at production scale
									- Make experimentation easier
									- Allow architectures to evolve
									- Build data-driven architectures
									- Improve through game days
								- Pillars
									- [Operational Excellence](https://docs.aws.amazon.com/wellarchitected/latest/operational-excellence-pillar/welcome.html)
									  collapsed:: true
									  The ability to run and monitor systems to deliver business value and to continually improve supporting processes.
										- Design principles
											- Documentation
												- Learn from all operational failures: Drive improvement through lessons learned from all operational events and failures. Share what is learned across teams and through the entire organization.
											- Make frequent small, reversible changes
												- Design workloads to allow components to be updated regularly to increase the flow of beneficial changes into your workload. Make changes in small increments that can be reversed if they fail to aid in the identification and resolution of issues introduced to your environment (without affecting customers when possible).
											- Perform operations as code
												- In the cloud, you can apply the same engineering discipline that you use for application code to your entire environment. You can define your entire workload (applications, infrastructure, etc.) as code and update it with code. You can script your operations procedures and automate their process by launching them in response to events. By performing operations as code, you limit human error and create consistent responses to events.
											- Refining procedures frequently and quickly
												- As you use operations procedures, look for opportunities to improve them. As you evolve your workload, evolve your procedures appropriately. Set up regular game days to review and validate that all procedures are effective and that teams are familiar with them.
											- Anticipate system failure
												- Perform “pre-mortem” exercises to identify potential sources of failure so that they can be removed or mitigated. Test your failure scenarios and validate your understanding of their impact. Test your response procedures to ensure they are effective and that teams are familiar with their process. Set up regular game days to test workload and team responses to simulated events.
									- [Security](https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/welcome.html)
									  collapsed:: true
									  The ability to protect information, systems and assets while delivering business value through risk assessments and mitigation strategies.
										- [Design principles](https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/security.html)
											- Implement a strong identity foundation
												- Implement the principle of least privilege and enforce separation of duties with appropriate authorization for each interaction with your AWS resources. Centralize identity management, and aim to eliminate reliance on long-term static credentials.
											- Maintain traceability
												- Monitor, alert, and audit actions and changes to your environment in real time. Integrate log and metric collection with systems to automatically investigate and take action.
											- Apply security at all layers
												- Apply a defense in depth approach with multiple security controls. Apply to all layers (for example, edge of network, VPC, load balancing, every instance and compute service, operating system, application, and code).
											- Automate security best practices
												- Automated software-based security mechanisms improve your ability to securely scale more rapidly and cost-effectively. Create secure architectures, including the implementation of controls that are defined and managed as code in version-controlled templates.
											- Protect data in transit and at rest
												- Classify your data into sensitivity levels and use mechanisms, such as encryption, tokenization, and access control where appropriate.
											- Keep people away from data
												- Use mechanisms and tools to reduce or eliminate the need for direct access or manual processing of data. This reduces the risk of mishandling or modification and human error when handling sensitive data.
											- Prepare for security events
												- Prepare for an incident by having incident management and investigation policy and processes that align to your organizational requirements. Run incident response simulations and use tools with automation to increase your speed for detection, investigation, and recovery.
										- Focus areas:
											- Identity and access management
											- Detective controls
											- Infrastructure protection
											- Data protection
											- Incident response
									- [Reliability](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html)
									  collapsed:: true
									  The ability to recovery from infrastructure/service failures, dynamically acquire computing resources to meet demand, and mitigate disruptions such as misconfigurations or transient network issues.
										- [Design principles](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/design-principles.html)
											- Automatically recover from failure:
												- By monitoring a workload for key performance indicators (KPIs), you can run automation when a threshold is breached. These KPIs should be a measure of business value, not of the technical aspects of the operation of the service. This allows for automatic notification and tracking of failures, and for automated recovery processes that work around or repair the failure. With more sophisticated automation, it’s possible to anticipate and remediate failures before they occur.
											- Test recovery procedures:
												- In an on-premises environment, testing is often conducted to prove that the workload works in a particular scenario. Testing is not typically used to validate recovery strategies. In the cloud, you can test how your workload fails, and you can validate your recovery procedures. You can use automation to simulate different failures or to recreate scenarios that led to failures before. This approach exposes failure pathways that you can test and fix before a real failure scenario occurs, thus reducing risk.
											- Scale horizontally to increase aggregate workload availability:
												- Replace one large resource with multiple small resources to reduce the impact of a single failure on the overall workload. Distribute requests across multiple, smaller resources to ensure that they don’t share a common point of failure.
											- Stop guessing capacity
												- A common cause of failure in on-premises workloads is resource saturation, when the demands placed on a workload exceed the capacity of that workload (this is often the objective of denial of service attacks). In the cloud, you can monitor demand and workload utilization, and automate the addition or removal of resources to maintain the optimal level to satisfy demand without over- or under-provisioning. There are still limits, but some quotas can be controlled and others can be managed (see Manage Service Quotas and Constraints).
											- Manage change through automation
												- Changes to your infrastructure should be made using automation. The changes that need to be managed include changes to the automation, which then can be tracked and reviewed.
										- Focus areas:
											- Foundations
											- Change management
											- Failure management
									- [Performance Efficiency](https://docs.aws.amazon.com/wellarchitected/latest/performance-efficiency-pillar/welcome.html)
									  collapsed:: true
									  The ability to use computing resources efficiently to meet system requirements, and to maintain that efficiency as demand changes and technologies evolve.
										- [Design principles](https://docs.aws.amazon.com/wellarchitected/latest/performance-efficiency-pillar/design-principles.html)
											- Democratize advanced technologies:
												- Make advanced technology implementation easier for your team by delegating complex tasks to your cloud vendor. Rather than asking your IT team to learn about hosting and running a new technology, consider consuming the technology as a service. For example, NoSQL databases, media transcoding, and machine learning are all technologies that require specialized expertise. In the cloud, these technologies become services that your team can consume, allowing your team to focus on product development rather than resource provisioning and management.
											- Go global in minutes
												- Deploying your workload in multiple AWS Regions around the world allows you to provide lower latency and a better experience for your customers at minimal cost.
											- Use serverless architectures
												- Serverless architectures remove the need for you to run and maintain physical servers for traditional compute activities. For example, serverless storage services can act as static websites (removing the need for web servers) and event services can host code. This removes the operational burden of managing physical servers, and can lower transactional costs because managed services operate at cloud scale.
											- Experiment more often
												- With virtual and automatable resources, you can quickly carry out comparative testing using different types of instances, storage, or configurations.
											- Consider mechanical sympathy
												- Use the technology approach that aligns best with your goals. For example, consider data access patterns when you select database or storage approaches.
										- Focus areas:
											- Selection
											- Review
											- Monitoring
											- Trade-offs
									- [Cost Optimisation](https://docs.aws.amazon.com/wellarchitected/latest/cost-optimization-pillar/welcome.html)
									  collapsed:: true
									  The ability to avoid or eliminate unneeded or suboptimal resources.
										- [Design principles](https://docs.aws.amazon.com/wellarchitected/latest/cost-optimization-pillar/design-principles.html)
											- Implement cloud financial management: To achieve financial success and accelerate business value realization in the cloud, you must invest in Cloud Financial Management. Your organization must dedicate the necessary time and resources for building capability in this new domain of technology and usage management. Similar to your Security or Operations capability, you need to build capability through knowledge building, programs, resources, and processes to help you become a cost efficient organization.
											- Adopt a consumption model: Pay only for the computing resources you consume, and increase or decrease usage depending on business requirements. For example, development and test environments are typically only used for eight hours a day during the work week. You can stop these resources when they’re not in use for a potential cost savings of 75% (40 hours versus 168 hours).
											- Measure overall efficiency: Measure the business output of the workload and the costs associated with delivery. Use this data to understand the gains you make from increasing output, increasing functionality, and reducing cost.
											- Stop spending money on undifferentiated heavy lifting: AWS does the heavy lifting of data center operations like racking, stacking, and powering servers. It also removes the operational burden of managing operating systems and applications with managed services. This allows you to focus on your customers and business projects rather than on IT infrastructure.
											- Analyze and attribute expenditure: The cloud makes it easier to accurately identify the cost and usage of workloads, which then allows transparent attribution of IT costs to revenue streams and individual workload owners. This helps measure return on investment (ROI) and gives workload owners an opportunity to optimize their resources and reduce costs.
										- Focus areas:
											- Cost-effective resources
											- Match supply and demand
											- Expenditure awareness
											- Optimising over time
											- Appropriate provisioning
									- [Sustainability](https://docs.aws.amazon.com/wellarchitected/latest/sustainability-pillar/sustainability-pillar.html)
									  collapsed:: true
									  The long-term environmental, economic, and societal impact of your business activities.
										- [Design principles](https://docs.aws.amazon.com/wellarchitected/latest/sustainability-pillar/design-principles-for-sustainability-in-the-cloud.html)
											- Understand your impact: Measure the impact of your cloud workload and model the future impact of your workload. Include all sources of impact, including impacts resulting from customer use of your products, and impacts resulting from their eventual decommissioning and retirement. Compare the productive output with the total impact of your cloud workloads by reviewing the resources and emissions required per unit of work. Use this data to establish key performance indicators (KPIs), evaluate ways to improve productivity while reducing impact, and estimate the impact of proposed changes over time.
											- Establish sustainability goals: For each cloud workload, establish long-term sustainability goals such as reducing the compute and storage resources required per transaction. Model the return on investment of sustainability improvements for existing workloads, and give owners the resources they need to invest in sustainability goals. Plan for growth, and architect your workloads so that growth results in reduced impact intensity measured against an appropriate unit, such as per user or per transaction. Goals help you support the wider sustainability goals of your business or organization, identify regressions, and prioritize areas of potential improvement.
											- Maximize utilization: Right-size workloads and implement efficient design to ensure high utilization and maximize the energy efficiency of the underlying hardware. Two hosts running at 30% utilization are less efficient than one host running at 60% due to baseline power consumption per host. At the same time, eliminate or minimize idle resources, processing, and storage to reduce the total energy required to power your workload.
											- Anticipate and adopt new, more efficient hardware and software offerings: Support the upstream improvements your partners and suppliers make to help you reduce the impact of your cloud workloads. Continually monitor and evaluate new, more efficient hardware and software offerings. Design for flexibility to allow for the rapid adoption of new efficient technologies.
											- Use managed services: Sharing services across a broad customer base helps maximize resource utilization, which reduces the amount of infrastructure needed to support cloud workloads. For example, customers can share the impact of common data center components like power and networking by migrating workloads to the AWS Cloud and adopting managed services, such as AWS Fargate for serverless containers, where AWS operates at scale and is responsible for their efficient operation. Use managed services that can help minimize your impact, such as automatically moving infrequently accessed data to cold storage with Amazon S3 Lifecycle configurations or Amazon EC2 Auto Scaling to adjust capacity to meet demand.
											- Reduce the downstream impact of your cloud workloads: Reduce the amount of energy or resources required to use your services. Reduce or eliminate the need for customers to upgrade their devices to use your services. Test using device farms to understand expected impact and test with customers to understand the actual impact from using your services.
								- Pillar-Specific Design Principles
									- Automate responses to security events
							- Related: ((64a419f7-d7f8-4aaf-be6e-d617989f17dc))
						- [AWS Cloud Quest: Cloud Practitioner](https://cloudquest.skillbuilder.aws)
						  id:: 64a6c664-aba8-4ec6-ad46-e5fb31f396c9
						  collapsed:: true
						  8/10 - very good for learning practically, however it's more depth than breadth-focused
							- Meta
							  collapsed:: true
								- Tasks come with 4 steps
									- 1) Learn
										- Multiple pages, plus videos
									- 2) Plan
										- Eye icon shows the diagram for the solution
									- 3) Practice
										- Deploys a test AWS account
										- You'll build a portion of the solution using guided steps
									- 4) DIY
										- Complete the solution by yoursel
								- Gamification
									- Music - changes when exploring vs doing an exercise
									- Pets can be collected - answer quizzes to earn
									- Drones can be shot down, and points earned for answering the one multiple-choice answer
									- Vehicles like hoverboard earned
									- Different paths of quest givers on a city route - different city routes for different learning pathways e.g. Cloud Practitioner, Developer
									- Earnings for lessons
										- Gems - used to buy cosmetic buildings/landscape
										- Customisation options
										- Reputation points - specific to each Amazon service
							- *Cloud Practitioner path*
								- AWS Global Infrastructure
									- AWS Regions have at least 2 AZs, most have 3, up to 6
									- AZs have 1 or more discrete data centers, usually 3
								- Amazon S3 - static website hosting
								  collapsed:: true
									- S3 bucket allows static website hosting
										- To do it for individual buckets go to the Properties tab > enable Static Website Hosting
									- Permissions tab
										- Ensure `Off` is the setting for Block all public access
										- Edit bucket policy
											- Ensure that `s3:GetObject` has `"Effect": "Allow"` and `"Resource": "Your_Bucket_ARN/*"`
											- Copy the ARN from the the `Bucket ARN` section on this Edit bucket policy webpage
									- Notes
										- Up to 5GB objects can be uploaded in a single PUT operation. For larger objects up to 6TB use the multipart upload API
								- Amazon EC2 + Amazon EBS - deploying multiple instances in different AZs in the same Region
								  collapsed:: true
									- Amazon EBS
									  collapsed:: true
									  AKA Amazon Elastic Block Storage
										- Multiple EBS volumes can be attached to a single EC2 instance, however they can only be attached to one instance at a time usually
											- Amazon EBS Multi-Attach allows a Provisioned IOPS SSD-based EBS volume to be attached to up to 16 Nitro-based EC2
										- EBS volumes can be easily increased in size
										- Snapshots (incremental backups) which are stored in S3 are easy
										- Volume types
											- General purpose SSD
												- `gp2`
												- `gp3`
											- Provisioned IOPS SSD
												- `io1`
												- `io2`
												- `io2 Block Express`
											- Throughput optimised HDD
												- `sc1`
												- `st1`
									- Steps
										- When creating the instance: Network settings >  Firewall (security groups) > Type: `HTTP`
											- This ensures this server acts like a web server (accepts inbound traffic on port 80)
											- You can select one or more security groups and modify the rules to allow traffic as desired e.g. `HTTPS` also
										- In Advanced details > User data > you can paste a bash script e.g.
											- ```bash
											  sudo yum update -y
											  sudo yum install -y httpd
											  ```
								- Amazon EC2 - increasing the size of an instance
								  collapsed:: true
									- Amazon Data Lifecycle Manager is the resource which automates the creation, retention and deletion of Amazon EBS snapshots and AMIs backed by Amazon EBS
									- Can connect to an instance via either:
									  id:: 64a7ce5f-3e8c-4c88-9cae-e331f6815431
										- *Meta*
											- EC2 > Instances > Connect > choose any of the 4 options
										- 1) EC2 Instance Connect - default method in the browser
											- Can be inhibited by security group settings if SSH inbound/outbound is blocked
										- 2) ((64b80795-b0df-423c-a9f6-0b4e1cc37ff5)) > Session Manager
										  collapsed:: true
										  Secure and auditable web-based terminal connection without the need to open inbound ports, maintain bastion hosts or manage SSH keys
											- `sudo -i`
											  Provide root privileges in the current session
											- `tail -1f aws_computer_solutions.log`
											  Check the instance log
										- 3) SSH client - use to connect via CLI
										- 4) EC2 serial console - serial port of an instance. Equivalent of plugging in mouse + keyboard directly to device
									- Steps
										- To filter instance types go to EC2 > Instance Types > type something like `t3.large` then press Enter
										- Instances > select an Instance > Actions dropdown > Instance settings > Edit user data
								- ((64a2e353-ee45-4bc9-8328-dca5458f441c))
								  collapsed:: true
								- Networking - Amazon EC2 and Amazon VPC
								  collapsed:: true
									- Create a routing table and attach an internet gateway. Configure a security group
									  collapsed:: true
										- ((6463499e-177d-4f57-a6c6-9c947d98a39a)) documentation
										  id:: 64a8146f-144f-4177-827c-83224b7f581c
										  collapsed:: true
											- This is a virtual private network. You get a default one for each AWS Region, and you can make up to 5 per Region without asking to raise the limits
											- A subnet is a partition of your VPC IP address range. A VPC allows 1024 IP addresses, so 4 subnets splits it into 251 IP addresses each
											- *Internet connectivity*
												- Internet gateways enable communication between the internet and your VPC
												- You must create one, then attach it to your VPC. Add it to your subnet route table. Make sure your instances have public IPv4/IPv6/Elastic IP addresses
												- Configure Network Access Control Lists (NACLs) to allow traffic inbound to subnet
												  id:: 64a81b9b-0f08-478f-877f-893ad0b18587
													- These are stateless network components, which means that data coming into an EC2 instance must be specifically allowed by creating the appropriate networking rule
													- It controls traffic inbound, not used for accessing the internet outbound
												- Configure Security groups to allow traffic to VPC
												- You need a NAT (Network Address Translation) gateway in the public internet to enable instances in a private subnet to connect to the internet, whilst preventing the internet from initiating connections with the instances. Then you need to point to it in the route table
												  id:: 64a81c33-b200-4f6f-aeef-939216e1d932
													- To create a NAT gateway, you must specify the public subnet in which it will reside, as well as Elastic IP for the gateway
													- Note: it doesn't support IPv6 traffic. For that you'd need an egress-only internet gateway instead
											- *Concepts*
												- When you create a VPC, you must specify a range of private IPs for it in the form of a CIDR (Classless Inter-Domain Routing)
												- VPCs come with a main route table by default. You can also create custom route tables
													- Rules are called Routes, which are rules that dictate where traffic destination and target
												- Each subnet must be associated with a route table
												- You can make a subnet public by adding a route in your subnet route table to an internet gateway to support inbound and outbound access to the public internet
											- *NACLs and Security Groups*
												- Default NACL on VPC allows all outbound and inbound traffic
												- You can make custom NACLs and associate it with a subnet. Default is deny all inbound/outbound traffic
												- You can associate multiple subnets to a NACL, but only one NACL to a subnet
												- Security Groups as like a virtual firewall at the instance level to control inbound/outbound traffic
													- By default, a security group denies all inbound but allows all outbound
											- Steps - configuring a VPC
												- To see an EC2 instance's VPC > select an EC2 instance
													- Networking tab > Subnet ID to go to VPC: Subnets filtered page > select the subnet > Route table tab > click the Route table link to go Route tables filtered page > Routes tab > Edit routes >
														- Add route: `0.0.0.0/0`, Target: Internet Gateway
															- Internet gateways do 2 things:
																- Provide a target in your VPC route tables for internet-routable traffic
																- Perform network address translation (NAT) to instances that have been assigned public IPv4 addresses
													- Security tab > Security groups link > Edit inbound rules > Add rule > Type: HTTP > Source: Anywhere-IPv4 > Save rule
												- Note: CIDR naming convention `0.0.0.0/0` represents all IPv4 addresses (`::/0` for IPv6)
									- Setting up VPC peering connection between 2 VPCs
									  collapsed:: true
										- VPC peering - create a connection via two VPCs, allowing you to route traffic between them via private IP addresses
										- Video
											- Allows instances to connect to each other as if they're on the same network
											- It allows for inter-region and inter-account communication
											- Route tables allow access to the entire CIDR block of a peered VPC
										- Steps
											- EC2 page > Instances > select one > presence of Public IPv4 address or not determines if this was generated in a public VPC, or a private one
											- 1) Setup peering connection
												- VPC page > Peering connections > Create peering connection >
													- Name: `Marketing <> Finance` > Requester ID: Marketing VPC > ensure first CIDR `x.x.x.x/x` exists and note it down for later> Accepter: Finance VPC > ensure second CIDR `x.x.x.x/x` exists and note it down for later > Create > Actions > Accept request
											- 2) Update routes
												- 2a) EC2 Instances > select the requester EC2 instance > Subnet ID link > check the box for the subnet > Route table > check the box > Routes tab > Edit routes > Add route > Destination: second CIDR`x.x.x.x/x` > Target: `pcx-` or `Peering connection`
												- 2b) Repeat for the other server
											- 3) Update security groups
											  id:: 64abe82b-a702-4134-bb6a-04e29372943f
												- 3a) EC2 page > select > Security groups > Edit inbound rules > Custom ICMP > IPV4 > first CIDR
												- 3b) Repeat for other server
								- Amazon RDS - setting up a Amazon RDS for MySQL instance, enabling backups, multiple AZs and read replicas
								  collapsed:: true
									- Videos
										- Overview
											- Managed server automates hardware provisioning, setup, patching, backups, etc
											- 6 options
												- Amazon Aurora
												- PostgreSQL
												- MySQL
												- MariaDB
												- Oracle
												- Microsoft SQL Server
											- Read replicas available for most DB types, useful for read-heavy workloads
											- Multi-AZ DB instances involves a replica in another AZ
										- Availability and Durability
											- Automated backups
											- Database snapshots - user-initiated, stored in S3, only charged for incremental storage use
									- Steps
										- RDS > Databsaes > Create database > Standard create > MariaDB > Dev/Test > Instance configuration: Burstable classes + db.t3.xlarge > Storage: gp2 > Allocated storage: 20 > enable Storage autoscaling > Availability and durability: enable Multi-AZ deployment (standby instance) > Monitoring: enable Performance Insights + Enhanced Monitoring > Additional configuration: ensure Automated Backups + Encryption + Auto Minor Version Upgrade notare enabled
								- AWS Identity and Access Management (IAM) - creating an IAM group, attaching an access policy to the group and attaching a user to the group
								  collapsed:: true
									- Steps
										- IAM page > User groups > Create group > User group name: SupportEngineer > Attach permissions policies: `AmazonEC2ReadOnlyAccess` > Create Group
										- To add a user go to IAM page > Users > Create user
								- ((63a06e59-4078-4357-b478-dda42326daf4)) - setup and sharing files between three EC2 instances
								  collapsed:: true
									- Videos
									  collapsed:: true
										- 2 storage classes: Standard and Infrequent Access
										- To enable EFS IA, turn on EFS Lifecycle Management and it'll intelligently move files which are infrequently accessed to EFS IA
										- 2 performance modes: General Purpose and Max I/O
											- General Purpose = lowest latency per operation
										- 2 throughput modes: Bursting and Provisioned
											- Bursting = throughput scales with the size of the file system, dynamically bursting as needed
											- Provisioned = higher dedicated throughput
										- Encryption at rest + in-transit
									- Note: EFS doesn't have to be AZ-specific. Standard storage class uses multiple AZs, whereas One Zone is cheaper and uses a single AZ
									- Steps
										- 1) Create new NFS security group
											- EC2 > Security Groups > Create security group > VPC: choose the correct one > Add rule > Inbound rules > Type: NFS > Source: choose the correct security group (click on input) > Create security group
										- 2) Create the new EFS
											- EFS > Create file system > select the correct VPC > Customise > disable automatic backups + lifecycle management: transition in IA in order to reduce costs until you're in production > Next
											- Remove all existing security groups > add the new security group to one AZ > Next > Create
											- Click the EFS > Attach > copy the EFS mount helper code into a text file
											  id:: 64ac24f5-7c44-411f-90e7-2ba1492f24d9
										- 3) Mount it to each servers
											- 3a)
												- EC2 > Instances > select the first instance > Connect > Session Manager > `sudo -i` > `sudo yum install -y amazon-efs-utils` > `mkdir data` > `sudo mount -t efs -o tls fs-0424cwdwwdw4:/ data` > `cd data` >
												- EFS > enter new EFS > Network tab > Manage > Add mount target > select a different AZ, same subnet, same security group > Save > wait for status to turn "Available" (use the refresh button in tab) >
											- 3b) Repeat for second server
										- EC2 > Instances > select the second instance > Connect > Ses
										-
								- Amazon EC2 - Auto-Scaling and Auto-Healing
								  collapsed:: true
									- 1) Create an AMI of your EC2
									  collapsed:: true
										- EC2 > Instances (sidebar) > select your instance > Actions dropdown > Images and templates > Create image > AMIs (sidebar) > wait until Available status
									- 2) Create a launch template
									  collapsed:: true
										- EC2: Launch Templates (sidebar) > Create launch template > enable `Provide guidance to help me set up a template that I can use with EC2 Auto Scaling` > AMIs: My AMIs: Owned by me: (name of AMI) > Instance type: `t2.nano` > Create new key pair > `.ppk` for Windows/PuTTY or `.pem` for Unix-based shell with OpenSSH > Network settings: Select existing security group > Security groups: select the correct one > Create launch template > View launch templates
									- 3) Create an Auto Scaling group
										- EC2 > Auto Scaling Groups (sidebar) > Create Auto Scaling group > Launch template: select yours > Next > Instance launch options: select the right VPC > AZs and subnets: select both subnet names that are correct > Next > No load balancer > Health check grace period: 240 secs > Next > Capacity: Desired: 2 > Minimum: 2 > Maximum: 4 > Scaling policies: Target tracking scaling policy > Metric type: Average CPU utilisation > Target value: 70 > Skip to review > Create Auto Scaling group > select the AS group > Activity tab > check that the Desired number of instances were successfully launched
									- 4) Adjust the AS group to auto scale higher for a specific time slot
										- Automatic scaling tab > Create scheduled action > Desired capacity: 3 > Minimum: 3 > Maximum: 4 > Recurrence: every week > set a start date in the future
								- Amazon EC2 - ((6463499e-9ecf-4800-bf1f-65704c310016)) + Auto Scaling group for multiple instances across multiple AZs
								  collapsed:: true
									- Videos
										- ELB can load balance across EC2 instances, containers, IP addresses, ((6457bcad-7919-46a4-a9c0-8bb0ddf40189)) functions and virtual appliances
										- Region-level service
										- Internal-facing or internet-facing
										- 4 types:
											- Application Load Balancer - Layer 7 (App), best for HTTP/HTTPS/gRPC traffic
											- Network Load Balancer - Level 4 (Connection), best for TCP/UDP/TLS traffic
											- Gateway Load Balancer - Level 3 (Gateway) + Layer 4 (Load balancing), best for IP traffic
											- Classic Load Balancer - Level 4 (Connection) + Layer 7 (App) level, best for TCP/SSL/TLS/HTTP/HTTPS
									- Steps
										- 1) Put instances behind an ELB
										  collapsed:: true
											- EC2 > Auto Scaling Groups > select the group > Details tab > Load balancing section: click Edit > Add a new load balancer > Load balancer type: Application Load Balancer > Scheme: Internet-facing > select all 3 AZs with the public subnet > Default routing (forward to): Create a target group > Update
											- Security Groups (sidebar) > Create security group > VPC: select correct one > Inbound rules: Add rule > HTTP `0.0.0.0/0` > Outbound rules: Add rule > HTTP > Destination: correct security group + remove All Traffic `0.0.0.0/0` destination > Create security group
											- Security Groups (sidebar) > select the web server security group > Actions dropdown > Edit inbound rules > Delete the current anywhere `0.0.0.0/0`rule > Add rule > HTTP > Source: Load balancer security group > Save rules
											- Load Balancers (sidebar) > click it's Name > Security tab > Edit > remove the web server security group > add the load balancer security group > Save changes > Copy the DNS name and open it in a new tab
										- 2) Setup health checks
										  collapsed:: true
											- Target Groups (sidebar) > select it > Health checks tab > Edit > Protocol: HTTP > Health check path: `/path` > Advanced health check settings > Healthy threshold: 5 > Unhealthy threshold: 2 > Timeout: 2 seconds > Interval: 5 seconds > Save changes
										- 3) Setup Auto Scaling for 2 instances, in separate AZs, and remove the non-ELB instance
										  collapsed:: true
											- Auto Scaling Groups (sidebar) > select it > Details tab > Network section > Edit > change it to the private subnet1 > Update
											- Instances (sidebar) > select it > Networking tab > Subnet ID: check if it's still the old one > Instance state dropdown > Terminate instance > Refresh the page, soon there should be the instance with private subnet ID
											- Auto Scaling Groups (sidebar) > select it > Activity tab > review the Activity history > refresh the DNS health check webpage
											- Auto Scaling Groups (sidebar) > select it > Details tab > Network section > Edit > select both private subnets > Update
											- Auto Scaling Groups (sidebar) > select it > Details > Group details section > Edit > Desired capacity: 2 > Min: 1 > Max: 2 > Update
											- Auto Scaling Groups (sidebar) > select it > Activity tab > review the Activity history
											- Instances (sidebar) > select the instance that matches the new instance ID of the previous step > Networking tab > check that it's subnet 2 (different AZ from original) > refresh the DNS health check webpage
								- Amazon DynamoDB (NoSQL db)
								  collapsed:: true
									- Video
										- It's a key-value and document DB
										- It supports two types of primary keys: a partition key only, or a partition key and sort key (e.g. userId and lastDateWatched)
									- Steps
										- DynamoDB >  Create table > Table name e.g. UserVideoHistory > Partition key e.g. `userId` + String > Sort key e.g. `lastDateWatched` + Number
										- Click on the table Name when the Status is `Active` > Update settings (sidebar) > UserVideoHistory table radio button > Actions dropdown > Create item > Partition key e.g. `abcde` > Sort key e.g. `121312` > Add new attribute > String > `videoId` > Value e.g. `9875-djac-1859` > Create item
										- Scan/Query items dropdown section > Query > Partition key: (type the matching one) > Sort key: greater than (type a number) > Run
										- Scan - returns 1 or more items and item attributes by accessing every item in a table or a secondary index
										- Scan/Query items dropdown section > Scan > Run > it'll show all data
										  id:: 64ad7e4d-788e-42a9-8e35-85df53e3cdc7
										-
						- Lani's materials from TechTalent
						  collapsed:: true
						  8/10 - large breadth, but slideshow course itself isn't engaging
							- 1)
							  collapsed:: true
								- The Shared Responsibility Model (for security)
								  collapsed:: true
									- ![image.png](../assets/image_1689152038286_0.png)
								- ((649d8c7c-8ec0-4ad2-868d-0b9b03abeec0))
								- ((64a7ce5f-3e8c-4c88-9cae-e331f6815431))
								  collapsed:: true
									- {{embed ((64a7ce5f-3e8c-4c88-9cae-e331f6815431))}}
								- Stopped instances aren't charged for compute hours, but you will be charged for any associated EBS volume storage
							- 2)
							  collapsed:: true
								- ((64b81154-09ce-46c2-993a-0451497bcf3c))
								  id:: 663a5790-d3be-4c07-9b8f-36717b237100
								  collapsed:: true
								- Storage Services
								  collapsed:: true
									- Block-based storage is used for data that is split into fixed blocks of data and stored separately with unique identifiers (e.g. Amazon Elastic Block Store (EBS), local HDD). The blocks are reassembled and loaded into RAM when access is needed
									- Object-based storage on the other hand has a flat file hierarchy. Unlike filesystems, you must use an API call to access and manage objects (e.g. Amazon Simple Storage Service (S3))
									- File storage (e.g. ((63a06e59-4078-4357-b478-dda42326daf4)), NAS)
									- Each EC2 instance can have multiple attached EBS, but no more than one EC2 can attach to an EBS simultaneously. You'd need ((63a06e59-4078-4357-b478-dda42326daf4)) instead
									- When an EC2 instance is terminated, the primary attached EBS volume will also be deleted. Secondary attached volumes won't, and neither will be unattached EBS volumes
									- EBS snapshots live in the same Region, but not the same AZ. They live in an S3 bucket
									- AMIs come in 3 categories:
										- Community - free to use
										- AWS Marketplace - pay to use
										- My AMIs - ones you created
									- ((63a06e59-4078-4357-b478-dda42326daf4)) is built on the NFS protocol
									- EFS can only be attached to Linux-based instances, but can also be attached to on-premise client site devices through a VPN or with Direct Connect
									- S3 objects are retrieved using key-value pairs - key being the filename, and value being the file data
									- S3 Gateway Endpoints can be used for maximum security with it's private connection, instead of traditional Internet Gateway Endpoints
									- S3 objects can be max 5TB each
									- S3 buckets have a globally unique namespace, however a Region-based resources
									- Notable features of S3:
										- Transfer acceleration - uses CloudFront's Edge locations
										- Requester Pays - rather than bucket owner for requests and data transfer
										- Events - trigger notifications to SNS, SQS or ((6457bcad-7919-46a4-a9c0-8bb0ddf40189)) when certain events happen
										- Static Web Hosting
										- Versioning and Replication
									- Availability in S3 = uptime
									- Replication - can be Cross-Region Replication (CRR) or Same-Region Replication (SRR)
									- S3 Lifecycle Management includes transition actions and expiration actions
									- AWS Storage Gateway is a hybrid cloud storage service used to storage on-premises data into an S3 bucket
										- 3 types:
											- File Gateway - uses NFS
											- Volume Gateway - block-based, uses S3
											- Backup Gateway - uses block or file-based storage
									- Amazon Route 54 (DNS)
										- A hosted zone = a set of records belonging to a specific domain
									- Scaling up = vertical scaling
									- Scaling out = horizontal scaling
									-
							- 3)
								- Application Services
								  id:: 64aeb4fc-29ea-4c22-9718-06bd6d69fffd
								  collapsed:: true
									- ((6457bcad-7919-46a4-a9c0-8bb0ddf40189)) uses millisecond billing, not whole second billing
									- ((64b7c5bd-a765-4700-8546-43162a29aea8))
									- ((64b7c595-93d7-46b1-9900-853028feed64))
									- ((64b7c5ea-fc23-4c8f-bba3-40309679cf7d)) vs Simple Workflow Service
									  id:: 64aeb5a0-c8b0-447a-89db-d4f0b653b337
										- ((64b7c5ea-fc23-4c8f-bba3-40309679cf7d))
										  id:: 64aeb5b6-61e1-4b80-8fa3-ff56b3e8f157
											- Can orchestrate part of your service e.g. each can be a ((6457bcad-7919-46a4-a9c0-8bb0ddf40189)) function
										- [Amazon SWF](https://aws.amazon.com/swf/details/)
										  id:: 64aeb5c9-219a-40c1-9cc7-e8f66c8950cc
										  collapsed:: true
										  AKA Simple Workflow Service
											- Similar to ((64aeb5b6-61e1-4b80-8fa3-ff56b3e8f157)) but much older. Main difference is SWF is used for asynchronous systems e.g. human-enabled workflows like order fulfilment
											- Documentation
												- One responsibility of the decider is to schedule activity tasks and provide input data to the activity workers. In addition to its normal responsibilities, the decider will execute events that show up while the workflow is executing. The decider will also close the workflow once it validates that the entire objective has been completed. Overall, the decider will coordinate tasks by validating concurrency that exists, processing their order, and scheduling the tasks based on application requirements.
												- A worker service is responsible for getting tasks and sending the task details back to Amazon SWF, not the decider.
												- The worker service, not the decider, processes all tasks that have been received.
												- A worker service also gives the results of the tasks back to Amazon SWF. All of these processes are related to worker services and are not the responsibility of the decider.
									- Amazon API Gateway
										- Region-based, serves as a gateway for your APIs. Backend can be any AWS service or workflow/step function etc
								- VPC, Networking and Hybrid
								  collapsed:: true
									- VPCs are Region-specific
									- Each VPC has a different block of IP addresses. It uses Classless Inter Domain Routing (CIDR) to assign a range of IP addresses to the VPC, which are then filtered into the subnets.
									- Each subnet of the VPC will have a block of those IP addresses from the initial VPC CIDR block.
									- All information leaving a subnet must go through the router. The router understands where to send data due to its routing table.
									- Security Groups and Network ACLs
										- Security groups are stateful
											- When we consider a stateful firewall, if the incoming traffic was accepted, the outgoing traffic is automatically allowed.
										- Network ACLs are stateless.
											- A stateless firewall, on the other hand, will check rules for both incoming and outgoing connections.
										- Network Access Control Lists (NACLs) are applied at the subnet level and will only apply to traffic entering or exiting the subnet. If we have two instances on separate subnets, both subnets will need the correct inbound and outbound allow rules to allow communication between them via the router.
										  
										  Network ACLs have both inbound and outbound rules and have an “allow” and a “deny” concept. These rules are numbered and executed in order, with the latest one being the rule listened to.
										  
										  A security group applies at the instance level, and you can apply the same security group to instances in different subnets and different availability zones.
										  
										  Instances within the same subnet that wish to communicate with each other do not have intervention from the NACL.
									- Private IPs are used for internal communication within the VPC. These don't change, unlike a public IP (it only changes when an instance is stopped, and if you don't use an Elastic IP)
									- NAT Gateways allow instances in private subnets to communicate with the internet
									- VPC Peering links are non-transitive. This means that we cannot route from 1 VPC through another VPC, to reach a third, destination VPC.
									- AWS Transit Gateways should be used to scale VPC peering
										- Instead of using VPC Peering to connect every VPC to every other VPC, we connect the VPC directly to a transit gateway. You can think of this as a router for your VPC (in appose to routers for subnets which communicate with internet gateways).
									- AWS Outpost - extends some AWS functionality to on-premise data centers
										- Limited number of services available but includes important ones like:
											- EC2, EBS, S3, VPC, ECS/EKS, RDS, EMR (Elastic Map Reduce)
								- Deployment and Automation
								  collapsed:: true
									- AWS Global Accelerator works similarly to CloudFront except it improves application performance across TCP and UDP and isn't concerned with cached data
										- It also uses AWS Global Network, which are dedicated network channels that are separate from the internet
									- AWS Cloud Development Kit (CDK) allows developers to write config files that work like CloudFormation's JSON/YAML files instead in programming languages like Python, TypeScript, Java, .NET, etc
									- ((6463499d-63a1-485e-bf7e-1bae513fd542))
										- is a PaaS that allows developers to easily deploy EC2, ELB, auto scaling, subnets, databases etc
										- Supports a wide range of programming languages such as Java, .NET, PHP, Docker, etc
										- Developers still have full control over the underlying resources if they wish
									- Developer tools
										- Code* (pronounced as Code Star) is an IDE connected service that introduces CI/CD tools
										- ((64b7f676-aaa5-4351-aeee-dcc14b014bae)) is a central repo system
										- ((64b7f66c-86f0-443a-b53b-190d004e78e7)) does building and testing
										- ((64b7f692-54e9-4bcf-95f9-301d3c298b1d)) will deploy code after tests are passed
										- ((64b7f69c-6359-41e8-ae5d-bccf8b1f1a4d)) - connects ((64b7f676-aaa5-4351-aeee-dcc14b014bae)), ((64b7f66c-86f0-443a-b53b-190d004e78e7)) and ((64b7f692-54e9-4bcf-95f9-301d3c298b1d)) together
										  id:: 64aec668-6f11-4961-a756-812c86bf8a37
									- ((64b7f73d-a5c9-4ec8-895e-ef8e5ab585d9)) - allows debugging AWS services e.g. EC2, Lambda, SQS, etc
									- AWS OpsWorks - managed Chef and Puppet (automation)
								- Database and Analytics
								  collapsed:: true
									- Aurora are proprietary versions of MySQL and Postgres with faster performance
									- DynamoDB is the NoSQL version - global scope so it is multi-region, multi-master
									- RedShift - SQL-based data warehouse, runs on EC2 instances
									- Elastic Map Reduce (EMR)
									  id:: 64aec848-b92e-472c-9ce1-80fbd7b547bf
										- Managed implementation of Hadoop/Spark
										- Apache Hadoop is a framework used to efficiently store and process large datasets, ranging in size from a few gigabytes to petabytes.
										- Apache Spark is also a data processing framework that can quickly perform processing tasks on very large data sets with a focus on machine learning and real-time workloads.
									- ((6463499e-529d-478c-822f-2ff43f26b6bf))
									- Athena = let's you run SQL queries against non-SQL data
									  id:: 64aec89f-45fa-4e04-92c7-6b5e98334647
										- e.g. CSV, TSV, JSON, Parquet
										- service pointed at S3 or data services within ((6457bcad-7919-46a4-a9c0-8bb0ddf40189))
									- AWS Glue = metadata catalog that can be used with Athena to store info and schemas about the databases generated by Athena
										- Works with other data lakes such as S3, data warehouses like RedShift, and databases like RDS or EC2
									- ((64b7ba97-a707-4786-a823-3a0ca7b2d177))
									  id:: 64aec97d-37c3-47cf-ac69-109e02c3b8f0
									- *Others*
										- AWS Data Pipeline – Processes and moves data between different AWS compute and storage services.
										- Amazon QuickSight – A Business Intelligence (BI) service used to create and publish interactive dashboards for machine leaning powered insights.
										- Amazon Neptune – A fully managed graph database service.
										- Amazon DocumentDB – A non-relational document database service which supports MongoDB workloads.
										- Amazon Quantum Ledger Database (QLDB) – Ledger database for immutable change history which provides cryptographically verifiable transaction logging.
										- Amazon Managed Blockchain – Managed service for joining public and private networks using Hyperledger Fabric and Ethereum
								- Management and Governance
								  collapsed:: true
									- AWS Control Tower - simplifies setup of multi-account environments. Allows automating AWS Organisations
									- AWS System Manager = manage and automate EC2, S3 and RDS
										- The features include:
										- Automation – Can do automated activities such as snapshots to be taken of an RDS database
										- Run Command – Can do commands such as checking for missing updates on EC2 instances
										- Inventory – All of the managed systems report information about themselves into a dashboard
										- Patch Manager – Deploy system and software packages across large groups of EC2 instances (requires an agent)
										- Session Manager – Secure remote management of your instances without logging into them
										- Parameter Store – Stores information such as secrets, passwords, or configuration information about services
									- AWS Service Catalog is a service that we can use to create catalogues of IT services that we can pre-approve for consumption on AWS.
										- i.e. CloudFormation templates which include databases, instances, etc
										- Catalog of products can be placed into a portfolio which is then assigned to users and groups
									- AWS Config is a service used to audit the configurations of the AWS resources. It can be used to validate that our resources are configured in a way that is compliant with the rules that we establish.
										- It can then use SNS, CloudWatch events, or Lambda functions for example to rectify the config changes and alert IT admins
									- Health API and Dashboards
										- See the health of various resources, alerts when AWS is experiencing events that could impact you
										- Service Health Dashboard - general info about downtime of various services or any data issues
							- 4)
							  collapsed:: true
								- AWS Cloud Security and Identity
								  collapsed:: true
									- AWS Security Token Service (STS) works with Microsoft Active Directory via on-premises Active Directory Federation Services (ADFS) to provide identity/authentication
									- IAM Identity Center enables centralised permissions and single sign-on
									- ((6463499e-3bb4-49ea-90d5-2df420c0fb1e)) : ((662a2de9-0665-42c2-916e-20503bb54acc))
									- [AWS Directory Service](https://aws.amazon.com/directoryservice/)
									  id:: 64afc836-955f-4e6a-a145-6ca6ea566f42
										- Suite of products for hosting a directory service or connecting to one
										- AWS Directory Service for Microsoft Active Directory
										  AKA AWS Managed Microsoft AD
										- Also has versions for LDAP (Lightweight Directory Access Protocol)
									- Active Directory (AD) Connector - connects on-premise active directory with AWS services
									- Directory Service Comparison
										- | Directory Service | Service Description | Use Cases |
										  | AWS Directory Service for Microsoft Active Directory | AWS-managed full Microsoft AD running on Windows Server 2012 R2 | Enterprises that want hosted Microsoft Active Directory |
										  | AD Connector | Allows on-premises users to log into AWS services with their existing AD credentials | Single-sign on for on-premises employees |
										  | Simple AD | Low scale, low cost, AD implementation based on Samba | Simple user directory, or you need LDAP compatibility |
									- Protecting secrets
										- ((64b80795-b0df-423c-a9f6-0b4e1cc37ff5)) Parameter Store - hierarchical storage for configuration data management and secrets
										- AWS Secrets Manager - additionally allows native + automatic rotation of keys and password; central auditing for secret rotation; fine-grained permissions; allows multiple version of a parameter to exist the same time (differentiated by staging labels)
									- AWS Certificate Manager (ACM) - responsible for creating, storing and renewing SSL/TLS certificates
									- AWS Key Management Store
									  Used to create both symmetrical + asymmetrical encryption keys
									- CloudHSM (cloud-hosted Hardware Security Module) has similar features by slightly more secure
										- Customer-managed custom master keys can be protected by hardware security modules
										- It's run in a VPC and is single tenancy, whereas KMS is multi-tenancy
									- Logging and Auditing
										- [Amazon CloudWatch Logs](https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/WhatIsCloudWatchLogs.html)
										  id:: 64aff99c-1c8f-4bdd-971d-3b34066116e4
										  collapsed:: true
										  Monitor, store and access your log files from other ((6463499e-7e3f-4d66-89b4-cf300a0dcda7))
											- Search, query language, can be used with on-premise infrastructure using the Unified CloudWatch Agent daemon on devices
										- ((6463499e-fe31-4613-8b61-e232816b6ddb))- helps enable operational and risk auditing, governance and compliance
										  collapsed:: true
											- All events are stored in CloudTrail for 30 days
											- For indefinite storage use CloudTrail Trail, to then store logs in S3
										- [VPC Flow Logs](https://docs.aws.amazon.com/vpc/latest/userguide/flow-logs.html)
										  id:: 64affa40-c29d-428b-bc82-4bfc8687bdb7
										  Audit and log VPC, these logs are stored in ((64aff99c-1c8f-4bdd-971d-3b34066116e4))
											- Which Amazon resource could you use to gather IP addresses for subnets classified as private within your VPC infrastructure?
										- Amazon Detective
										  collapsed:: true
										  Used to analyse, investigate and identify the root cause of potential security issues or suspicious activity
											- It automatically collects data from your resources and uses machine learning, statistical analysis, and graph theory to support it in its investigation.
											- It will create a unified, interactive view of your resources and maps the interactions between them.
											- The data sources that you can feed into Amazon Detective include VPC Flow Logs, ((6463499e-fe31-4613-8b61-e232816b6ddb)) API activity, and information from something called GuardDuty.
										- GuardDuty 
										  collapsed:: true
										  is an intelligent threat detection service. It detects account compromise, instance compromise, and malicious reconnaissance activities.
											- It provides continuous monitoring for events across:
											  collapsed:: true
												- AWS CloudTrail Management Events
												  AWS CloudTrail S3 Data Events
												  Amazon VPC Flow Logs
												  DNS Logs
										- Amazon Macie 
										  collapsed:: true
										  is a fully managed data security and data privacy services. It uses machine learning and pattern matching to discover, monitor, and help protect your sensitive data stored within S3.
											- This means that Macie is capable of inspecting the data stored within S3.
											- It enables security compliance and preventative security and can identify a variety of data types including:
											  collapsed:: true
												- Personally Identifiable Information (PII)
												- Protected Health Information (PHI)
										- AWS Web Application Firewall (WAF) - firewall
										- AWS Shield - mitigate DDoS attacks. Free and paid version
										- AWS Artifact - access to AWS compliance reports
										- AWS Security Hub
										  collapsed:: true
											- provides a comprehensive view of security alerts and security posture across AWS accounts. It aggregates, organises, and prioritises security alerts, or findings, from multiple AWS services.
											  
											  AWS Security Hub continuously monitors your environment using automated security checks, and allows security standards to validate against accepted industry standards:
											  AWS Foundational Security Best Practices
											  Center for Internet Security (CIS) AWS Foundations Benchmark
											  PCI Data Security Standard (DSS)
										- Penetration testing
										  collapsed:: true
											- You're allowed to carry our assessments of their infrastructure without prior approval on:
											  collapsed:: true
												- Relational Database Services and Aurora
												  EC2 instances, WAF, NAT Gateways, and ((6463499e-9ecf-4800-bf1f-65704c310016))
												  CloudFront
												  API Gateways
												  Elastic Beanstalk environments
												  Transit Gateway
												  S3 hosted applications (although targeting S3 buckets is strictly forbidden)
											- You're not allowed to do the following:
											  collapsed:: true
												- DNS zone walking via Route 53
												  DNS hijacking via Route 53
												  DDoS attacks
												  Port flooding
												  Protocol flooding
								- AWS Cloud Adoption Framework (AWS CAF)
								- Migraiton, Machine Learning and More
								  collapsed:: true
									- AWS Migration Hub
									- There is the AWS Database Migration Service used for migrating databases into RDS.
									  
									  AWS DataSync used to migrate NAS and File servers so S3.
									  
									  AWS Application Migration Service (AWS MGN) for lift-and-shift migrating applications to EC2 instances.
									- Snowball family of devices
										- Snowcone
										- Snowball
										- Snowmobile
										- ![image.png](../assets/image_1689256083690_0.png)
									- Machine Learning services
										- AWS Rekognition – Capable of identifying objects within images and videos
										  AWS Transcribe – Adds speech to text capabilities to applications
										  AWS Translate – Used for language translation
										  Amazon Textract – Used to extract printed text, handwriting, and data from any document with OCR
										  Amazon SageMaker – Allows scientists and developers to prepare, build, train, and deploy high-quality machine learning models
										  Amazon Comprehend – A Natural-Language Processing (NLP) service used to uncover information in unstructured data and identify sentiment in your content.
										  Amazon Lex – A conversation AI for chatbots
										  Amazon Polly – Turns text into life-life speech
									- End User Computing
										- Amazon Workspaces – Managed, Desktop-as-a-Service (DaaS) solution. It manages streaming gateways and brokering services, so you don’t have to.
										  
										  AWS AppStream 2.0 – Fully managed, non-persistent application streaming service such as Office products, development tools, or browsers.
										  
										  AWS WorkLink – Provides a secure, one-click access to your internal websites and web apps using mobile phone browsers. Does not require a VPN client or installed application.
										  
										  AWS WorkDocs – Secure content creation, storage, and collaboration service allowing users to create, edit, and share content that’s centrally stored on AWS.
									- AWS IoT Core - lets you connect IoT devices to the AWS cloud without the need to provision or manage servers and can support billions of devices, and trillions of messages.
									- AWS Device Farm - is an application testing service that lets you improve the quality of your web and mobile apps by testing them across an extensive range of desktop browser and real mobile devices, without having to provision and manage any testing infrastructure.
									- AWS Knowledge Center - their personal docs and wiki
									- Amazon Connect - their customer service center
									- AWS Lightsail - simpler EC2, preconfigured images for tools like WordPress, Node.js, Magento etc
									- AWS CloudShell and ((6544c9ef-05f1-41f8-8062-a6f5dc3cc6ad))
										- both work the same way. They are used to quickly run scripts and AWS specific commands in a Command Line Interface (CLI).
										- They can be further provisioned to experiment with service APIs, and other tools to increase your productivity.
										- The difference between the two:
											- AWS CloudShell is browser based and is part of your Management Console
											- ((6544c9ef-05f1-41f8-8062-a6f5dc3cc6ad)) is a locally downloaded program that can communicate with AWS from your local machine
								- Accounts, Billing and Support
									-
						- [AWS Certification Prep](https://app.pluralsight.com/explore/certifications/topics/aws?trackId=b2dc79ce-d1ad-4797-92fb-3b39922947b6) - Pluralsight practice exam
						  id:: 64ba5113-7159-4353-aa54-7f06e487872f
						  collapsed:: true
						  9/10
							- [Simulated exam](https://www.kaplanlearn.com/education/qbank/view/81858185?testId=258739203) [[2023-07-21 Friday]]
								- ((64a42901-ffd2-4028-b1c5-269b205e4dd0))
								- ((64b8079f-24fc-46b2-9015-d7bd15713de3)) : ((64ba5a3d-a4b6-483d-ac63-1accc15b8dd4))
								- ((64b7f692-54e9-4bcf-95f9-301d3c298b1d))
								- ((64a81c33-b200-4f6f-aeef-939216e1d932))
								- ((64a81b9b-0f08-478f-877f-893ad0b18587))
								- ((64b804c0-e44f-4279-a3d1-1202b16c19f4))
								- ((6463499e-42ab-4a58-8911-df6138dfee8f)) : ((6463499e-8216-4942-bd04-14d71330b7d6))
								  collapsed:: true
									- {{embed ((6463499e-8216-4942-bd04-14d71330b7d6))}}
								- ((6463499e-1f1d-4439-ac9b-26c7fb1bd86f)) : ((64ba8f54-9b77-497a-8931-018453acf40a))
								  collapsed:: true
									- {{embed ((64ba8f54-9b77-497a-8931-018453acf40a))}}
								- ((64b81154-09ce-46c2-993a-0451497bcf3c))
								  collapsed:: true
									- ((6463499e-3cba-49b6-8dba-355fa353fe90))
										- {{embed ((6463499e-3cba-49b6-8dba-355fa353fe90))}}
									- ((64ba958e-226d-40bf-88ca-468dea441069))
										- {{embed ((64ba958e-226d-40bf-88ca-468dea441069))}}
								- ((6463499e-971f-49ad-9136-306a4377fe86))
								- ((64b804b9-35d0-44c6-a7c6-d6908582a9a3))
								- ((64b7f40b-fa53-4f71-969f-3cfe64407747))
								- ((6463499e-177d-4f57-a6c6-9c947d98a39a))
								- ((64a2ea92-920d-496d-9418-fd74d9bbded0))
								- ((6463499e-bd2d-4c48-b05b-bdddeb7d8bba)) : ((64ba9532-ffd9-4f28-8237-5ed6f1c6fd7b))
								- ((6463499e-5ffa-47d2-aeb5-b9a8bce9bc64))
								- ((6463499e-fe31-4613-8b61-e232816b6ddb))
								- ((649d87b0-9a8c-4fe8-8a4f-2c9491a0c041))
								- Purpose behind configuring dynamic architectures for growth and elasticity on AMS
								  collapsed:: true
									- A: AWS usage should be focused on building applications spread across multiple AZs and Regions
									  collapsed:: true
										- AWS usage should be focused on building applications spread across multiple Availability Zones (AZ) and Regions. You can always extend your application by adding load balancers and additional AZs to your preconfigured scaling group, but spreading your application workload across different AZs and even Regions will create a level of increased elasticity with expanding application functionality and data integrity.
										- You never want to focus on reducing costs when expanding the architecture of your application. The key is to separate your primary functions onto different Amazon Elastic Compute Cloud (EC2) instances and add additional AZs and Regions as needed.
										- AWS usage focused on Amazon S3 components is too finite of an option from an architectural perspective.
										- Auto Scaling is a great feature to account for dynamic solutions to changes in your business, but application architectures should focus on
										  adding Regions and AZs, not increasing capacity.
								- ((649d87db-e0f6-4fd3-b82c-22a095dba688))
								- Security policies
								  collapsed:: true
									- Default security policy
										- Default security policy is not the correct choice. This type of policy is assumed because when you create an AWS account, a default security
										  group is created automatically within the default virtual private cloud (VPC). An ELB uses a predefined security policy rather than a default.
									- Resource-based policy
										- Resource-based policy is not the correct choice because this type of policy uses JavaScript Object Notation (JSON) documents to attach to
										  specific AWS resources and work with inline policies. This type of policy is used within the Amazon Simple Storage Service (S3) infrastructure.
									- Predefined security policy
										- A predefined security policy allows you to determine which protocols and ciphers are used when negotiations are occurring between the load balancer and the client. Elastic Load Balancing (ELB) uses the configuration of the load balancer to leverage a custom security policy or a predefined security policy. These policies meet the security standards and compliance requirements that also disable specific Transport Layer Security (TLS) protocol versions.
										- Suitable for ensuring the connection between EC2 and ELB is using correct SSL
									- Geolocation routing policy
										- Geolocation routing policy is not the correct choice because this form of routing is only based on the geographic location of moving traffic and
										  is not a security policy.
								- ((64baba4c-1ea5-48a6-adb8-056e4591fda1))
								- ((64a3dff5-efbe-4d9e-9baf-0106aae2dc78))
								- ((64a2ed7b-5edf-49b3-9619-9598f7df6139))
							- Simulated exam [[2023-07-24 Monday]]
								- ((64b81083-d55d-46c5-b58c-76342dc6a8ca))
								- ((64b7ba97-a707-4786-a823-3a0ca7b2d177))
								- To protect data-in-transit, Amazon recommends SSL/TLS, and/or IPSec ESP
								  collapsed:: true
									- Amazon supports IPSec, which is Internet Protocol Security, used in combination with a virtual private network (VPN) network. ESP stands for Encapsulating Security Payload, which is a protocol that can protect data integrity and create authentication for network packets, or what is referred to as payloads, that can be encrypted/decrypted. You could also use both forms of encryption (SSL/TLS and IPSec ESP). When it comes to accidental disclosure of private information, you should always limit access. Amazon describes the concern of having confidential information touch a public network, which should always have a basic level of encryption.
								- [AWS Security Competency Partners](https://aws.amazon.com/security/partner-solutions/)
								  collapsed:: true
								  Should be used to ensure your company meets security and copliance requirements, and implements best practices whilst migrating to AWS
									- You would use AWS Security Competency Partners. AWS Security Competency Partners provide various security solutions, which can help ensure that AWS customers meet security and compliance needs through all stages of cloud adoption from migration to daily management. AWS Marketplace has
									  various security solutions from third-party vendors.
									- You would not use AWS Trusted Advisor. AWS Trusted Advisor is a tool that indicates how you should provision your AWS resources as per AWS best
									  practices. It performs real-time monitoring of your AWS resources and recommends actions accordingly.
								- ((6463499e-1f1d-4439-ac9b-26c7fb1bd86f)) : ((64be49bd-8041-491c-a18d-d65b9f866c88))
								  collapsed:: true
									- {{embed ((64be49bd-8041-491c-a18d-d65b9f866c88))}}
								- ((64a2ea92-920d-496d-9418-fd74d9bbded0)) : ((64be4a55-3db0-4849-ab3f-1e608063b1cb))
								- ((64b80fb8-db41-4dd8-9edd-b10a77a45104))
								- ((64a6babe-8836-4d19-a205-1268fb2f2c57))
								- ((64aeb5c9-219a-40c1-9cc7-e8f66c8950cc))
								- {{embed ((64affa40-c29d-428b-bc82-4bfc8687bdb7))}}
								- {{embed ((64aff99c-1c8f-4bdd-971d-3b34066116e4))}}
					- Related: ((6463499e-7e3f-4d66-89b4-cf300a0dcda7))
			- L2 - Associate
				- [AWS Certified Developer - Associate](https://aws.amazon.com/certification/certified-developer-associate/)
				  id:: 64b11870-c4ec-4240-af29-9096c4d535ab
				  collapsed:: true
					- Qualifications + weeks
					- Content
						- QA ecourse: Developing on AWS
						  collapsed:: true
						  [[2024-09-24 Tuesday]] 3-day full-time online course
							- Logistics
								- 09:00-17:00
								- 12:00-12:45 lunch break
								- AWS Labs
									- Resources take 10-15 mins to create, and stay available for about 8 hours
									- You can preload up to 2 labs at a time
								- [VitalSource Bookhshelf](https://bookshelf.vitalsource.com/)
									- You can export books as PDF if desired
									- Access remains available for 2 years
							- Links
								- [AWS Labs for this course](https://classrooms.aws.training/class/1gAyM8rYKMuHvWQGMKw2iU)
								- [[Student Guide](https://online.vitalsource.com/reader/books/200-DODEVA-45-EN-SG-E/pageid/2) (i.e. 582 page slides for course)
									- ![VitalSource Bookshelf_ Developing on AWS 4.5.10 (EN)_ Student Guide-OCRd.pdf](../assets/VitalSource_Bookshelf_Developing_on_AWS_4.5.10_(EN)_Student_Guide-OCRd_1727178659716_0.pdf) - **use this**
									- ![VitalSource Bookshelf_ Developing on AWS 4.5.10 (EN)_ Student Guide.pdf](../assets/VitalSource_Bookshelf_Developing_on_AWS_4.5.10_(EN)_Student_Guide_1727173634243_0.pdf)
							- Review
								- Instructor Pranav Phadke of QA has too strong an accent, hard to understand. Going through the content too fast, often coughing on day 2
							- Overview
								- Building an app using these multiple AWS services - graphic
								  collapsed:: true
									- ![image.png](../assets/image_1727165283555_0.png)
								- List of AWS services
									- ((64b81154-09ce-46c2-993a-0451497bcf3c)) for user authentication
									- ((6529032b-bb04-4660-836b-f33e1ae727ba)) to glue S3 static web hosting to Lambda
									- ((6463499e-5ffa-47d2-aeb5-b9a8bce9bc64)) to monitor the application, alarms, events, logs
									- ((64b7f73d-a5c9-4ec8-895e-ef8e5ab585d9)) for end-to-end tracing, debugging, analysis, service maps
									- ((6463499e-971f-49ad-9136-306a4377fe86)) to store user notes and interactions
									- ((64b804b9-35d0-44c6-a7c6-d6908582a9a3)) for converting MP3 files to?
									- ((6463499e-3bb4-49ea-90d5-2df420c0fb1e)) for user authentication (people can easily sign up to pools)
									- ((6620d4c0-1c5f-4f16-bfee-cf33e7cf5ffd)) for testing app locally before pushing it, and simple templates
									- ((6457bcad-7919-46a4-a9c0-8bb0ddf40189)) for business logic CRUD operations
									- ((6463499e-42ab-4a58-8911-df6138dfee8f)) static website hosting and user file storage
							- # Day 1
							  collapsed:: true
								- ## Agenda
								  collapsed:: true
									- ![image.png](../assets/image_1727165334721_0.png)
									- ![image.png](../assets/image_1727165389242_0.png)
								- # ((66f43362-da2a-4325-9457-c8e0f3abf725))
									- ## ((66f43372-ce12-43fe-abd0-f0488e484f1f))
									  collapsed:: true
										- By the end of this module, you will be able to:
											- Describe the architecture of the application you are going to build during this course.
											- List AWS services needed to build your web application.
											- Determine how to store, manage, and host your web application
									- ((66f433e8-23a2-46de-8901-c7725a2bca78))
									- ((66f433f5-3c2c-4c88-a93d-ea828f398eeb))
									- ((66f43405-b64d-42ac-a469-6b1cff2b4c0e))
									- ((66f4340c-eed9-47f6-ad59-57f27feeb64c))
									- ((66f43418-20e6-4f4e-b375-7d0c7afa9f9c))
									- ((66f4342f-16f1-4f33-8373-e09d19cb19cf))
									- ((66f43443-1efe-44b0-b93a-ef3eb1e61561))
									- ((66f43453-d092-4d1f-b923-36778095bd90))
									- ((66f4345c-9ccf-4246-9966-024157de6663))
									- ((66f43466-bfbb-45c0-aa73-46b083062746))
								- # ((66f2a7e7-ae96-4bee-8e3d-6fe36b501a52))
								  collapsed:: true
									- ## ((66f43476-469c-4e52-8ed4-d9c63f5ef3f9))
										- By the end of this module, you will be able to:
											- Describe how to access AWS services programmatically.
											- List programmatic patterns within AWS SDKs.
											- Explain the value of AWS Cloud9
									- ## ((66f2a894-ea8f-4126-8141-d09a17c3ec1c))
										- ((66f434a1-67ab-47df-a35a-8cecd21e40e2))
										- ((66f434b1-5548-4892-be38-694d2f3dea75))
										- ((66f434c0-5108-4a03-bec8-d6a1dd7adff7))
										- ### Accessing AWS services
											- Accessing AWS services
												- ((64b806d2-fdd2-4f63-84b8-4f0b76f20027))
												  logseq.order-list-type:: number
												- HTTP request/response
												  logseq.order-list-type:: number
													- ((5ac78cbc-ed2d-4914-ab68-b05c2d27e278))
												- ((6544c9ef-05f1-41f8-8062-a6f5dc3cc6ad))
												  logseq.order-list-type:: number
												- SDKs e.g. Boto3 for [[Python]]
												  logseq.order-list-type:: number
												  collapsed:: true
													- Pros
														- Language binding
														- HTTP request signing
														- Built-in resilience
															- Logic for retries/errors/timeouts
														- Pagination support
											- ((66f434f5-833f-444b-b55d-0b835e344500))
											- ((66f43509-70f9-4813-8c09-068267d8f3ae))
											- ((66f43518-2060-4b12-b3b5-d64a7ed05b5c))
											- ((66f43526-c485-4e24-bf5d-074d40d7780d))
										- ((66f43535-7444-4e3f-b569-256c22825e0e))
										- ((66f4353d-b129-43d0-96f0-bf21663ddd41))
										- ((66f2add9-f709-47fc-b310-a7c3302aa5b2))
											- ((66f2adea-6d27-46e3-9fd8-d6153f30dd6c))
										- ((66f2adfa-0086-4cab-9735-f4e19611e111))
											- High-level is preferred because it's simpler
									- ## ((66f2ae09-10dc-4ba3-9285-d656dbeae73c))
										- ((66f4355d-ef23-468f-9cd8-a52a218edb34))
											- ((6544c9ef-05f1-41f8-8062-a6f5dc3cc6ad)) can be invoked
											- Invoke locally e.g. [[Terminal]]
											- Invoke remotely: e.g.
												- EC2 over SSH, ((64b7f629-76b1-4695-9eec-3caea77b1452)), ((663a5791-49d2-4403-a63a-2b12c34bd94d)), ((64b80795-b0df-423c-a9f6-0b4e1cc37ff5)) Session
										- ((66f4358a-1123-4c31-b710-902e5f16ce61))
									- ## ((66f2aef3-1dd9-4414-8756-1a4c5dd8b696))
										- ((66f4359c-40c2-4f83-99e7-e135d454a7b5))
											- Operation calls on AWS services can be synchronous or asynchronous. Lambda can be invoked synchronously or asynchronously. Amazon S3 invokes functions asynchronously. The CreateTable operation for DynamoDB is an asynchronous operation.
										- ((66f435b2-c50f-41dc-a108-858d98cda1d1))
										- ((66f435bf-d523-4647-93c1-15613d5de156))
										- ((66f435c9-d1af-40dc-94b4-6cc57865dee0))
										- ((66f435d3-a4d5-4ed8-860e-278866b2b35e))
										- ((66f435dd-3794-490e-ba3f-11104354edab))
										- ((66f435e9-66e8-4a4b-89ad-2c0f752bc04c))
									- ## ((66f435fa-19f9-4157-8864-901caa87b296))
										- ((66f4360a-c7b5-4ae4-a7a1-6e30b82ac2c3))
										- ((66f43613-784c-433e-94d8-776af682042c))
											- ((64b7f629-76b1-4695-9eec-3caea77b1452))
									- ## ((66f43623-21f8-4a9e-949b-1d6575bf90e9))
										- ((663a58ef-dc8d-4e09-b151-7ca8ba6f1cf3))
										- ((66f43632-5f70-430a-a55d-d545f8978e19))
										- ((66f43644-bb84-4a07-abaf-597ff6733894))
										- ((66f4364c-2027-44dc-9261-5f603353cb3c))
										- ((66f43653-4322-4d78-8b48-80ca9d0fa16b))
									- ## ((66f43664-a935-4762-81ff-4b7985236588))
									- ## ((66f2bc50-a2bb-4788-9c5b-4b15e90bbc6f))
									  collapsed:: true
										- False
										  logseq.order-list-type:: number
											- Because resource APIs give more abstraction
											  logseq.order-list-type:: number
										- True
										  logseq.order-list-type:: number
										- True
										  logseq.order-list-type:: number
											- They have exponential backoff e.g. ((6463499e-971f-49ad-9136-306a4377fe86)) waiting for a response
											  logseq.order-list-type:: number
										- False
										  logseq.order-list-type:: number
											- Client error is 400 errors
											  logseq.order-list-type:: number
										- True
										  logseq.order-list-type:: number
										- True
										  logseq.order-list-type:: number
								- # ((66f2a8f5-c9b3-4180-af9b-74c5c8844cd6))
								  collapsed:: true
									- Example exam questions
									  collapsed:: true
									  1 from Official Practice Question Set: AWS Certified Developer - Associate (DVA-C02 - English)
										- A developer is building a new application that transforms text files to .pdf files. A separate application writes the text files to a source Amazon S3 bucket. The new application must read the files as they arrive in Amazon 53 and must convert the files to .pdf files by using an AWS Lambda function. The developer has written an IAM policy to allow access to Amazon 53 and Amazon CloudWatch Logs. What should the developer do to ensure that the Lambda function has the correct permissions?
										  collapsed:: true
											- Correct
												- A) Create a Lambda execution role by using AWS Identity and Access Management (IAM). Attach the IAM policy to the role. Assign the Lambda execution role to the Lambda function.
											- Incorrect
												- B) Create a Lambda execution user by using AWS Identity and Access Management (IAM). Attach the IAM policy to the user. Assign the Lambda execution user to the Lambda function.
												- C) Create a Lambda execution role by using AWS Identity and Access Management (IAM). Attach the [AM policy to the role. Store the IAM role as an environment variable in the Lambda function.
												- D) Create a Lambda execution user by using AWS Identity and Access Management (IAM). Attach the IAM policy to the user. Store the IAM user credentials as environment variables in the Lambda function.
										- ![image.png](../assets/image_1727184358131_0.png)
											- Correct answer: **B**
									- ## ((66f4368d-de2d-49ed-ad39-0a6523615407))
										- By the end of this module, you will be able to:
											- Identify AWS Identity and Access Management (IAM) features and components.
											- Configure permissions to support a development environment.
											- Demonstrate how to test IAM permissions.
											- Configure your IDEs and SDKs to support a development environment.
											- Demonstrate accessing AWS services using SDKs and AWS Cloud9.
									- ## ((66f2ab5c-e0e3-45bf-8b9c-8957209af50c))
										- ((64b81154-09ce-46c2-993a-0451497bcf3c))
										- [IAM Policy Simulator](https://policysim.aws.amazon.com/home/index.jsp)
										- ((66f436c7-89a5-409a-8362-a51d4c503fe8))
										- ((66f436d4-3256-4da1-9e56-45f43e2eb980))
										- ((66f436dd-74a9-4c45-8017-1a828776a970))
										- ((66f2aba1-de82-4a80-abb8-503a006545ed))
										- ((66f2abb5-b766-409c-bae2-308458942579))
										- ((66f2abc2-0b89-4753-8a41-8184976f0a10))
											- These specify the maximum limit of permissions, not the minimum permissions you get. i.e. it limits
										- ((66f436f8-74c1-4340-a129-cb476365db83))
										- ((66f2ac3b-64b2-4c9c-bbdd-9649fb71d67a))
										- ((66f2ac55-9f69-49a4-a95a-c215c88013ba))
										- ### ((66f43727-9dfc-4bf8-83a7-ea01f4e12568))
										- ### ((66f43742-7bb8-4881-9a98-21051e522e52))
										- ((66f43751-7c3e-4d1a-8920-a8a16a03a984))
									- ## ((66f2ab2c-5c2f-40a1-92aa-c3789cb3aa8f))
										- ((66f43764-3aeb-4bd2-a4e5-6aeb17251c4e))
										- ((66f4376f-3142-4a76-ac8b-95635e6060d3))
										- ((66f2ac8b-e341-42f6-930e-e90ae064a978))
											- Involves edits to both ((66f29c25-c130-4074-9136-96f9307ec825)) and ((66f29c2a-fe97-4e7f-af89-020f29017644))
										- ((66f4377c-7980-4b06-a704-7294b78b212f))
										- ((66f4378b-e68c-46e4-b61d-7fae363843a7))
										- `~/.aws/config`
										  id:: 66f29c25-c130-4074-9136-96f9307ec825
										  collapsed:: true
											- ![image.png](../assets/image_1727175795794_0.png)
										- `~/.aws/credentials`
										  id:: 66f29c2a-fe97-4e7f-af89-020f29017644
										- Both
										  collapsed:: true
											- ![image.png](../assets/image_1727175743861_0.png)
										- ((66f2acd0-6717-4018-873b-be05612fab04))
										- ((66f2acdc-5820-4700-9cf3-d97784b74c7f))
											- Best practice is to sign request with SigV4. This is done automatically if you use the SDK
										- ((66f2ad11-8239-49b6-9dac-600419a455d7)) to create temporary credentials
										- ((66f2ad3a-b30d-42c9-a0eb-a7ec8052ba9c))
										- ((66f437a6-7ed4-4c2e-b3f6-17bc80d92c30))
									- ## ((66f2ad4c-3e82-4596-b475-4db38ce15032))
									  collapsed:: true
										- Permissions boundaries are used to set minimum permissions that an identity-based policy can grant to an IAM entity, such as users or roles.
										  logseq.order-list-type:: number
											- **False**
											  logseq.order-list-type:: number
												- Permissions boundaries are used to set maximum permissions that an identity-based policycan grant to an IAM entity, such as users or roles.
												  logseq.order-list-type:: number
										- IAM roles temporarily delegate access to users or services that normally do not have access to your AWS resources
										  logseq.order-list-type:: number
											- **True**
											  logseq.order-list-type:: number
										- Identity-based policies grant the specified principal permission to specific actions on a resource and define under what conditions this applies.
										  logseq.order-list-type:: number
											- **False**
											  logseq.order-list-type:: number
												- Resource-based policies grant the specified principal permission to perform specifig Actions on that resource and defines under what conditions this applies.
												  logseq.order-list-type:: number
										- The AWS CLI supports multiple named profiles to interact with your AWS resources
										  logseq.order-list-type:: number
											- **True**
											  logseq.order-list-type:: number
										- After temporary security credentials expire you do not have to rotate them or explicitly revoke them
										  logseq.order-list-type:: number
											- **True**
											  logseq.order-list-type:: number
										- The config and credentials files contain additional settings that can be stored in the environment variables of your operating system
										  logseq.order-list-type:: number
											- **True**
											  logseq.order-list-type:: number
									- ## ((66f2af82-8d66-4deb-8d8d-ee0d870efbdc))
									  collapsed:: true
									  Basically review ((64b81154-09ce-46c2-993a-0451497bcf3c)) policy and assign one
										- Meta
											- High-level instructions = TL;DR
											- Detailed instructions = step-by-step
										- Objectives
											- Connect to a development environment.
											- Verify IDE and the AWS CLI are installed and configured to use instance profile.
											- Verify the necessary permissions have been granted to run AWS CLI commands.
											- Assign an IAM policy to a role to delete an Amazon Simple Storage Service (Amazon S3) bucket.
										- ## Task 0: Connect to your development environment
										- ## Task 1: Review the development environment
											- ### Task 1.3) Deactivate the AWS managed temporary credentials setting in ((64b7f629-76b1-4695-9eec-3caea77b1452))
												- open the AWS Cloud9 Preferences > AWS SETTINGS > Untoggle AWS managed temporary credentials
												- Then `rm /home/ec2-user/.aws/credentials` in the terminal if necessary
											- `aws configure`
												- When prompted, verify the following:
												- **AWS Access Key ID** [leave blank]: *Press ENTER*
												- **AWS Secret Access Key** [leave blank]: *Press ENTER*
												- **Default region name** [update to proper region]: `us-east-1` for this example
												- **Default output format** [update to yaml]: `yaml`
											- `aws sts get-caller-identity` or `aws sts decode-authorization-message` to verify auth
										- ## Task 2: Review the AWS Toolkit options
											- AWS Toolkit should in the Explorer pane that it's connected to the specified AWS region
										- ## Task 3: Verify IAM Permissions
											- `aws s3 ls` = list all buckets
											- ```bash
											  # Delete a bucket with "deleteme" in the name
											  bucketToDelete=$(aws s3api list-buckets --output text --query 'Buckets[?contains(Name, `deletemebucket`) == `true`] | [0].Name')
											  ```
											- Delete bucket with specified name, either:
												- `aws s3 remove-bucket s3://$bucketToDelete`
												- `aws s3 rb s3://$bucketToDelete`
											- `aws s3 rb s3://$bucketToDelete --debug`
											  Delete a bucket using debug to see why it failed
												- The last step should say why the error occurred
										- ## Task 4: Add the missing permissions to your developer role
											- ### Task 4.1: Review a customer managed IAM policy
												- ```bash
												  policyArn=$(aws iam list-policies --output text --query 'Policies[?PolicyName == `S3-Delete-Bucket-Policy`].Arn')
												  ```
												  Assign the policy ARN value to the **$policyArn** variable (which will be used in the next command)
												- `aws iam get-policy-version --policy-arn $policyArn --version-id v1`
												  collapsed:: true
												  Review the policy document for the `S3-Delete-Bucket-Policy` policy. Note: This policy was created for you to grant delete bucket permissions for your role.
													- Example output
														- ```
														  PolicyVersion:
														    CreateDate: '2022-03-24T17:58:58+00:00'
														    Document:
														      Statement:
														      - Action:
														        - s3:DeleteBucket
														        Effect: Allow
														        Resource: arn:aws:s3:::6nzxc1sjkmar-lab1deletemebucket-t63kd50lk000
														      Version: '2012-10-17'
														    IsDefaultVersion: true
														    VersionId: v1
														  ```
											- ### Task 4.2: Attach the IAM policy to the notes-application-role
												- Either:
													- `aws iam attach-role-policy --policy-arn $policyArn --role-name notes-application-role`
													- `aws iam attach-role-policy --policy-arn $policyArn --user-name notes-application-role`
											- `aws iam list-attached-role-policies --role-name notes-application-role`
											  Review the policies attached to the role
											- ### Task 4.4: Run the bucket delete command and verify it has been deleted
												- `aws s3 rb s3://$bucketToDelete`
												  Delete the bucket with `deleteme`in the name
												- `aws s3 ls`
												  Verify the bucket has been removed
								- # ((66f2a934-776d-4993-a6cb-cdb1519090c4))
								  collapsed:: true
									- ## ((66f2bf56-c6b7-443f-a485-9f9072fd9169))
										- ((66f2bf71-4dd6-4cef-9f05-0ed11554287d))
											- Block storage
												- i.e. raw storage
												- e.g. hard disks, storage area network (SAN), storage arrays
												- AWS e.g.: ((6463499e-ba62-451c-b295-387f10fcd780)) : `General Purpose SSD`
											- File storage
												- i.e. file system manages unrelated data blocks
												- e.g. NAS, Windows file servers
												- AWS e.g.: ((63a06e59-4078-4357-b478-dda42326daf4)), Amazon FSx for Windows File Server, Amazon FSx for OpenZFS
											- Object storage
												- i.e. stores virtual containers that encapsulate the data and metadata
												- e.g. ((663a578c-4e87-4711-873e-a573b457046a)), OpenStack Swift
												- AWS e.g.: ((6463499e-42ab-4a58-8911-df6138dfee8f)) : `S3 Standard`
										- ((66f2c10a-5dfc-4d6b-999b-1cc8ecc6ff35))
											- Pros
												- Availability
													- Copied to 3 availability zones with standard plan
												- Durability
												- Security
												- Manageability
												- Performance
												- Scalability
													- 5TB max
										- ((66f2c1e9-a0eb-4d32-b79d-202e1e8b484a))
											- The namespace for S3 names is global, but the resource itself is regional
										- ((66f2c204-9ae9-46be-ab16-7f16caa5eef7))
											- i.e. directory names
										- ((66f2c2ee-3099-4c42-bbc6-e9da48d93a4f))
										- ((66f2c394-c239-4bbf-b5cb-7b496930a2d4))
											- i.e. backups for each changed version of a file
										- ((66f2c433-b037-449a-9e60-9aaea59e4073))
											- `DELETE` = Inserts a delete marker in the bucket, and sets it as the
											  current version of the object.
											- `DELETE Object versionID` — Deletes a specific object version permanently.
										- ((66f2c485-c038-49a0-a6c9-6318f48b7e91))
										- ((66f2c50e-3ce4-4597-904e-537ffabc8618))
											- IAM policies are attached to users
											- Objects ACLs are attached to objects
											- Bucket ACLs and bucket policies (one per bucket) are attached to buckets
										- ((66f2c56a-1f6a-4abf-b0ef-b3301d7b2287))
										- ((66f2c59f-95e9-4991-bdbc-f5ec362e544c))
											- Instead of bucket policies you can use access points as a further limitation to which objects that a user can access
											- Similar to accessing a subdomain of a site. You have similar permissions from the policy, just on less directories/objects
											- Workaround for one policy per bucket
											- e.g. different access points for support team, dev team, QA, etc
										- ((66f2c6b0-7f5b-4c8c-a474-97b35fa6f661))
									- ## ((66f2c6d0-8ef5-46c0-8f09-28f1aa9d845b))
										- ((66f2c6fa-5bfa-462a-a886-9eb9b9d68f71))
											- Low-level commands (s3api)
												- One-to-one mapping to Amazon S3 API
												- Fine level control
												- Examples: `copy-object`, `create-multipart-upload`
											- High-level commands (s3)
												- May result in multiple s3api invocations
												- Faster, but less control. Allows you to do operations in bulk
												- Examples: `cp`, `sync`
										- ((66f2c7ae-4915-4664-a32d-c84e4b321582))
											- `s3api` is an alias for `s3` on CLI, so it's fine to just stick with `s3`
									- ## ((66f2c7c2-02b3-45d3-8daa-db770354f24a))
										- ((66f2c7d6-0d51-41cd-bc6a-30aa16cba83a))
										- ((66f2c7e7-6651-4e87-93d7-dcae9508c7d4))
										- ((66f2c81f-a29d-43d0-ab1c-a66263db87a0))
										- ((66f2c82b-91f3-43cf-aac3-97490b1c91a9))
											- ((66f2c839-405e-4af7-a390-f3571d8ee313))
											- ((66f2c86c-8dea-4393-beb0-fe194ec2cb37))
											- ((66f2c87b-b7b8-45df-b1cc-340e23e14d96))
											- ((66f2c888-fbbf-4ab6-9623-2d2ff8a451a1))
										- ((66f2c899-13f3-476b-91ab-947264126217))
										- ((66f2c8d0-8559-44f9-bb55-3bc8fda156d4))
											- `close()`
									- ## ((66f2cd35-be99-4d70-9b53-9ca6aef62d79))
										- True
										  logseq.order-list-type:: number
										- False
										  logseq.order-list-type:: number
											- Although an S3 bucket is a global resource, it is created in a specific AWS Region.
											  logseq.order-list-type:: number
										- True
										  logseq.order-list-type:: number
										- False
										  logseq.order-list-type:: number
											- Enabling web hosting just enables or adds the additional web endpoint, it doesn't change any existing ones.
											  logseq.order-list-type:: number
										- True
										  logseq.order-list-type:: number
										- True
										  logseq.order-list-type:: number
									- ((66f2cdfc-fc5e-47ef-8f23-d523008daf1a))
										- You are now able to:
											- Describe the basic concepts of ((6463499e-42ab-4a58-8911-df6138dfee8f))
											- List the options for securing data using ((6463499e-42ab-4a58-8911-df6138dfee8f))
											- Define SDK dependencies for your code.
											- Explain how to connect to the Amazon S3 service.
											- Describe request and response objects
								- # ((66f2a94b-b110-4788-8061-3e79dd0f0aa4))
								  collapsed:: true
									- ((66f2ce4f-fc1a-4591-a426-18608e28b643))
										- Perform key bucket and object operations
										- Explain how to handle large files and a large number of files
										- Create and configure an ((6463499e-42ab-4a58-8911-df6138dfee8f)) bucket for hosting a static website
										- Explain how to grant temporary access to your objects
									- ## ((66f2ced3-f14d-4c4d-8963-b90292b516ec))
										- ((66f2cee9-87bf-4511-ab80-964bd90261b0))
											- Create, List, Delete
											- Configuration updates
												- e.g. Encryption, Lifecycle, CORS, Versioning, Website, Notification, Policies, Replication, Tagging, etc
										- ((66f2cf21-28ea-45a3-9331-5575ac5f5dac))
										- ((66f2cfad-74c7-4d1b-92be-b778ffba91e5))
											- This determines whether a bucket exists and you have permission to access it
											- ((66f2cfd2-9f44-48ad-a68f-c804d38da836))
											- ((66f2cfde-cca9-44b2-9eb2-61f86cfe38ac))
											- ((66f2cff0-a464-4791-8d1c-0b8ac81d222c))
										- ((66f2cffd-7c35-4879-963b-b268b2e77139))
										- ((66f2d00d-48ed-4c3f-acb1-f6bc23198386))
										- ((66f2d020-edaf-4711-bcc1-8b0ad206e3c1))
											- Can either enable or suspend (i.e. can't disable it, just prevent it from versioning in the future. This means old versions don't get deleted)
									- ## ((66f2d060-9ff0-4364-bf4e-f039db9183eb))
										- ((66f2d06d-5f02-4363-9516-513dd34f05f6))
											- Bulk operations include:
												- `copy`
												- `sync`
												- `batch`
											- Bulk operations are basically a script of low-level commands e.g. ((66f2d0c2-1347-4660-8afc-92181d10c58d))
										- ((66f2d0b6-16dc-41fa-bd12-3f89b193ba8f))
										- ((66f2d0c2-1347-4660-8afc-92181d10c58d))
										- ((66f2d0fb-69a3-4ca9-bfd1-fa802accd16d))
											- Get object and metadata
												- `GetObject`
											- Get object metadata
												- `HeadObject`
												- `GetObjectAcl`
												- `GetObjectTagging`
										- Example: Getting an object
											- ((66f2d138-ba95-4ed7-a644-30340d639bac))
											- ((66f2d14a-be57-47cd-b955-6478527a2ae9))
											- ((66f2d153-9b3f-438f-8eb2-f347033943d7))
										- ((66f2d15f-aabc-4c67-8df5-1a8b0c49038f))
										- ((66f2d195-6fc8-4242-a3de-5420d730598a))
											- Retrieve only a subset of data from an object using simple SQL expressions
										- ((66f2d1c4-b424-4484-a2b6-ad77491ce942))
									- ## ((66f2d214-041c-4cd5-b8c1-e264a7fa3c30))
										- ((66f2d228-6474-4e59-aa3d-0416cb58d33b))
										- ((66f2d26e-0e61-4b16-b4f2-7d9e1419e139))
									- ## ((66f2d2a5-cdd7-41bd-9c83-81e3be1768b0))
										- ((66f2d2b4-2a1c-48da-b770-89dd1d61286e))
										- ((66f2d2bf-4fd7-462a-a196-b69dd21636ef))
										- ((66f2d307-b791-4cc4-a751-5f3505281503))
										- ((66f2d31c-ca66-4b28-8062-c716ee0a9333))
										- ((66f2d35a-d28c-4d2c-8537-275c48dca91c))
									- ## ((66f2d366-b91c-4493-8c52-a89061c2a0c8))
										- ((66f2d37c-7ca3-49fc-9ff9-57b1e46dee56))
										- ((66f2d38d-7f01-4a8c-898f-418f07cbe276))
										- ((66f2d39d-6070-4677-8b8d-dbe3a35fda02))
									- ## ((66f2d3ab-b8b3-469e-ab09-bf034cce3111))
									  collapsed:: true
										- Consider using multipart upload for objects larger than 100 MB in size.
										  logseq.order-list-type:: number
											- **True**
											  logseq.order-list-type:: number
												- It is a best practice to consider using multipart upload for objects larger than 100 MB. This is true even though the largest object that can be uploaded method is 5 GB.
												  logseq.order-list-type:: number
										- Some services have APIs that require pagination to access all the data returned from the service.
										  logseq.order-list-type:: number
											- **True**
											  logseq.order-list-type:: number
												- You reviewed an example of paginated results when listing the content of a bucket.
												  logseq.order-list-type:: number
										- With presigned URLs, you can share specific 53 objects with time-limited access.
										  logseq.order-list-type:: number
											- **True**
											  logseq.order-list-type:: number
												- Using presigned URL, you can grant users temporary access to specific $3 objects.
												  logseq.order-list-type:: number
										- Use S3 Select with SQL-like querying to select and download objects that match specific criteria.
										  logseq.order-list-type:: number
											- **False**
											  logseq.order-list-type:: number
												- With S3 Select, you can use SQL-like syntax to retrieve only a subset of data from an object. To get a subset of objects that match criteria, such as file types or prefixes, use the Amazon S3 GET command.
												  logseq.order-list-type:: number
										- Use S3 Select with SQL-like querying to select and download objects that match specific criteria.
										  logseq.order-list-type:: number
											- **False**
											  logseq.order-list-type:: number
												- You can configure a bucket to send zon S3 event notifications in response to actions in Amazon$3, such as PUT, POST, COPY, or DELETE.6.
												  logseq.order-list-type:: number
										- A web server uses CORS to allow or deny the loading of resources stored within the same domain that the website is accessed from.
										  logseq.order-list-type:: number
											- **False**
											  logseq.order-list-type:: number
												- Cross-Origin Resource Sharing (CORS) protects your data from being accessed from other domains. In CORS, the origin is a web server, and a resource is an asset at a different domain. With CORS a web server indicates the origins (domain, scheme, or port) other than its own from which a browser should permit loading of resources.
												  logseq.order-list-type:: number
									- ## ((66f2d74f-41d3-4d08-a8f3-d534ac9be4f5))
									  collapsed:: true
										- ### Objectives
											- Interact with Amazon S3 programmatically using AWS SDKs and the AWS CLI.
											- Create a bucket using waiters and verify service exceptions codes.
											- Build requests needed to upload an Amazon S3 object with metadata attached.
											- Build requests to download an object from the bucket, process data, and upload the object back to bucket.
											- Configure a bucket to host the website and sync the source files using the AWS CLI.
										- ## Task 1: Create a new Amazon S3 bucket
										  collapsed:: true
											- **High level instructions**
												- In the **labRepo/config.ini** file, replace the bucket_name value *NOTES_BUCKET_NAME* with the **NotesBucketName** value shown to the left of these instructions.
												- Finish **labRepo/create-bucket.py** to create an Amazon S3 bucket.
												- Complete the **TODO 1** section to create an Amazon S3 service client.
												- Complete the **TODO 2** section to verify if the generated bucket name is valid to use.
												- Complete **TODO 3** to add the new bucket to Amazon S3 in your lab account.
												- Complete **TODO 4** to use a waiter to confirm that the bucket has been created.
												- Run the script and resolve any errors.
											- ### Task 1.1: Configure your environment and develop code to create an Amazon S3 service client
												- ```python
												  ## TODO 1: Create an S3 client to interact with the service and pass 
												  ## it to the main function that will create the buckets
												  client = boto3.client('s3')
												  ```
											- ### Task 1.2: Develop code to verify that your proposed bucket name is valid
												- ```python
												  def verifyBucketName(s3Client, bucket):
												      try:
												          ## Start TODO 2: enter a command that will check if a bucket already exists in AWS
												          ## with the name built from your ini file input.
												          s3Client.head_bucket(Bucket=bucket)
												          ## End TODO 2
												  
												          # If the previous command is successful, the bucket is already in your account.
												          raise SystemExit('This bucket has already been created in your account, exiting because there is nothing further to do!')
												      except botocore.exceptions.ClientError as e:
												          error_code = int(e.response['Error']['Code'])
												          if error_code == 404:
												            ## If you receive a 404 error code, a bucket with that name
												            ##  does not exist anywhere in AWS.
												            print('Existing Bucket Not Found, please proceed')
												          if error_code == 403:
												            ## If you receive a 403 error code, a bucket exists with that
												            ## in another AWS account.
												            raise SystemExit('This bucket has already owned by another AWS Account, change the suffix and try a new name!')
												  ```
													- Choice B is incorrect because `list_buckets` does not allow you to pass a Bucket property to limit it to one bucket. Additionally, the `list_bucket` method will only list buckets in your AWS account.
											- ### Task 1.3: Develop code to create the bucket in your lab region
												- ```python
												  def createBucket(s3Client, name):
												      session = boto3.session.Session()
												  
												      # Obtain the region from the boto3 session
												      current_region = session.region_name
												      print('\nCreating ' + name + ' in ' + current_region)
												  
												      # Start TODO 3: Create a new bucket in the users current region 
												      if current_region == 'us-east-1':
												          response = s3Client.create_bucket(Bucket=name)
												      else:
												          response = s3Client.create_bucket(
												            Bucket=name,
												            CreateBucketConfiguration={
												              'LocationConstraint': current_region
												            })
												      # End TODO 3:
												  
												      print('Success!')
												  ```
													- Choice B uses the incorrect syntax to create a bucket with the Amazon S3 client. If this code was using an Amazon S3 bucket resource, you could use the *bucket.create()* method. The bucket name would have to be specified before calling *create()* though, not passed with the call.
											- ### Task 1.4: Develop code to verify the bucket is in your account, and run your script
												- ```python
												  def verifyBucket(s3Client, bucket):
												      ## Start TODO 4: Complete the function so that it will 
												      ## pause and only proceed after the bucket exists.
												      waiter = s3Client.get_waiter('bucket_exists')
												      waiter.wait(Bucket=bucket)
												      ## End TODO 4
												      print('The bucket:' + bucket + ' is now available.')
												  ```
													- You have to create the waiter and then use it to poll Amazon S3 until the bucket is found.
											- ### `create-bucket.py` full code
											  collapsed:: true
												- ```python
												  import boto3, botocore, configparser
												  
												  def main(s3Client):
												      print('\nStart of create bucket script\n')
												  
												      print('Reading configuration file for bucket name...')
												      config = readConfig()
												      bucket_name = config['bucket_name']
												  
												      print('Verifying that the bucket name is valid...')
												      #### Verify that the bucket exists. The script with exit 
												      #### if the name is not valid for a new bucket.
												      verifyBucketName(s3Client, bucket_name)
												      print(bucket_name)
												  
												      #### Create the notes-bucket-
												      createBucket(s3Client, bucket_name)
												  
												      ##Pause until the the bucket is in the account
												      print('\nConfirm that the bucket exists...')
												      verifyBucket(s3Client, bucket_name)
												  
												      print('\nEnd of create bucket script\n')
												  
												  def verifyBucketName(s3Client, bucket):
												      try:
												          ## Start TODO 2: enter a command that will check if a bucket already exists in AWS
												          ## with the name built from your ini file input.
												          s3Client.head_bucket(Bucket=bucket)
												          ## End TODO 2
												  
												          # If the previous command is successful, the bucket is already in your account.
												          raise SystemExit('This bucket has already been created in your account, exiting because there is nothing further to do!')
												      except botocore.exceptions.ClientError as e:
												          error_code = int(e.response['Error']['Code'])
												          if error_code == 404:
												            ## If you receive a 404 error code, a bucket with that name
												            ##  does not exist anywhere in AWS.
												            print('Existing Bucket Not Found, please proceed')
												          if error_code == 403:
												            ## If you receive a 403 error code, a bucket exists with that
												            ## in another AWS account.
												            raise SystemExit('This bucket has already owned by another AWS Account, change the suffix and try a new name!')
												  
												  def createBucket(s3Client, name):
												      session = boto3.session.Session()
												  
												      # Obtain the region from the boto3 session
												      current_region = session.region_name
												      print('\nCreating ' + name + ' in ' + current_region)
												  
												      # Start TODO 3: Create a new bucket in the users current region 
												      
												      if current_region == 'us-east-1':
												          response = s3Client.create_bucket(Bucket=name)
												      else:
												          response = s3Client.create_bucket(
												            Bucket=name,
												            CreateBucketConfiguration={
												              'LocationConstraint': current_region
												            })
												      # End TODO 3:
												  
												      print('Success!')
												  
												  def verifyBucket(s3Client, bucket):
												      ## Start TODO 4: Complete the function so that it will 
												      ## pause and only proceed after the bucket exists.
												      waiter = s3Client.get_waiter('bucket_exists')
												      waiter.wait(Bucket=bucket)
												      ## End TODO 4
												      print('The bucket:' + bucket + ' is now available.')
												  
												  ## Utility methods
												  def readConfig():
												      config = configparser.ConfigParser()
												      config.read('./labRepo/config.ini')
												      
												      return config['S3']
												  
												  ## TODO 1: Create an S3 client to interact with the service and pass 
												  ## it to the main function that will create the buckets
												  client = boto3.client('s3')
												  
												  
												  ## End TODO 1
												  
												  try:
												      main(client)
												  except botocore.exceptions.ClientError as err:
												      print(err.response['Error']['Message'])
												  except botocore.exceptions.ParamValidationError as error:
												      print(error)
												  ```
										- ## Task 2: Upload an object to Amazon S3
										  collapsed:: true
											- **High-Level Instructions**
												- Finish **labRepo\create-object.py** to add the **notes.csv** to your bucket.
												- Complete **TODO 5** to create a notes.csv object.
												- Run the script and confirm that there are no errors returned.
											- ### Task 2.1: Develop code to create an object in an Amazon S3 bucket
												- ```python
												  def uploadObject(s3Client, bucket, name, key, contentType, metadata={}):
												  
												      ## Start TODO 5: create a object by transferring the file to the S3 bucket, 
												      ## set the contentType of the file and add any metadata passed to this function.
												      response = s3Client.upload_file(
												          Bucket=bucket, 
												          Key=key,
												          Filename=name,
												          ExtraArgs={
												              'ContentType': contentType,
												              'Metadata': metadata
												              }
												      )
												      ## End TODO 5
												      return "Finished creating object\n"
												  ```
													- Choice B is incorrect because the parameters passed to put_object would not be correct. Put_object requires the contents of the object passed in a data property, not the filename, to be transferred.
												- `python labRepo/create-object.py`
											- ### `create-object.py` full code
											  collapsed:: true
												- ```python
												  import boto3, botocore, configparser
												  
												  def main(s3Client):
												      print('\nStart of create object script\n')
												      ## Initialize variables for object creation
												  
												      print('Reading configuration file for bucket name...')
												      config = readConfig()
												      bucket_name = config['bucket_name']
												      source_file_name = config["object_name"] + config['source_file_extension']
												      key_name = config['key_name']+ config['source_file_extension']
												      contentType = config['source_content_type']
												      metaData_key = config['metaData_key']
												      metaData_value = config['metaData_value']
												  
												      #### Create object in the s3 bucket
												      print('Creating Object...')
												      print(uploadObject(s3Client, bucket_name, source_file_name, key_name, contentType, {metaData_key: metaData_value}))
												      
												      print('\nEnd of create object script\n')
												  
												  def uploadObject(s3Client, bucket, name, key, contentType, metadata={}):
												  
												      ## Start TODO 5: create a object by transferring the file to the S3 bucket, 
												      ## set the contentType of the file and add any metadata passed to this function.
												      response = s3Client.upload_file(
												          Bucket=bucket, 
												          Key=key,
												          Filename=name,
												          ExtraArgs={
												              'ContentType': contentType,
												              'Metadata': metadata
												              }
												      )
												      ## End TODO 5
												      return "Finished creating object\n"
												      
												  def readConfig():
												      config = configparser.ConfigParser()
												      config.read('./labRepo/config.ini')
												      
												      return config['S3']
												  
												  # Create an S3 client to interact with the service and pass 
												  # it to the main function that will create the buckets
												  client = boto3.client('s3')
												  try:
												      main(client)
												  except botocore.exceptions.ClientError as err:
												      print(err.response['Error']['Message'])
												  except botocore.exceptions.ParamValidationError as error:
												      print(error)
												  ```
										- ## Task 3: Process the data from an object stored in Amazon S3
										  collapsed:: true
											- **High-Level Instructions**
												- Finish **labRepo\convert-csv-to-json.py** to process data in notes.csv.
												- Complete **TODO 6** to download the contents of the csv file to memory.
												- Complete **TODO 7** to upload the converted data to a new object.
												- Run the script to convert the data and confirm that there are no errors.
												- Download the JSON file to confirm the contents.
											- ### Task 3.1: Develop code to retrieve the object data from Amazon S3
												- ```python
												  def getCSVFile(s3Client, bucket, key):
												      bytes_buffer = io.BytesIO()
												      
												      ## Start TODO 6: Download the file contents to the 
												      ## bytes_buffer object so that it can be decoded to a string.
												      s3Client.download_fileobj(
												          Bucket=bucket, 
												          Key=key, 
												          Fileobj=bytes_buffer)
												      ## End TODO 6
												  
												      byte_value = bytes_buffer.getvalue()
												      return byte_value.decode('utf-8')
												  ```
											- ### Task 3.2: Develop code to create a new object with the processed data
												- ```python
												  def createObject(s3Client, bucket, key, data, contentType, metadata={}):
												      ## Start TODO 7: Create an S3 object with the converted data
												      s3Client.put_object(
												          Bucket=bucket, 
												          Key=key,
												          Body=data,
												          ContentType=contentType,
												          Metadata=metadata
												      )
												      ## End TODO 7
												      return 'Successfully Created Object\n'
												  ```
													- Choice A is incorrect because upload_file is used to upload a file from the local disk. For this solution there is no need to write the converted data to a disk when it can be uploaded directly.
											- ### Task 3.3: Run the script to create a new object in JSON format
												- `python labRepo/convert-csv-to-json.py`
											- ### `convert-csv-to-json.py` full code
											  collapsed:: true
												- ```python
												  import boto3, botocore, json, csv, io, configparser
												  
												  def main(s3Client):
												      print('\nStart of convert object script\n')
												  
												      ## Initialize variables for object creation
												      print('Reading configuration file for bucket name...')
												      config = readConfig()
												      bucket_name = config['bucket_name']
												      source_file_name = config['object_name'] + config['source_file_extension']
												      key_name = config['key_name']+ config['source_file_extension']
												      processed_file_name = config['key_name'] + config['processed_file_extension']
												      contentType = config['processed_content_type']
												      metaData_key = config['metaData_key']
												      metaData_value = config['metaData_value']
												  
												      #### Get the object from S3
												      print('\nGetting the CSV object from S3 bucket')
												      csvStr = getCSVFile(s3Client, bucket_name, key_name)
												      
												      ## Convert the object to the new format
												      print('\nConverting CSV string to JSON...')
												      jsonStr = convertToJSON(csvStr)
												      
												      ## Uploaded the converted object to S3
												      print('Creating the new JSON object on S3')
												      print(createObject(s3Client, bucket_name, processed_file_name, jsonStr, contentType, {metaData_key: metaData_value}))
												  
												      print('\nEnd of convert object script\n')
												  
												  def getCSVFile(s3Client, bucket, key):
												      bytes_buffer = io.BytesIO()
												      
												      ## Start TODO 6: Download the file contents to the 
												      ## bytes_buffer object so that it can be decoded to a string.
												      s3Client.download_fileobj(
												          Bucket=bucket, 
												          Key=key, 
												          Fileobj=bytes_buffer)
												      ## End TODO 6
												  
												      byte_value = bytes_buffer.getvalue()
												      return byte_value.decode('utf-8')
												  
												  def createObject(s3Client, bucket, key, data, contentType, metadata={}):
												      ## Start TODO 7: Create an S3 object with the converted data
												      s3Client.put_object(
												          Bucket=bucket, 
												          Key=key,
												          Body=data,
												          ContentType=contentType,
												          Metadata=metadata
												      )
												      ## End TODO 7
												      
												      return 'Successfully Created Object\n'
												  
												  def convertToJSON(input):
												      jsonList = []
												      keys = []
												      
												      csvReader = csv.reader(input.split('\n'), delimiter=",")
												  
												      for i, row in enumerate(csvReader):
												          if i == 0:
												              keys = row
												          else:
												              obj = {}
												              for x, val in enumerate(keys):
												                  obj[val] = row[x]
												              jsonList.append(obj)
												      return json.dumps(jsonList, indent=4)
												  
												  def readConfig():
												      config = configparser.ConfigParser()
												      config.read('./labRepo/config.ini')
												      
												      return config['S3']
												  
												  # Create an S3 client to interact with the service and pass 
												  # it to the main function that will create the buckets
												  client = boto3.client('s3')
												  try:
												      main(client)
												  except botocore.exceptions.ClientError as err:
												      print(err.response['Error']['Message'])
												  except botocore.exceptions.ParamValidationError as error:
												      print(error)
												  ```
										- ## Task 4: Configure static website hosting on an Amazon S3 bucket with the AWS CLI
											- **High-Level Instructions**
												- Upload the files in the **labRepo/html** folder to your Amazon S3 bucket.
												- Enable Amazon S3 website hosting on your bucket using the index.html and error.html you uploaded.
												- Apply the bucket policy provided in the **labRepo/policy.json** file to your bucket.
												- View the website in your web browser to confirm that it displays as expected.
										- ## Optional Challenge: Configure static website hosting on an Amazon S3 bucket using Python
							- # Day 2
							  collapsed:: true
								- ## Agenda
								  collapsed:: true
									- ![image.png](../assets/image_1727165404592_0.png)
									- ((66434390-e70f-4dda-8141-2cbfe223db56))
									- ![image.png](../assets/image_1727165427422_0.png)
								- # ((66f3c49b-53e0-4b84-b1ed-f6daed53e4a6))
								  collapsed:: true
									- ## ((66f3c4df-b7c5-4030-9258-7d4fb2e29d6b))
										- By the end of this module, you will be able to:
										- Describe the key components of DynamoDB
										- Explore multiple ways to connect to DynamoDB
										- Define SDK dependencies and settings for your code
										- Work with request and response objects
									- ## ((66f3c5af-0c35-48f0-ad16-8cab51c7aef7))
										- ((66f3c5cc-d187-4251-a2a3-f00da239b4a5))
											- Relational i.e. ((6463499e-a669-4769-9e57-f3cb57e2c4f3)), ((64b7f40b-fa53-4f71-969f-3cfe64407747)). SQL-based, as opposed to NoSQL
												- For traditional applications, ERP, CRM, ecommerce
											- Key-value i.e. ((6463499e-971f-49ad-9136-306a4377fe86))
												- For high-traffic web applications, ecommerce systems, gaming applications
											- Graph i.e. ((663a5791-97bd-4716-98ae-69c5d9bd1a6e))
												- For data analytics, fraud detection, social networking, recommendation engines
											- In-memory caching i.e. ((6463499e-529d-478c-822f-2ff43f26b6bf))
												- For caching, session management, gaming leaderboards
										- ((66f3c773-a685-4402-9f9f-85955c72bf84))
											- ((66f3c792-a372-4cfc-8d7e-ebe8aa16a5cf))
										- ((66f3c7ee-bcf3-4af9-b4fe-92206672f654))
											- Rows and columns vs JSON documents
										- ((66f3c837-9225-415a-bb55-fe8544e6e415))
											- It's main benefits for us is that in this demo app is that it's serverless so it's cheaper and fully-managed
									- ## ((66f3cbb3-d900-4931-82a8-7a75236553b6))
										- ((66f3cbbf-9e69-4422-9337-dc20b24c8c2c))
										- ((66f3cbcb-823c-4518-8d05-a617996716ca))
										- ((66f3cbd7-1c61-4c13-a211-4ed8620408b6))
										- ((66f3cbe1-9ae8-4138-80f8-c3efc78cad0f))
										- ((66f3cbeb-857e-410d-bd28-0f81e3774d4f))
											- You can query data based on non-primary key attributes
										- ((66f3cc13-3e71-46ee-b05b-6058116f6e23))
											- Local because the index is located on the same table partition as the items that have a given partition key value
											- You can have 5 max
										- ((66f3ccd7-3bce-4bad-88a4-fa1108774ef7))
											- Global because queries on this index can span all data in a table across all partitions
										- ((66f3cce3-dcd0-434b-a2a1-919532ee9404))
											- Can shift up and down based on usage
									- ## ((66f3cf0f-0bb2-4a2f-a84c-138b01a9d82a))
										- ((66f3cf29-e8b6-4049-ba71-1761e3766d25))
											- ((64b806d2-fdd2-4f63-84b8-4f0b76f20027))
											- NoSQL Workbench
											  id:: 66f3cf37-859b-4003-900c-cc5f179578c3
											- DynamoDB Local
											- PartiQL
											- ((6544c9ef-05f1-41f8-8062-a6f5dc3cc6ad))
											- SDKs
												- Low-level interface
												- Document interface
												- High-level interface
										- ((66f3cf76-86db-445d-adb4-89c05f7ce990))
										  id:: 66f3cf6a-f0cf-4c5e-b2d2-52a9681b075e
											- Cross-platform client-side GUI application
											- Supported databases:
												- ((6463499e-971f-49ad-9136-306a4377fe86))
												- ((663a5791-9f7e-43cd-b84a-6c225d586d86))
										- ((66f3cfb1-7c04-420b-baab-6022b904b293))
										- ((66f3d001-cae8-47dc-885d-7fab28deb5c6))
										- ((66f3d010-645e-4002-9632-b904dda6a8e2))
									- ## ((66f3d024-1366-4c71-96ca-a5b468fb543f))
										- ((66f3d030-7875-4ca9-9628-2bb641d27603))
											- ((66f3d04c-fda1-4a94-b5c5-6a48c92e5800))
											- Object persistence interface and document interface works with complex data types
										- ((66f3d09b-d3a1-48ce-9fb6-a2558c8b0c68))
									- ## ((66f3d0cf-f579-45ab-8488-0051ad80ef24))
										- ((66f3d0dd-939a-4f17-a1d6-bf2b702283b2))
											- Lists of each for each language
									- ## ((66f3d0f1-3f67-469f-a0e3-adf6257f2ac5))
										- ((66f3d102-168a-4fcd-a42a-65c10a819a94))
										- ((66f3d10d-8b15-4c1d-b23f-827cba42087a))
									- ## ((66f3d117-07bb-4e3c-bef7-df8c8a8afbf1))
										- ((66f3d14c-7d5e-4167-9256-a8e961aec0d6))
										- ((66f3d18a-9d46-49c1-b790-ce443da622e1))
										- ((66f3d192-b471-4b45-a9f7-23ac18560bcd))
										- ((66f3d19b-f1e5-486e-9e6a-b6e91393dfcf))
									- On-demand grows in response to usage, it's a common serverless mode. Alternatively can use provisioned with autoscaling
									- ## ((66f3d1ad-ebcc-4503-867a-4b37105a45f9))
										- False
										  logseq.order-list-type:: number
										- False
										  logseq.order-list-type:: number
											- DynamoDB stores data **in partitions** and divides a table's items into multiple partitions based on the partition key value.
											  logseq.order-list-type:: number
										- True
										  logseq.order-list-type:: number
										- True
										  logseq.order-list-type:: number
										- False
										  logseq.order-list-type:: number
											- With the ((66f3cf6a-f0cf-4c5e-b2d2-52a9681b075e)), you can develop and test applications without accessing the DynamoDB web service
											  logseq.order-list-type:: number
										- True
										  logseq.order-list-type:: number
									- ## ((66f3d322-6aa1-4693-8708-da43524a5116))
										- You are now able to:
											- Describe the key components of DynamoDB
											- Define SDK dependencies for your code
											- Explain how to connect to DynamoDB
											- Describe how to perform key table operations
											- Describe how to build a request object
											- Explain how to read a response object
											- List the most common troubleshooting exceptions
								- # ((66f3d352-5b1a-4bc9-8594-e34f23f33126))
								  collapsed:: true
									- ## ((66f3d865-6d60-40a5-bcca-9d4d3ec01e6c))
										- By the end of this module, you will learn how to:
											- Develop programs to interact with Amazon DynamoDB using AWS SDKs
											- Perform CRUD operations to access tables, indexes, and data
											- Describe developer best practices when accessing DynamoDB
											- Review caching options for DynamoDB to improve performance
									- ((66f3d892-b0b1-47f9-8df2-970135f24505))
									- ((66f3d8a6-bf03-4b6b-8755-61b3d5bdacb4))
									- ## ((66f3d8af-c5a8-4625-bee6-85aca6aaba12))
										- ((66f3d8bc-34fe-46d4-a66a-b9f030077d58))
										- ((66f3dab5-5c99-44fd-b689-b34381e943f1))
										- ((66f3daee-37a9-45e3-9589-2217ef91c35b))
										- ((66f3dafa-643a-4f3d-9eba-4ca7c79bb444))
										- ((66f3db04-257d-460f-acc6-7911495d8bae))
									- ## ((66f3db0c-e587-4e8b-964c-ff5538212065))
										- ((66f3db18-d88e-4865-8e6d-d88f95c6adcc))
										- ((66f3db20-42bb-42d3-9ccd-1f978c5a86fa))
										- ((66f3db2c-becc-4c20-9888-6f73707e6574))
										- ((66f3db45-b106-424d-be89-488e78653d16))
										- ((66f3db50-2bae-4512-bf2a-278d7094e07d))
										- ((66f3db69-6a9f-4c58-88ca-527e5c6c0102))
										- ((66f3db72-a485-46a8-a1cd-0ca41c425006))
										- ((66f3db7e-a38c-4096-9019-a6bc9ebb109c))
										- ((66f3db88-bd43-444a-97be-2e9a2e1a3d08))
										- ((66f3db90-f8a8-4b70-8caa-9084dc982b2e))
									- ## ((66f3db98-3462-41d4-a384-24eae501bceb))
										- ((66f3dba4-4e07-4df4-aed2-c3159e07fe7f))
											- `s` being string, `n` being number. also `b` would allow for booleans, etc
										- ((66f3dbaf-4438-4d6d-81a2-5808ea2eeed2))
										- ((66f3dbc0-8fff-4332-afef-2307a0d5ed60))
									- ## ((66f3dbcd-86f0-45fd-abb7-66d710c40293))
										- ((66f3dbee-883e-4f83-a081-9721d6eabf5b))
										- ((66f3dc15-2b4a-4e4b-ae23-ba44b124bbf5))
											- Unsure if it supports `OR`
										- ((66f3dc20-89dd-47f9-a909-71c036d78882))
											- Returns 1MB or less usually. Results are divided into pages
											- Use the value of `LastEvaluatedKey` as `ExclusiveStartKey` in the new query as a parameter
										- ((66f3dcb6-6468-4474-a80a-0f56bfc6c291))
										- ((66f3df1b-eba1-4d58-86d2-1966af4d87d0))
										- ((66f3df27-06db-452c-a522-c55277df0edf))
									- ## ((66f3df31-ddad-4162-82a9-209424859926))
										- ((66f3df3c-bbd0-4c20-819f-0009359ed3d7))
										- ((66f3df46-3124-4752-94cd-757acfdcd025))
									- ## ((66f3df4e-edc9-4c56-aa9b-c07145e52652))
										- ((66f3df59-bc1c-4ca7-a7f4-7f0113285175))
									- ## ((66f3df60-e634-43fd-8fff-c874a1dbd027))
										- ((66f3df77-cf26-45c7-8763-29f73ee35568))
										- ((66f3df83-b2f9-4ffb-97a2-3881a05883b2))
										- ((66f3df96-f2fa-4d4c-93e8-643859de8164))
									- ## ((66f3dfa2-d273-469d-8e89-00139329da1b))
										- ((66f3dfb3-a608-488d-975b-9e4e0618e945))
										- ((66f3dfbf-a9c7-4377-bd9a-6973c2cd6813))
									- ## ((66f3dfcd-72f4-43a3-b8a5-2a6036fd8d57))
										- Key design concepts for NoSQL DBs include size, shape, and velocity.
										  logseq.order-list-type:: number
											- **True**
											  logseq.order-list-type:: number
										- Design partition keys around common access patterns and their level of uniqueness among
										  logseq.order-list-type:: number
										  items in the table.
											- **True**
											  logseq.order-list-type:: number
										- Developers should sethetable's capacity mode to provisioned if they expect traffic
										  logseq.order-list-type:: number
										  to be inconsistent.
											- **False**
											  logseq.order-list-type:: number
												- On-demand mode is best suited for inconsistent traffic
												  logseq.order-list-type:: number
										- By default, the DynamoDB write operations (PutItem, UpdateItem, DeleteItem) are conditional.
										  logseq.order-list-type:: number
											- **False**
											  logseq.order-list-type:: number
												- By default, the DynamoDB write operations (Putitem, Updateltem, Deleteltem) are unconditional.
												  logseq.order-list-type:: number
										- BatchwritelItem cannot
										  logseq.order-list-type:: number
										  update items. To update items,
										  use the UpdatelItem action.
											- **True**
											  logseq.order-list-type:: number
										- By design, table scans are more efficient than a query.
										  logseq.order-list-type:: number
											- **False**
											  logseq.order-list-type:: number
												- Table scans are less efficient than queries and should be used sparingly (because they go through every item).
												  logseq.order-list-type:: number
								- # ((66f3e14d-98d3-4d22-a29c-2bfdc942b98c))
								  collapsed:: true
									- ## Objectives
										- After completing this lab, you will be able to:
										- Interact with DynamoDB programmatically using low-level, document, and high-level APIs in your programs.
										- Create a table using waiters with a partition key, sort key, and desired provisioned throughput.
										- Load a table by reading JSON objects from a file.
										- Retrieve items from a table using key attributes, filters, expressions, and paginations.
										- Update items by adding new attributes and changing data conditionally.
										- Access DynamoDB data using PartiQL.
									- ## Task 1: Create an Amazon DynamoDB table
										- **High-Level Instructions**
											- Finish **labRepo/createTable.py** to create a new Amazon DynamoDB table.
											- Complete the **TODO 1** section to create an Amazon DynamoDB service client
											- Complete **TODO 2** to create the DynamoDB table.
											- Complete **TODO 3** so that your script will wait until the table exists before continuing.
											- Run the script and resolve any errors.
										- ### Task 1.1: Configure your AWS Cloud9 environment and inspect the configuration settings for this lab
										- ### Task 1.2: Create an Amazon DynamoDB service client
											- `client = boto3.client('dynamodb')`
										- ### Task 1.3: Develop code to create the table
										  collapsed:: true
											- ```python
											  def createTable(ddbClient, tableDefinition):
											      ## TODO 2: Add logic to create a table with UserId as the 
											      ## partition key and NoteId as the sort key
											      response = ddbClient.create_table(
											          AttributeDefinitions=[
											              {
											                  'AttributeName': tableDefinition["partitionKey"],
											                  'AttributeType': 'S',
											              },
											              {
											                  'AttributeName': tableDefinition["sortKey"],
											                  'AttributeType': 'N',
											              },
											          ],
											          KeySchema=[
											              {
											                  'AttributeName': tableDefinition["partitionKey"],
											                  'KeyType': 'HASH',
											              },
											              {
											                  'AttributeName': tableDefinition["sortKey"],
											                  'KeyType': 'RANGE',
											              },
											          ],
											          ProvisionedThroughput={
											              'ReadCapacityUnits': int(tableDefinition["readCapacity"]),
											              'WriteCapacityUnits': int(tableDefinition["writeCapacity"]),
											          },
											          TableName=tableDefinition["tableName"]
											      )
											      ## End TODO 2
											      return response
											  ```
										- ### Task 1.4: Develop code to only continue after the table is ready and run your code
										  collapsed:: true
											- ```python
											  def waitForTableCreation(ddbClient, tableName):
											      ## TODO 3: Add a waiter to pause the script until your new table exists
											      waiter = ddbClient.get_waiter('table_exists')
											      waiter.wait(TableName=tableName)
											      ## End TODO 3
											  ```
										- ### `createTable.py` full code
										  collapsed:: true
											- ```python
											  import boto3, botocore, configparser
											  
											  
											  def main(ddbClient):
											      
											      config = readConfig()
											      tableDefinition = {
											          'tableName': config["tableName"],
											          'partitionKey': config["partitionKey"],
											          'sortKey': config["sortKey"],
											          'readCapacity': config["readCapacity"],
											          'writeCapacity': config["writeCapacity"]
											          }
											          
											      print('\nCreating an Amazon DynamoDB table \"' + config["tableName"] + '\" \nwith a partition key: \"' +
											          config["partitionKey"] + '\" \nand sort key: \"' + config["sortKey"] + '\".\n\n')
											      creationResponse = createTable(ddbClient, tableDefinition)
											      print('Table Status: ' + creationResponse['TableDescription']['TableStatus'])
											  
											      print('\nWaiting for the table to be available...\n')
											      waitForTableCreation(ddbClient, config["tableName"])
											  
											      print('\nTable is now available.\n\n')
											      tableOutput = getTableInfo(ddbClient, config["tableName"])
											      print('Table Status: ' + tableOutput['Table']['TableStatus'])
											  
											  
											  def createTable(ddbClient, tableDefinition):
											      ## TODO 2: Add logic to create a table with UserId as the 
											      ## partition key and NoteId as the sort key
											      response = ddbClient.create_table(
											          AttributeDefinitions=[
											              {
											                  'AttributeName': tableDefinition["partitionKey"],
											                  'AttributeType': 'S',
											              },
											              {
											                  'AttributeName': tableDefinition["sortKey"],
											                  'AttributeType': 'N',
											              },
											          ],
											          KeySchema=[
											              {
											                  'AttributeName': tableDefinition["partitionKey"],
											                  'KeyType': 'HASH',
											              },
											              {
											                  'AttributeName': tableDefinition["sortKey"],
											                  'KeyType': 'RANGE',
											              },
											          ],
											          ProvisionedThroughput={
											              'ReadCapacityUnits': int(tableDefinition["readCapacity"]),
											              'WriteCapacityUnits': int(tableDefinition["writeCapacity"]),
											          },
											          TableName=tableDefinition["tableName"]
											      )
											      ## End TODO 2
											      return response
											  
											  
											  def waitForTableCreation(ddbClient, tableName):
											      ## TODO 3: Add a waiter to pause the script until your new table exists
											      waiter = ddbClient.get_waiter('table_exists')
											      waiter.wait(TableName=tableName)
											      ## End TODO 3
											  
											  
											  def getTableInfo(ddbClient, tableName):
											      response = ddbClient.describe_table(
											          TableName=tableName
											      )
											  
											      return response
											  
											  ## Utility methods
											  
											  def readConfig():
											      config = configparser.ConfigParser()
											      config.read('./labRepo/config.ini')
											  
											      return config['DynamoDB']
											  
											  
											  ## TODO 1: create an Amazon DynamoDB service client to pass to the
											  ## main function.
											  client = boto3.client('dynamodb')
											  ## End TODO 1
											  
											  try:
											      main(client)
											  except botocore.exceptions.ClientError as err:
											      print(err.response['Error']['Message'])
											  except botocore.exceptions.ParamValidationError as error:
											      print(error)
											  ```
									- ## Task 2: Load data into the table
										- **High-Level Instructions**
											- Finish **labRepo/loadData.py** to import notes to your new table.
											- Complete the **TODO 4** section to add an item to the table using the resource and note passed to the function.
											- Run the script and resolve any errors.
										- ### Task 2.1: Develop code to load data into your table and run the code
										  collapsed:: true
											- ```python
											  def putNote(table, note):
											      print("loading note " + str(note))
											      ## TODO 4: Add code that uses the function parameters to 
											      # add a new note to the table.
											      table.put_item(
											          Item={
											              'UserId': note["UserId"],
											              'NoteId': int(note["NoteId"]),
											              'Note': note["Note"]
											          }
											      )
											      ## END TODO 4
											  ```
										- ### `loadData.py` full code
										  collapsed:: true
											- ```python
											  import boto3, botocore, configparser, json
											  
											  
											  def main(ddbResource):
											      
											      config = readConfig()
											      tableName = config['tableName']
											      jsonFileName = config['sourcenotes']
											  
											      # Opening JSON file
											      f = open(jsonFileName)
											  
											      print("\n Loading \"" + tableName +
											          "\" table with data from file \"" + jsonFileName + "\"\n\n")
											      # Load json object from file
											      notes = json.load(f)
											  
											      # Create dynamodb table resource
											      table = ddbResource.Table(tableName)
											  
											      # Iterating through the notes and putting them in the table
											      for n in notes:
											          putNote(table, n)
											  
											      # Closing the JSON file
											      f.close()
											      print("\nFinished loading notes from the JSON file.\n")
											  
											  
											  def putNote(table, note):
											      print("loading note " + str(note))
											      ## TODO 4: Add code that uses the function parameters to 
											      # add a new note to the table.
											      table.put_item(
											          Item={
											              'UserId': note["UserId"],
											              'NoteId': int(note["NoteId"]),
											              'Note': note["Note"]
											          }
											      )
											      ## END TODO 4
											      
											  
											  ## Utility methods
											  def readConfig():
											      config = configparser.ConfigParser()
											      config.read('./labRepo/config.ini')
											  
											      return config['DynamoDB']
											  
											  resource = boto3.resource('dynamodb')
											  
											  try:
											      main(resource)
											  except botocore.exceptions.ParamValidationError as error:
											      print(error)
											  ```
									- ## Task 3: Query data using a partition key and projections
										- **High-Level Instructions**
											- Finish **labRepo/queryData.py** to find notes for a specific UserId.
											- Complete the **TODO 5** to query your table.
											- Run the script and resolve any errors.
										- ### Task 3.1: Develop code to return a specific note from your table
										  collapsed:: true
											- ```python
											  def queryNotesByPartitionKey(ddbClient, tableName, qUserId):
											      ## TODO 5: Add code to query for a specific not with the parameter 
											      # values available for use.
											      response = ddbClient.query(
											          TableName=tableName,
											          KeyConditionExpression='UserId = :userId',
											          ExpressionAttributeValues={
											              ':userId': {"S": qUserId}
											          },
											          ProjectionExpression="NoteId, Note"
											      )
											      ## End TODO 5
											      return response["Items"]
											  ```
										- ### `queryData.py` full code
										  collapsed:: true
											- ```python
											  import boto3, botocore, json, decimal, configparser
											  from boto3.dynamodb.conditions import Key, Attr
											  from boto3.dynamodb.types import TypeDeserializer
											  
											  
											  def main(ddbClient):
											      
											      ##load configuration data from file
											      config = readConfig()
											  
											      tableName = config['tableName']
											      UserId = config['queryUserId']
											  
											      print("\n************\nQuerying for notes that belong to user " + UserId + "...\n")
											      printNotes(queryNotesByPartitionKey(ddbClient, tableName, UserId))
											  
											  def queryNotesByPartitionKey(ddbClient, tableName, qUserId):
											      ## TODO 5: Add code to query for a specific not with the parameter 
											      # values available for use.
											      response = ddbClient.query(
											          TableName=tableName,
											          KeyConditionExpression='UserId = :userId',
											          ExpressionAttributeValues={
											              ':userId': {"S": qUserId}
											          },
											          ProjectionExpression="NoteId, Note"
											      )
											      ## End TODO 5
											      return response["Items"]
											  
											  ## Utility methods
											  def printNotes(notes):
											      if isinstance(notes, list):
											          for note in notes:
											              print(
											                  json.dumps(
											                      {key: TypeDeserializer().deserialize(value) for key, value in note.items()},
											                      cls=DecimalEncoder
											                  )
											              )
											  
											  # Helper class to convert a DynamoDB item to JSON.
											  class DecimalEncoder(json.JSONEncoder):
											      def default(self, o):
											          if isinstance(o, decimal.Decimal):
											              return str(o)
											          if isinstance(o, set):  # <---resolving sets as lists
											              return list(o)
											          return super(DecimalEncoder, self).default(o)
											  
											  def readConfig():
											      config = configparser.ConfigParser()
											      config.read('./labRepo/config.ini')
											  
											      return config['DynamoDB']
											  
											  client = boto3.client('dynamodb')
											  
											  try:
											      main(client)
											  except botocore.exceptions.ClientError as err:
											      print(err.response['Error']['Message'])
											  except botocore.exceptions.ParamValidationError as error:
											      print(error)
											  
											  ```
									- ## Task 4: Scan the table with a paginator
										- **High-Level Instructions**
											- Finish **labRepo/paginateData.py** to find notes for a specific UserId.
											- Complete **TODO 6** to scan with a paginator.
											- Run the script and resolve any errors.
										- ### Task 4.1: Develop code to return all notes, display them in pages, and run your code
										  collapsed:: true
											- ```python
											  def queryAllNotesPaginator(ddbClient, tableName, pageSize):
											  
											      ## TODO 6: Add code that creates a paginator and uses the printNotes function 
											      # to print the items returned in each page.
											      paginator = ddbClient.get_paginator('scan')
											  
											      page_iterator = paginator.paginate(
											          TableName=tableName,
											          PaginationConfig={
											              'PageSize': pageSize
											          })
											  
											      pageNumber = 0
											      for page in page_iterator:
											          if page["Count"] > 0:
											              pageNumber += 1
											              print("Starting page " + str(pageNumber))
											              printNotes(page['Items'])
											              print("End of page " + str(pageNumber) + "\n")
											      ## End TODO 6
											  ```
										- ### `paginateData.py` full code
										  collapsed:: true
											- ```python
											  import boto3, botocore, json, decimal, configparser
											  from boto3.dynamodb.conditions import Key, Attr
											  from boto3.dynamodb.types import TypeDeserializer
											  
											  
											  def main(ddbClient):
											      
											      ##load configuration data from file
											      config = readConfig()
											  
											      tableName = config['tableName']
											      pageSize = config['pageSize']
											  
											      print("\n************\nScanning with pagination...\n")
											      queryAllNotesPaginator(ddbClient, tableName, pageSize)
											  
											  def queryAllNotesPaginator(ddbClient, tableName, pageSize):
											  
											      ## TODO 6: Add code that creates a paginator and uses the printNotes function 
											      # to print the items returned in each page.
											      paginator = ddbClient.get_paginator('scan')
											  
											      page_iterator = paginator.paginate(
											          TableName=tableName,
											          PaginationConfig={
											              'PageSize': pageSize
											          })
											  
											      pageNumber = 0
											      for page in page_iterator:
											          if page["Count"] > 0:
											              pageNumber += 1
											              print("Starting page " + str(pageNumber))
											              printNotes(page['Items'])
											              print("End of page " + str(pageNumber) + "\n")
											      ## End TODO 6
											  
											  ## Utility methods
											  def printNotes(notes):
											      if isinstance(notes, list):
											          for note in notes:
											              print(
											                  json.dumps(
											                      {key: TypeDeserializer().deserialize(value) for key, value in note.items()},
											                      cls=DecimalEncoder
											                  )
											              )
											  
											  # Helper class to convert a DynamoDB item to JSON.
											  class DecimalEncoder(json.JSONEncoder):
											      def default(self, o):
											          if isinstance(o, decimal.Decimal):
											              return str(o)
											          if isinstance(o, set):  # <---resolving sets as lists
											              return list(o)
											          return super(DecimalEncoder, self).default(o)
											  
											  def readConfig():
											      config = configparser.ConfigParser()
											      config.read('./labRepo/config.ini')
											  
											      return config['DynamoDB']
											  
											  client = boto3.client('dynamodb')
											  
											  try:
											      main(client)
											  except botocore.exceptions.ClientError as err:
											      print(err.response['Error']['Message'])
											  except botocore.exceptions.ParamValidationError as error:
											      print(error)
											  ```
									- ## Task 5: Update an item in the Table
									  collapsed:: true
										- **High-Level Instructions**
											- Finish **labRepo/updateItem.py** to update an item two different ways.
											- Complete **TODO 7** to add an attribute to an existing item.
											- Complete **TODO 8** to update an item conditionally based on the attribute you added.
											- Run the script and resolve any errors.
										- ### Task 5.1: Develop code to update an item in your DynamoDB table
										  collapsed:: true
											- ```python
											  def updateNewAttribute(ddbClient, tableName, qUserId, qNoteId):
											      
											      ## TODO 7: Add code to set an 'Is_Incomplete' flag to 'Yes' for the note that matches the 
											      ## provided function parameters
											      response = ddbClient.update_item(
											          TableName=tableName,
											          Key={
											              'UserId': {'S': qUserId},
											              'NoteId': {'N': str(qNoteId)}
											          },
											          ReturnValues='ALL_NEW',
											          UpdateExpression='SET Is_Incomplete = :incomplete',
											          ExpressionAttributeValues={
											              ':incomplete': {'S': 'Yes'}
											          }
											      )
											      ## End TODO 7
											      return response['Attributes']
											  ```
										- ### Task 5.2: Develop code to update an item conditionally in your DynamoDB table and run your code
										  collapsed:: true
											- ```python
											  def updateExistingAttributeConditionally(ddbClient, tableName, qUserId, qNoteId, notePrefix):
											      try:
											          ## TODO 8: Add code to update the Notes attribute for the note that matches 
											          # the passed function parameters only if the 'Is_Incomplete' attribute is 'Yes'
											          notePrefix += ' 400 KB'
											          ## End TODO 8
											          response = ddbClient.update_item(
											              TableName=tableName,
											              Key={
											                  'UserId': {'S': qUserId},
											                  'NoteId': {'N': str(qNoteId)}
											              },
											              ReturnValues='ALL_NEW',
											              UpdateExpression='SET Note = :NewNote, Is_Incomplete = :new_incomplete',
											              ConditionExpression='Is_Incomplete = :old_incomplete',
											              ExpressionAttributeValues={
											                  ':NewNote': {'S': notePrefix},
											                  ':new_incomplete': {'S': 'No'},
											                  ':old_incomplete': {'S': 'Yes'}
											              }
											          )
											          
											          return response['Attributes']
											      except botocore.exceptions.ClientError as err:
											          if err.response['Error']['Code'] == 'ConditionalCheckFailedException':
											              return "Sorry, your update is invalid mate!"
											          else:
											              return err.response['Error']['Message']
											  ```
										- ### Task 5.3: Test updating an item where the condition is not true
											- Run `python labRepo/updateItem.py`
											- Comment out line 16 `print(updateNewAttribute(ddbClient, tableName, qUserId, qNoteId))`
											- Then run `python labRepo/updateItem.py` again
										- ### `updateItem.py` full code
										  collapsed:: true
											- ```python
											  import boto3, botocore, configparser
											  
											  def main(ddbClient):
											      
											      config = readConfig()
											  
											      tableName = config['tableName']
											  
											      qUserId = config['queryUserId']
											      qNoteId = config['queryNoteId']
											      notePrefix = config['notePrefix']
											      
											  
											      print("\nUpdating the note flag for remediation...\n")
											      # print(updateNewAttribute(ddbClient, tableName, qUserId, qNoteId))
											  
											      print("\nRemediating the marked note...\n")
											      print(updateExistingAttributeConditionally(ddbClient, tableName, qUserId, qNoteId, notePrefix))
											  
											  def updateNewAttribute(ddbClient, tableName, qUserId, qNoteId):
											      
											      ## TODO 7: Add code to set an 'Is_Incomplete' flag to 'Yes' for the note that matches the 
											      ## provided function parameters
											      response = ddbClient.update_item(
											          TableName=tableName,
											          Key={
											              'UserId': {'S': qUserId},
											              'NoteId': {'N': str(qNoteId)}
											          },
											          ReturnValues='ALL_NEW',
											          UpdateExpression='SET Is_Incomplete = :incomplete',
											          ExpressionAttributeValues={
											              ':incomplete': {'S': 'Yes'}
											          }
											      )
											      ## End TODO 7
											      return response['Attributes']
											  
											  
											  def updateExistingAttributeConditionally(ddbClient, tableName, qUserId, qNoteId, notePrefix):
											      try:
											          ## TODO 8: Add code to update the Notes attribute for the note that matches 
											          # the passed function parameters only if the 'Is_Incomplete' attribute is 'Yes'
											          notePrefix += ' 400 KB'
											          ## End TODO 8
											          response = ddbClient.update_item(
											              TableName=tableName,
											              Key={
											                  'UserId': {'S': qUserId},
											                  'NoteId': {'N': str(qNoteId)}
											              },
											              ReturnValues='ALL_NEW',
											              UpdateExpression='SET Note = :NewNote, Is_Incomplete = :new_incomplete',
											              ConditionExpression='Is_Incomplete = :old_incomplete',
											              ExpressionAttributeValues={
											                  ':NewNote': {'S': notePrefix},
											                  ':new_incomplete': {'S': 'No'},
											                  ':old_incomplete': {'S': 'Yes'}
											              }
											          )
											          
											          return response['Attributes']
											      except botocore.exceptions.ClientError as err:
											          if err.response['Error']['Code'] == 'ConditionalCheckFailedException':
											              return "Sorry, your update is invalid mate!"
											          else:
											              return err.response['Error']['Message']
											  
											  ## Utility methods
											  def readConfig():
											      config = configparser.ConfigParser()
											      config.read('./labRepo/config.ini')
											  
											      return config['DynamoDB']
											  
											  client = boto3.client('dynamodb')
											  
											  try:
											      main(client)
											  except botocore.exceptions.ClientError as err:
											      print(err.response['Error']['Message'])
											  except botocore.exceptions.ParamValidationError as error:
											      print(error)
											  ```
									- ## Optional Task 6: Using PartiQL for DynamoDB
										- **High-Level Instructions**
											- Finish **labRepo/partiQL.py** to retrieve items from your table.
											- Complete **TODO 9** to use PartiQL to query your table.
											- Run the script and resolve any errors.
										- ### Task 6.1: Develop code to query DynamoDB with PartiQL and run your code
										  collapsed:: true
											- ```python
											  def querySpecificNote(ddbClient, tableName, qUserId, qNoteId):
											      ## TODO 9: Using PartiQL, add code to query for a specific note with the parameter 
											      # values available for use.
											      response = ddbClient.execute_statement(
											          Statement="SELECT * FROM " + tableName + " WHERE UserId = ? AND NoteId = ?",
											          Parameters=[
											              {"S": qUserId},
											              {"N": str(qNoteId)}
											          ]
											      )
											      ## End TODO 9
											      return response["Items"]
											  ```
										- ### `partiQL.py` full code
										  collapsed:: true
											- ```python
											  import boto3, botocore, json, decimal, configparser
											  from boto3.dynamodb.conditions import Key, Attr
											  from boto3.dynamodb.types import TypeDeserializer
											  
											  def main(ddbClient):
											      
											      ##load configuration data from file
											      config = readConfig()
											  
											      tableName = config['tableName']
											  
											      UserId = config['queryUserId']
											      NoteId = config['queryNoteId']
											      
											      print("\n************\nQuerying for note " + str(NoteId) + " that belongs to user " + UserId + "...\n")
											      printNotes(querySpecificNote(ddbClient, tableName, UserId, NoteId))
											  
											  def querySpecificNote(ddbClient, tableName, qUserId, qNoteId):
											      ## TODO 9: Using PartiQL, add code to query for a specific note with the parameter 
											      # values available for use.
											      response = ddbClient.execute_statement(
											          Statement="SELECT * FROM " + tableName + " WHERE UserId = ? AND NoteId = ?",
											          Parameters=[
											              {"S": qUserId},
											              {"N": str(qNoteId)}
											          ]
											      )
											      ## End TODO 9
											      
											      return response["Items"]
											      
											  ## Utility methods
											  
											  # Helper function to deserialize DynamoDB JSON ('Notes': {'S': 'Note text'}) 
											  # to standard JSON ('Notes': 'Note text')
											  def printNotes(notes):
											      if isinstance(notes, list):
											          for note in notes:
											              print(
											                  json.dumps(
											                      {key: TypeDeserializer().deserialize(value) for key, value in note.items()},
											                      cls=DecimalEncoder
											                  )
											              )
											  
											  # Helper class to convert a DynamoDB item to JSON.
											  class DecimalEncoder(json.JSONEncoder):
											      def default(self, o):
											          if isinstance(o, decimal.Decimal):
											              return str(o)
											          if isinstance(o, set):  # <---resolving sets as lists
											              return list(o)
											          return super(DecimalEncoder, self).default(o)
											  
											  def readConfig():
											      config = configparser.ConfigParser()
											      config.read('./labRepo/config.ini')
											  
											      return config['DynamoDB']
											  
											  client = boto3.client('dynamodb')
											  
											  try:
											      main(client)
											  except botocore.exceptions.ClientError as err:
											      print(err.response['Error']['Message'])
											  except botocore.exceptions.ParamValidationError as error:
											      print(error)
											  ```
								- # ((66f40009-10e5-4332-a7be-b4b5ea1e47e5))
								  collapsed:: true
									- ## ((66f40039-1235-4db8-9273-41edad28b3b3))
										- By the end of this module, you will be able to:
											- Explore how AWS Lambda works
											- Develop an AWS Lambda function using SDKs
											- Configure triggers and permissions for Lambda functions
											- Test, deploy, and monitor Lambda function
									- ## ((66f40079-217a-42ac-9e9b-3c96fce8fc7f))
										- ((66f40093-e76c-45f3-ac2a-6d9aaa94115b))
											- Instances - ((6463499e-bd2d-4c48-b05b-bdddeb7d8bba))
											- Containers - ((64b7eede-2e9c-445d-b566-71db85dfa49c)) and ((64b7efa1-ae9e-4219-ae5d-b5f52ffc4251))
											- Serverless - ((66434390-e70f-4dda-8141-2cbfe223db56))
										- ((66f4009d-1341-400e-88b9-eac4f7225c7c))
											- Axis
												- Abstraction
												- Packaging
												- Pricing Model
												- Scalability and concurrency
									- ## ((66f400a7-c3ed-4b2b-bd1f-e8620c22131c))
										- ((66f40116-b57f-4454-b0fc-3887e69f97b2))
											- Basically just a script that runs in a defined runtime
										- ((66f401d4-1bd8-4373-a91f-674b23830829))
											- ![image.png](../assets/image_1727267360684_0.png)
										- ((66f40245-daf5-4395-b918-2d158c8dacdf))
									- ## ((66f40375-acf9-4ce0-9735-f66cddcc0315))
										- ((66f404af-0df0-4473-8c6c-8b8f079b230e))
										- ((66f404bf-e5d2-4f3c-9664-2bc761b397c7))
											- 15 mins max length of running
										- ((66f404f6-1716-4e3c-8e3f-e23ec8dd4516))
										- ((66f4050b-61ce-4207-8fc9-5ec9afd55478))
										- ((66f40519-f85e-4525-8df6-8ce34a608299))
										- ((66f40526-94d1-4467-a0c0-49888b255886))
											- Lambda SnapStart
											- Available for Java 11 and Java 17 managed runtimes
									- ## ((66f40532-a68d-4af2-a9f9-4d354b011631))
										- ((66f40541-a4de-4c84-bee1-9352afc71e09))
											- Invocation permissions
												- Grant event sources permission to invoke Lambda
												- Update the resource policy associated with your Lambda function
												- Use the Lambda AddPermission API
											- Processing permissions
												- Grant AWS Lambda permission to read from the stream
												- Update the execution role
										- ((66f4054a-42fd-4f27-9306-83730fb7b6bc))
										- ((66f407ed-c587-41ac-8b94-d7ae7e2f511d))
									- ## ((66f407f8-076e-4d7e-9acd-c9ff53f7922d))
										- ((66f40916-9b79-4789-82b9-8cb60c47c297))
										- ((66f4091d-f7b3-43ab-bb3f-16a68960dcd4))
										- ((66f40924-57ea-4526-b0d9-c17f2e0c82bc))
										- ((66f4092c-9aad-4980-867a-fc5eebc7adaa))
										- ((66f40933-f3c1-4278-b2d5-54b9944b169b))
										- ((66f4098c-3738-434f-b507-955b7087c0cf))
										- ((66f409b3-c5b0-40b5-bac8-268a6546ea39))
										- ((66f409bc-3fef-40d5-9403-77726e3e2162))
											- ![image.png](../assets/image_1727269330691_0.png)
										- ((66f409e2-9ade-4143-8f2d-cf919b92235b))
										- ((66f409f0-a497-4a4b-990f-bf1f3381f49d))
											- Allows you to adjust the behaviour of a Lambda function without updating its code
											- Encrypted at-rest
											- Stored in function's version-specific configuration
										- ((66f40a37-79a3-46d4-832f-49bfe8ea3622))
											- CreateFunction
												- Create a Lambda function through a deployment package
												- Package type can be a ZIP or a container image
											- UpdateFunctionCode
												- Update the code of the Lambda function
												- Code must be unpublished
											- UpdateFunctionConfiguration
												- Modify the version-specific settings of the Lambda function
											- Invoke
												- Invokes a Lambda function synchronously or asynchronously
										- ((66f40aa4-d623-47d8-a17f-7b0f79e0c579))
										- ((66f40ab2-d456-429a-9fb9-b72eb8241f39))
										- ((66f40cfc-ce75-47d5-9bf9-7918e7d95a3b))
										- ((66f40d05-5036-4396-b395-511478e390f1))
										- ((66f40d0d-e469-4e26-9f68-92935c59e121))
									- ## ((66f40d15-8136-4182-90cd-1163c26e8699))
										- ((66f40d25-1f54-40d3-b3b6-e5a470530c17))
										- ((66f40d2f-0c59-4366-891a-ab813256d7d6))
										- ((66f40d39-1cf1-4188-b29f-2d7b333c5d9f))
										- ((66f40d43-798e-4387-b543-39d308e235c3))
										- ((66f40d87-c103-4517-8137-8089772117cf))
										- ((66f40d92-dc20-4b65-b041-139b412b81c4))
											- Invocation errors
												- Max 1000 concurrent run limit per region by default
											- Function errors
												- Response header: `X-Amz-Function-Error`
									- ## ((66f40dd7-45dd-4d15-b5ea-43d651158ee2))
										- ((66f40de6-8229-4c37-a70b-08e4d38220b9))
										- ((66f40df1-962c-4504-8928-b0f90577a6cd))
											- Dependencies should be at the root level
										- ((66f40dfe-075f-4cc7-b6ed-74a430a59858))
										- ((66f40e07-ede1-4b93-b967-76d5d1b97376))
									- ## ((66f40ee7-6907-4b9e-a9f7-3ecdfa04f680))
										- The AWS Lambda service handles servers, capacity, and deployment needs for you.
										  logseq.order-list-type:: number
											- **True**
											  logseq.order-list-type:: number
										- Your AWS Lambda function needs Invocation permissions to access other AWS resources in your
										  logseq.order-list-type:: number
										  account.
											- **False**
											  logseq.order-list-type:: number
											- Your AWS Lambda function needs processing permissions to access other AWS resources in your account.
											  logseq.order-list-type:: number
										- Developing and creating a Lambda function is possible only through the AWS Lambda console.
										  logseq.order-list-type:: number
											- **False**
											  logseq.order-list-type:: number
											- In addition to the AWS Lambda console, you can use the AWS CLI. You can also interact with your custom code using AWS SDKs. Further, both Eclipse’and Visual Studio toolkits support the development of Lambda functions.
											  logseq.order-list-type:: number
										- If you enable DynamoDB Streams on a table, you can associate the stream ARN with a Lambda function that you write.
										  logseq.order-list-type:: number
											- **True**
											  logseq.order-list-type:: number
										- Each Lambda function runs in its own isolated environment, with its own resources and file system view.
										  logseq.order-list-type:: number
											- **True**
											  logseq.order-list-type:: number
										- AWS Lambda's programming model is stateless, but it can still access
										  logseq.order-list-type:: number
										  stateful data.
											- **True**
											  logseq.order-list-type:: number
											- Although AWS Lambda’s programming model is stateless, your codeicah access stateful data by calling other web services, such as Amazon S3 or Amazon DynamoDB
											  logseq.order-list-type:: number
								- # ((66f4150a-c2f5-411b-91fa-4e1180cbbb8e))
								  collapsed:: true
									- ### Objectives
										- After completing this lab, you will be able to:
											- Create AWS Lambda functions and interact programmatically using AWS SDKs and the AWS CLI.
											- Configure Lambda functions to use the environment variables and integrate with other services.
											- Generate Amazon S3 pre-signed URLs using AWS SDKs and verify the access to bucket objects.
											- Deploy the Lambda functions with .zip file archives through your IDE and test as needed.
											- Invoke AWS Lambda functions using the AWS Console and AWS CLI.
									- ## Task 1: Create an AWS Lambda function
										- **High-Level Instructions**
											- Use the AWS Console to create the `dictate-function`
											- Set the runtime to **python3.11**.
											- Use **lambdaPollyRole** to grant the Lambda function permissions
									- ## Task 2: Add processing logic to the Lambda function code
										- **High-Level Instructions**
											- **Command:**  Add two environment variables, **MP3_BUCKET_NAME** and **TABLE_NAME**, to the **dictate-function**. Be sure to replace *APIBUCKETNAME* with the **APIBucketName** value from the left side of the lab page.
												- ```
												  apiBucket=APIBUCKETNAME
												  notesTable='Notes'
												  ```
											- In AWS Cloud9 complete **app.py** in **api/dictate-function** folder using the parameters passed to each function:
												- Add code to TODO1 that returns the note text from Amazon DynamoDB.
												- Add code to TODO2 that creates a local MP3 file in the `/tmp` folder with an audio version of that note using Amazon Polly and returns the file location.
												- Add code to TODO3 that uploads the MP3 file to Amazon S3, removes the local file, and returns a pre-signed URL to that object.
										- ### Task 2.1: Add code to retrieve the note text from Amazon DynamoDB
											- Add env variables using the terminal
												- `apiBucket=APIBUCKETNAME`
												  Replace the e.g. `=labstack-0afd9c74-6703-4bce-96-pollynotesapibucket-mmjxczcsrka6`
												- `notesTable='Notes'`
											- Update the Lambda env varariables
												- ```bash
												  aws lambda update-function-configuration \
												  --function-name dictate-function \
												  --environment Variables="{MP3_BUCKET_NAME=$apiBucket, TABLE_NAME=$notesTable}"
												  ```
												- `q` to quit the prompt
											- ```python
											  def getNote(dynamoDBResource, ddbTable, UserId, NoteId):
											      print("getNote Function")
											  
											      table = dynamoDBResource.Table(ddbTable)
											      records = table.get_item(
											          Key={
											              'UserId': UserId,
											              'NoteId': int(NoteId)
											          }
											      )
											  # TODO 1: Get the note text from the pollynotes DynamoDB table that matches the UserId and NoteId
											      return records['Item']['Note']
											      # End TODO 1
											  ```
										- ### Task 2.2: Add code to use Amazon Polly to convert the note text to an MP3 file
											- ```python
											  def createMP3File(pollyClient, text, VoiceId, NoteId):
											      print("createMP3File Function")
											      # TODO 2: Use polly to convert the note text to speech using the VoiceId
											      # and save the file as an MP3 in the /tmp folder
											      pollyResponse = pollyClient.synthesize_speech(
											          OutputFormat='mp3',
											          Text = text,
											          VoiceId = VoiceId
											      )
											      # End TODO 2
											      if "AudioStream" in pollyResponse:
											          postId = str(NoteId)
											          with closing(pollyResponse["AudioStream"]) as stream:
											              filePath = os.path.join("/tmp/", postId)
											              with open(filePath, "wb") as file:
											                  file.write(stream.read())
											  
											      return filePath
											  ```
										- ### Task 2.3: Add code to upload the MP3 file to Amazon S3 and generate a pre-signed URL
											- ```python
											  def hostFileOnS3(s3Client, filePath, mp3Bucket, UserId, NoteId):
											      print("hostFileOnS3 Function")
											      # TODO 3: Upload the mp3 file to S3 mp3Bucket and generate a pre-signed URL to access the MP3 object
											      s3Client.upload_file(filePath, 
											      mp3Bucket, 
											      UserId+'/'+NoteId+'.mp3')
											      # End TODO 3
											      
											      # Remove the file from the temp location to avoid potential data leaks
											      os.remove(filePath)
											  
											      # Generate a pre-signed URL to access the MP3 object
											      url = s3Client.generate_presigned_url(
											          ClientMethod='get_object',
											          Params={
											              'Bucket': mp3Bucket,
											              'Key': UserId+'/'+NoteId+'.mp3'
											          }
											      )
											      return url
											  ```
										- ### `app.py` full code
										  collapsed:: true
											- ```python
											  # This lambda function is will get a note text from DynamoDB,
											  # convert the text to speech and save it as an MP3 file,
											  # Save that MP3 file in S3 and return a generated signed URL to access that file.
											  
											  from __future__ import print_function
											  import boto3
											  import os
											  from contextlib import closing
											  
											  dynamoDBResource = boto3.resource('dynamodb')
											  pollyClient = boto3.client('polly')
											  s3Client = boto3.client('s3', endpoint_url='https://s3.' +
											                          os.environ['AWS_REGION'] + '.amazonaws.com')
											  
											  
											  def lambda_handler(event, context):
											  
											      # Log debug information
											      print(event)
											  
											      # Extract the user parameters from the event and environment
											      UserId = event["UserId"]
											      NoteId = event["NoteId"]
											      VoiceId = event['VoiceId']
											      mp3Bucket = os.environ['MP3_BUCKET_NAME']
											      ddbTable = os.environ['TABLE_NAME']
											  
											      # Get the note text from the database
											      text = getNote(dynamoDBResource, ddbTable, UserId, NoteId)
											  
											      # Save a MP3 file locally with the output from polly
											      filePath = createMP3File(pollyClient, text, VoiceId, NoteId)
											  
											      # Host the file on S3 that is accessed by a pre-signed url
											      signedURL = hostFileOnS3(s3Client, filePath, mp3Bucket, UserId, NoteId)
											  
											      return signedURL
											  
											  
											  def getNote(dynamoDBResource, ddbTable, UserId, NoteId):
											      print("getNote Function")
											  
											      table = dynamoDBResource.Table(ddbTable)
											      records = table.get_item(
											          Key={
											              'UserId': UserId,
											              'NoteId': int(NoteId)
											          }
											      )
											  # TODO 1: Get the note text from the pollynotes DynamoDB table that matches the UserId and NoteId
											      return records['Item']['Note']
											      # End TODO 1
											  
											  
											  def createMP3File(pollyClient, text, VoiceId, NoteId):
											      print("createMP3File Function")
											      # TODO 2: Use polly to convert the note text to speech using the VoiceId
											      # and save the file as an MP3 in the /tmp folder
											      pollyResponse = pollyClient.synthesize_speech(
											          OutputFormat='mp3',
											          Text = text,
											          VoiceId = VoiceId
											      )
											      # End TODO 2
											      if "AudioStream" in pollyResponse:
											          postId = str(NoteId)
											          with closing(pollyResponse["AudioStream"]) as stream:
											              filePath = os.path.join("/tmp/", postId)
											              with open(filePath, "wb") as file:
											                  file.write(stream.read())
											  
											      return filePath
											  
											  
											  def hostFileOnS3(s3Client, filePath, mp3Bucket, UserId, NoteId):
											      print("hostFileOnS3 Function")
											      # TODO 3: Upload the mp3 file to S3 mp3Bucket and generate a pre-signed URL to access the MP3 object
											      s3Client.upload_file(filePath, 
											      mp3Bucket, 
											      UserId+'/'+NoteId+'.mp3')
											      # End TODO 3
											      
											      # Remove the file from the temp location to avoid potential data leaks
											      os.remove(filePath)
											  
											      # Generate a pre-signed URL to access the MP3 object
											      url = s3Client.generate_presigned_url(
											          ClientMethod='get_object',
											          Params={
											              'Bucket': mp3Bucket,
											              'Key': UserId+'/'+NoteId+'.mp3'
											          }
											      )
											      return url
											  ```
									- ## Task 3: Publish an AWS Lambda function
										- **High-Level Instructions**
											- Create a zip file that contains your app.py as a deployment package.
												- `zip dictate-function.zip app.py`
											- Update the code of the function, created in task 1, with your deployment package.
												- ```bash
												  aws lambda update-function-code \
												  --function-name dictate-function \
												  --zip-file fileb://dictate-function.zip
												  ```
											- Update the function handler to match the path to the handler function in your deployment package.
												- ```bash
												  aws lambda update-function-configuration \
												  --function-name dictate-function \
												  --handler app.lambda_handler
												  ```
									- ## Task 4: Invoke an AWS Lambda function
										- **High-Level Instructions**
											- Invoke the Lambda function with the following event using the AWS CLI and AWS Management Console.
												- ```
												  {
												  	"UserId": "newbie",
												  	"NoteId": "2",
												  	"VoiceId": "Joey"
												  }
												  ```
										- ### Task 4.1: Invoke the AWS Lambda function in your AWS Cloud9 terminal
											- `touch dictate-function/event.json`
											- Add this text to the file
												- ```json
												  {
												    "UserId": "newbie",
												    "NoteId": "2",
												    "VoiceId": "Joey"
												  }
												  ```
											- ```bash
											  aws lambda invoke \
											  --function-name dictate-function \
											  --payload fileb://event.json response.txt
											  ```
											- Related: ((65770a27-6361-4507-9cff-d2f1217d157d)) - quite an effort to do multi-line on terminal compared to copy/paste
										- ### Task 4.2: Invoke the AWS Lambda function in the AWS console
											- Lambda > Test
											- **Test event action:**   Create new event
											- **Event name:** `testPolly`
											- **Event sharing settings:**  Private
											- **Template - optional:** hello-world
											- **Event JSON:** Replace the default JSON object with the following:
												- ```json
												  {
												    "UserId": "newbie",
												    "NoteId": "2",
												    "VoiceId": "Joey"
												  }
												  ```
											- Save, then Test
											- Copy the URL returned in the execution log (without the surrounding quotes) and browse to that URL. It should play a second MP3
									- ## Optional Challenge Task 5: Create the remaining AWS Lambda functions used in the course application
										- **High-Level Instructions**
											- Using the `aws lambda create-function` command and the code in the api folder create the remaining functions:
												- createUpdate-function
												- search-function
												- delete-function
												- list-function
											- Use the `lambdaPollyRole` for all functions
											- Test all the functions with the provided **event.json** files in each folder.
										- ### Task 5.1: Create the functions
										  collapsed:: true
											- Create a variable for the ARN of the **lambdaPollyRole** that the functions will use:
												- ```bash
												  roleArn=$(aws iam list-roles --output text --query 'Roles[?contains(RoleName, `lambdaPollyRole`) == `true`].Arn')
												  ```
											- Set the **folderName** variable for the **createUpdate-function** folder
												- `folderName=createUpdate-function`
											- `zip $folderName.zip app.py`
											- ```bash
											  aws lambda create-function \
											  --function-name $folderName  \
											  --handler app.lambda_handler \
											  --runtime python3.11 \
											  --role $roleArn \
											  --environment Variables={TABLE_NAME=$notesTable} \
											  --zip-file fileb://$folderName.zip
											  ```
											- Create the remaining functions (script)
												- ```bash
												  functionName=[ReplaceName]
												  
												  folderName=$functionName
												  cd ~/environment/api/$folderName
												  
												  ## Bundle and create the function
												  zip $folderName.zip app.py
												  aws lambda create-function \
												  --function-name $functionName  \
												  --handler app.lambda_handler \
												  --runtime python3.11 \
												  --role $roleArn \
												  --environment Variables={TABLE_NAME=$notesTable} \
												  --zip-file fileb://$folderName.zip
												  ```
										- ### Task 5.2: Test the new functions
											- ```bash
											  functionName=[ReplaceName]
											  folderName=$functionName
											  cd ~/environment/api/$folderName
											  
											  ## Test the function with the provided test event
											  aws lambda invoke \
											  --function-name $functionName \
											  --payload fileb://event.json response.txt
											  ```
								- # ((66f4151b-27f4-440f-b63c-11e7e079b3d0))
								  collapsed:: true
									- ((66f42705-bf20-46e0-8503-4db7311c538f))
										- By the end of this module, you will be able to:
										- Describe the key components of ((6529032b-bb04-4660-836b-f33e1ae727ba))
										- Develop API Gateway resources to integrate with AWS services
										- Configure API request and response calls for your application endpoints
										- Test API resources and deploy your application API endpoint
										- Demonstrate creating API Gateway resources to interact with your application APIs
									- ## ((66f42739-722c-4af2-810e-44d278b9b274))
										- ((66f4273e-a589-477e-a549-baeb27cfaafc))
											- Create, publish, maintain, monitor and secure APIs that access AWS or other third-party services.
											- ![image.png](../assets/image_1727277047367_0.png)
										- ((66f42821-3047-4f52-80c1-eb9bc6dd8013))
											- HTTP APIs can access a URL slug
												- Cheaper and low latency
												- Less featureful like no throttling
											- REST APIs can use sub-slugs e.g. `https://api.example.com/myservice/notes/search`
										- ((66f42887-16cd-417a-bbf9-e3f2918285c4))
											- They're for bidirectional communication
										- ((66f428b4-496c-41df-b728-5309b184ab17))
											- ![image.png](../assets/image_1727277265681_0.png)
												- Resources e.g. `/notes GET`
												- Methods e.g. `/notes/(id) POST`
										- ((66f42907-5e4e-4f40-b036-8e502e83af63))
											- Host multiple versions
											- Data transformations
											- Configure API keys
											- Throttle limits
											- Control and manage access
											- Response caching
											- Mock integrations
											- SDK generation
											- Data transformations
									- ## ((66f4297d-81fc-4cb6-9be7-d984bd4f04fc))
										- ((66f429b2-8628-4422-b1fb-be2a40408e33))
										- ((66f429c7-b185-4ad9-907f-ef0b35566b3f))
										- ((66f429d3-2fd1-4948-8e37-adb9d94e6bc7))
									- ## ((66f42a38-04a8-4902-a799-82dd4f30790f))
										- ((66f42ad4-d2bc-494b-a9fa-070dbc01bfb9))
										- ((66f42ae0-c674-48b8-9067-92651aca4e30))
											- Mapping template is in VTL, which is similar to XML
											- Converted to JSON
										- ((66f42b18-43f8-4d26-971e-05ac7958cd21))
										- ((66f42b20-a60d-4bbc-8694-2aa86f0e0f9d))
										- ((66f42b2a-50b2-4958-8e89-d34cb06bf0f7))
									- ## ((66f42b33-e024-4e25-9769-31636dada64d))
										- ((66f42b3f-e485-46ad-a287-1ad330267632))
									- ## ((66f42b49-7e44-4ae8-8c78-1348440c1260))
										- ((66f42b55-aa18-44b4-a5bb-c725bb56a443))
										- ((66f42b5d-9438-4692-949f-e634c48d5395))
										- ((66f42b65-e664-463f-bcd5-7d5cb5a3bbd3))
										- ((66f42b6f-c9ce-4ffe-a9d7-93b480ebcba6))
										- ((66f42b80-ab0d-433b-aeb9-192eb6c754a0))
									- ## ((66f42b89-5ec1-4422-9239-3d264269b2ae))
										- ((66f42b9a-833d-48c5-8f09-b67fbd7ac4ab))
										- ((66f42ba2-17af-4b2e-a8b8-1cb6d0e7596a))
										- ((66f42baa-381d-4a28-959f-224d57e8065c))
										- ((66f42bb1-6a13-4264-be76-73247f53f755))
									- ## ((66f42bc2-37ec-41ae-b999-4776d9da9e97))
									  collapsed:: true
										- With Amazon AP! Gateway, developers can create, publish,
										  logseq.order-list-type:: number
										  maintain, monitor, and secure APIs.
											- **True**
											  logseq.order-list-type:: number
										- In a canary release deployment, you partially deploy a new software feature and shift some percentage of API traffic to the new version of the application.
										  logseq.order-list-type:: number
											- **True**
											  logseq.order-list-type:: number
										- Mock integrations respond only to a 200 status code for API methods.
										  logseq.order-list-type:: number
											- **False**
											  logseq.order-list-type:: number
											- API developers can configure any status code and decide how AP! Gateway responds to a mock integration request.
											  logseq.order-list-type:: number
										- A resource is a logical entity that an application can access through a
										  logseq.order-list-type:: number
										  resource path.
											- **True**
											  logseq.order-list-type:: number
										- Stage variables are name-value pairs that you can define as configuration attributes associated with a
										  logseq.order-list-type:: number
										  deployment stage of a REST API.
											- **True**
											  logseq.order-list-type:: number
										- To handle a diverse array of API calls intelligently, you can use an AWS
										  logseq.order-list-type:: number
										  Lambda function as a CRUD backend.
											- **True**
											  logseq.order-list-type:: number
									- Practice exam questions
										- 8) A developer is building a web application that uses Amazon API Gateway. The developer wants to maintain different environments for development (dev) and production (prod) workloads. The API will be backed by an AWS Lambda function with two aliases: one for dev and one for prod.
										  collapsed:: true
										  How can the developer maintain these environments with the LEAST amount of configuration?
											- Correct
												- B) Create one REST API. Integrate the API with the Lambda function by using a stage variable in place of an alias. Deploy the API to two different stages: dev and prod. Create a stage variable in each stage with different aliases as the values. Access the API by using the different stage URLs.
											- Incorrect
												- A) Create a REST API for each environment. Integrate the APIs with the corresponding dev and prod aliases of the Lambda function. Deploy the APIs to their respective stages. Access the APIs by using the stage URLs.
												- C) Create one REST API. Integrate the API with the dev alias of the Lambda function. Deploy the API to the dev environment. Configure a canary release deployment for the prod environment where the canary will integrate with the Lambda prod alias.
												- D) Create one REST API. Integrate the API with the prod alias of the Lambda function. Deploy the API to the prod environment. Configure a canary release deployment for the dev environment where the canary will integrate with the Lambda dev alias.
										- 10) A developer is testing an application locally and has deployed the application to an AWS Lambda function. To avoid exceeding the deployment package size quota, the developer did not include the dependencies in the deployment file. When the developer tests the application remotely, the Lambda function does not run because of missing dependencies.
										  collapsed:: true
										  Which solution will resolve this issue?
											- Correct
												- D) Create a layer that contains the missing dependencies. Attach the layer to the Lambda function.
											- Incorrect
												- A) Use the Lambda console editor to update the code and include the missing dependencies.
												- B) Create an additional .zip file that contains the missing dependencies. Include the .zip file in the original Lambda deployment package.
												- C) Add references to the missing dependencies in the Lambda function's environment variables.
										- 1) Acompany is migrating a legacy application to Amazon 562 instances. The application uses a user name and password that are stored in the source code to connect to a MySQL database. The company will migrate the database to an Amazon RDS for MySQL DB instance. As part of the migration, the
										  collapsed:: true
										  company needs to implement a secure way to store and automatically rotate the database credentials.
										  Which solution will meet these requirements?
											- Correct
												- B) Store the database credentials in AWS Systems Manager Parameter Store. Configure Parameter Store to automatically rotate the credentials.
											- Incorrect
												- A) Store the database credentials in environment variables in an Amazon Machine Image (AMI). Rotate the credentials by replacing the AMI.
												- C) Store the database credentials in environment variables on the EC2 instances. Rotate the credentials by relaunching the EC2 instances.
												- D) Store the database credentials in AWS Secrets Manager. Configure Secrets Manager to automatically rotate the credentials.
							- # Day 3
							  collapsed:: true
								- ## Agenda
								  collapsed:: true
									- ![image.png](../assets/image_1727165453142_0.png)
								- #+BEGIN_TIP
								  You don't need the know the individual API calls, you just need to know general workflow of what steps need to be taken and how it fits together
								  #+END_TIP
								- # ((66f51656-27bc-44dd-8b77-13c204eca908))
								  collapsed:: true
									- Overview
										- Now that you have the core backend set up for storage, database, and compute processing, you need a way for users to access the AWS Lambda functions over the internet.
										- In this lab, you will create an Amazon API Gateway resource for your application. You will then configure two methods for that resource to allow access to two of your AWS Lambda functions. With these methods you will validate the requests and transform the responses returned from the Lambda functions. Finally, you will configure Cross-Origin Request Sharing (CORS) headers to allow access for your web application that will be added in the next lab.
										- Once you have completed this lab, your deployment will look like the following diagram:
										  collapsed:: true
											- ![image.png](../assets/image_1727345247731_0.png)
									- ### Objectives
										- After completing this lab, you will be able to:
											- Create RESTful API resources and configure CORS for your application.
											- Integrate API methods with AWS Lambda functions to process application data.
											- Configure mapping templates to transform the pass-through data during method integration.
											- Create a request model for API methods to ensure that the pass-through data format complies with application rules.
											- Deploy the API to a stage and validate the results using the API endpoint.
									- ## Task 1: Create a REST API and resource
										- **High-Level Instructions**
											- Create a new `PollyNotesAPI` Regional REST API
											- Create a `/notes` resource with CORS enabled
										- ### Task 1.1: Create the Amazon API Gateway and resource
											- Open ((6529032b-bb04-4660-836b-f33e1ae727ba))
									- ## Task 2: Configure the GET method and add a mapping template to transform responses
										- Intro
											- The first Lambda function that you need to allow access to is the list-function. Whenever a request is sent to the API Gateway resource, using a GET method, this function should be invoked and the response returned to the requester. If a UserId is specified in the event, the Lambda function will only return items that match that UserId. Using the integration request, you will create a mapping template to hard code that parameter for now.
											- After the request is configured to return items for a single user, it is redundant to include the UserId in every item that is returned. Only returning responses with the information needed, and no more, is important to increase performance and reduce data transfer costs as your application scales.
										- **High-Level Instructions**
											- Configure a GET method for the notes resource, map it to the **list-function**, and test the output.
											- Add a mapping template to manually specify `{"UserId":"student"}` and confirm the output.
											- Create a response mapping template to transform the response to only return the note id and note text.
										- ### Task 2.1: Configure GET method
											- Select the `/notes` resource
											- Create method > Method type: `GET` > Integration type: `Lambda function`
											- You're redirected back to the Resources page, with the new `GET` resource selected
											- `Test` tab
												- The Lambda function is successful and returns a Status of 200. The Response Body now returns a JSON array with all items in the DynamoDB table.
										- ### Task 2.2: Update the GET method integration request to pass a UserId variable
											- The integration request is the internal interface of a REST API method in API Gateway. In the integration request, you map the body of a route request, or the parameters and body of a method request, to the formats required by the backend.
												- Additional information: The mapping templates are a script in Velocity Template Language (VTL) that transforms a request or response body to the needed data format. Mapping templates can be specified in the integration request or in the integration response. They can reference data made available at runtime as context and stage variables.
												- The mapping can be as simple as an identity transform that passes the headers or body through the integration as-is from the client to the backend for a request. The same is true for a response, in which the payload is passed from the backend to the client.
											- In this `GET` method select the `Integration request` tab
											- Edit > scroll to Mapping templates section > Add mapping template > Content type:  `application/json` > Template body (example): `{"UserId":"student"}` > Save
											- In the **/notes - GET - Method Execution** panel, choose **Test** tab.
											- Once again the Lambda function is successful and the **Status** it returns is **200**.  The **Response Body** now returns a JSON array with only notes where the **UserId** is *student*.
										- ### Task 2.3: Limit the response data returned from the API method
											- Now that you are specifying the UserId in the request, you can reduce the amount of redundant data returned in the response. You will specify a mapping template for the integration response.
												- The integration response is the internal interface of a REST API method in API Gateway. You use the integration response to map the status codes, headers, and payload, that are received from the backend, to the response format that is returned to a client app.
											- Integration Response tab > Edit > scroll to Mapping Templates > Content type: `application/json`
											- Template body (example):
												- ```vtl
												  #set($inputRoot = $input.path('$'))
												  [
												      #foreach($elem in $inputRoot)
												      {
												          "NoteId" : "$elem.NoteId",
												          "Note" : "$elem.Note"
												      }
												      #if($foreach.hasNext),#end
												      #end
												  ]
												  ```
											- Save and Test again
												- The response is now a JSON array with just the **NoteId** and **Note** properties in each object. Since the UserId is not needed in this response you are able to reduce the amount of data returned. As more notes are entered into the system this will exponentially reduce the size of the responses. Smaller responses will lead to better application performance and reduced data transfer costs.
									- ## Task 3: Configure the POST method and add a request validation model
										- **High-Level Instructions**
											- Configure the POST method, map it to the **createUpdate-function**, and test the default behavior with a new note object.
											- Create a Model that specifies the note schema above. (The Schema can be found in task 3.2 if you need a hint.)
											- Configure validation on the request body, enforce the schema, and test a valid and invalid submission.
										- ### Task 3.1: Configure the POST method and add a request validation model
											- Select the **/notes** resource, choose the **Create Method **
											- Method type: POST
											- Lambda function: ARN example `createUpdate-function`
											- Go to Test tab
												- Request body:
												  ```json
												  {
												      "Note": "This is your new note added using the POST method",
												      "NoteId": 3,
												      "UserId": "student"
												  }
												  ```
												- It'll return just the `NoteId`
											- In the **Resources** panel, for the **/notes** resource, choose **GET** > choose **Test** tab
												- The **Response Body** now has the note you added and the placeholder notes that were already in the table.
										- ### Task 3.2: Enforce a schema for the POST request body
											- The POST function works as is, but you can make it better. For instance, if the note isn’t submitted or all required fields are not included, there is no need to pass the request to the Lambda function. Using an API Gateway Model, validate that there is information in the body of the request and choose what fields are passed to the function in the body.
											- In the left navigation panel, under **API: PollyNotesAPI**, choose **Models**.
											- Choose **Create model**.
											- For **Name**, enter `NoteModel`
											- For **Content type**, enter `application/json`
											- Model schema (example)
												- ```json
												  {
												      "title": "Note",
												      "type": "object",
												      "properties": {
												          "UserId": {"type": "string"},
												          "NoteId": {"type": "integer"},
												          "Note": {"type": "string"}
												      },
												      "required": ["UserId", "NoteId", "Note"]
												  }
												  ```
											- In the left navigation panel, under API: PollyNotesAPI, choose Resources > POST > Method Request tab > Edit
												- For **Request validator**, choose **Validate body**.
												- Expand  **Request Body** > ** Add model**
												- For **Content type**, enter `application/json`
												- For **Model**, select **NoteModel** > Save
										- ### Task 3.3: Test the request validator
											- Test tab
											- Request Body
												- ```json
												  {
												      "Note": "This is your updated note using the Model validation",
												      "UserId": "student",
												      "id": 3
												  }
												  ```
											- Then test it and notice the error because there's no `NoteId` key
												- Notice that the test was not successful, there is a **Status** of **400** and the **Response Body** clearly states that there was an **Invalid request body**.  If you review the **Logs**, there is more detail. *“Request body does not match model schema for content type application/json: [object has missing required properties ([“NoteId”])]”*
											- Try again with the new correct Request Body:
												- ```json
												  {
												      "Note": "This is your updated note using the Model validation",
												      "UserId": "student",
												      "NoteId": 3
												  }
												  ```
									- ## Task 4: Deploy the API with CORS configurations
										- Intro
											- Cross-Origin Resource Sharing (CORS) is an HTTP-header based mechanism that allows a server to indicate any other origins (domain, scheme, or port) than its own from which a browser should permit loading of resources. CORS also relies on a mechanism by which browsers make a “preflight” request, to the server hosting the cross-origin resource, in order to check that the server will permit the actual request. In that preflight, the browser sends headers that indicate the HTTP method and headers that will be used in the actual request.
											- An example of a cross-origin request: the front-end JavaScript code served from https://domain-a.com uses XMLHttpRequest to make a request for https://domain-b.com/data.json.
											- In later labs, your web application will be accessed with an Amazon S3 domain name, and the API will have an Amazon API Gateway domain name, so this configuration is required for the labs. There are many reasons to host backend APIs with different domains, configuring CORS is a common requirement in API development.
											- After configuring CORS, you will create a new stage and deploy the API. This creates an endpoint that can be accessed from the internet.
										- **High-Level Instructions**
											- Enable CORS on all methods to allow any origin.
											- Deploy the API to a Prod stage.
											- Test the API with your web browser.
										- ### Task 4.1: Configure Cross-Origin Request Sharing (CORS)
											- When you first created the API, you instructed the service to enable CORS. That created and configured the **OPTIONS** method for the resource. The **OPTIONS** method is requested when browsers perform the “preflight” request.  You have created methods, so you need to configure CORS for those methods.
											- In Resources panel select `/notes` > `Enable CORS`
												- i.e. enable all
												- For **Gateway Responses**, check the box for **Default 4XX** and **Default 5XX**. This is to allow you to view 4xx and 5xx errors from your browser in the event you need to troubleshoot.
												- For **Access-Control-Allow-Methods**, check the box for **GET**, **OPTIONS** and **POST**.
												- Save
											- For each existing method, this step added **Header Mappings** and **Response Headers** for each status code your methods have configured. Now your web browser will allow CORS for these API methods.  You can modify this configuration to make it more secure in the future when your web 
											  front-end and API use known domain names.
										- ### Task 4.2: Deploy the API
											- Intro
												- Your API has been configured, but before you can access this configuration with the API endpoint, you need to create a stage and deploy the configuration to that stage.
												- A stage is a logical reference to a lifecycle state of your API. API stages are identified by API ID and stage name. You could create a “dev” and a “prod” stage, and all changes could be deployed to dev and fully tested before you allow them to be deployed to prod.
												- Another common strategy is to have a new stage for each major or minor version of your API. Anytime you make a change that could impact legacy versions, of the front end applications that use your API, you could create a new stage (for example, “v2”). Your users would have to change the API endpoint URL to take advantage of the new features after they have confirmed that their code works with the new version.
												- An API deployment is a point-in-time snapshot of your API Gateway API. To be available for clients to use, the deployment must be associated with one or more API stages.
											- In Resources panel select `/notes` > `Deploy API`
											- Stage: `New stage` > Stage name: `Prod` > Deploy
											- Copy the **Invoke URL** and paste it to a new web browser tab, append `/notes` to the end of the URL and press Enter.
								- # ((66f5166e-b003-4d54-9b69-490523385f4d))
								  collapsed:: true
									- ## ((66f516b3-c60f-465b-b748-de46db4fd86d))
										- By the end of this module, you will be able to:
											- Describe the challenges with traditional architectures
											- Describe the microservice architecture and benefits¢ Explain various approaches for designing microservice applications
											- Explain steps involved in decoupling monolithic applications
											- Explain how to orchestrate Lambda functions using AWS Step Function
									- ## ((66f516dc-f1b0-47e8-9491-0b998eab0ed4))
										- ((66f516ec-f752-4dc0-8f69-01aa8283b9c5))
											- Architectural patterns - microservices
											- Software delivery - DevOps
											- Operational model - serverless
											- This maximises speed, scaling, resilience and security
										- ((66f51a42-a57a-451e-8d12-83565e27ca28))
										- ((66f51a4f-8458-4b25-8484-125751c696ec))
											- They can be bottlenecked by the slowest component
										- ((64b7f03d-286f-4845-9cbb-765cb4e9653b)) - you don't define the container capacity, it'll just autoscale automatically
										- ((66f528e3-1dc7-4e30-8d8b-7e27d9b22abf))
										- ((66f528f1-073d-4464-8777-5fbf6f2840aa))
										- ((66f528fa-2099-410e-9d8c-6f1d4f927481))
										- ((66f52903-ad4e-48d2-b9fa-f5d8a9dabaaf))
										- ((66f5290b-a080-44e5-8ee4-96fbdb9ac53f))
										- ((66f52912-5767-4a3e-9c1e-111bb1654795))
									- ## ((66f52919-657c-40d1-9fcd-a27166a9d90e))
										- ((66f52923-ab69-4a26-9b3f-a6f90589ad6e))
										- ((66f5292c-b17c-4478-85fc-d2557a3c22c6))
										- ((66f52934-1cdf-4f36-8319-45a193e62038))
									- ## ((66f5293b-d73b-4197-813a-a55c5b94d92f))
										- ((66f5295d-97cc-48b1-857f-5206ab80e3c7)) build
									- ## ((66f52971-98c0-41d4-8be7-5bfeb2cf7ef9))
										- ((66f5297a-6a78-4ef3-9673-ee1645aa9a84))
										- ((66f52981-2d34-4f42-b921-003f6832b4c0))
										- ((66f5298b-c924-47a1-866b-492ea579df66))
										- ((66f52992-be04-4bea-8e17-a2d2aeb9f3b4))
										- ((66f52999-1381-4c39-9e17-17edc0165fcb))
										- ((66f529a6-112d-4351-931f-7bc56ace50b5))
										- ((66f529b4-33e2-424a-b2fa-d7ab015b0372))
										- ((66f529c6-3e13-4cfc-a540-612a6ca119e7))
									- ## ((66f529d6-49b1-4c01-ba23-662bca3a4dbd))
								- # ((66f52a71-f0a5-4947-9702-e63e0802564a))
								  collapsed:: true
									- ## ((66f52a7d-db68-49bc-8821-5116d36839c5))
										- By the end of this module, you will be able to: e Explore the authentication process using Amazon Cognito« Manage user access and authorize serverless APIs¢ Observe best practices for implementing Amazon Cognito« Demonstrate the integration of Amazon Cognito and review the JWT token
									- ## ((66f52a95-53c1-4b42-aac7-83f6386bd190))
										- ((66f52aa0-8728-4d42-9fb5-4e5d7cdea1b0))
										- ((66f52aab-f6a5-4c37-8d99-e90dbb8b6202))
											- Framework - SAML, OAuth, OIDC, JWT
										- ((66f52ad1-c49f-4883-9718-b2cb0571bc9d))
											- ((6463499e-3bb4-49ea-90d5-2df420c0fb1e)) can handle this all for you
									- ## ((66f52ae9-de5f-43ce-96ed-f94a65f3ef15))
										- ((66f52af4-68f0-47c3-a279-43edcaf6ca1c))
											- Provides authentication, authorization, and user management for your web and mobile apps
											- Basically a log-in for your service
										- ((66f52b65-a0d5-4c16-bad8-3c5c6f18a33d))
											- User pool - authentication. It's basically a directory of all users with attributes fo them. To verify they are who they say they are
											- Identity pool - authorisation. Grant them access to specific AWS services
										- ((66f52e05-c17c-4fdd-ab1e-334d52662285))
										- ((66f52e19-a9e8-4603-b55a-efff481433a8))
									- ## ((66f52e22-f987-4af3-9bc6-26da2f3ccafc))
										- ((66f52e31-681e-4891-8037-6c0ca1f31ac2))
										- ((66f52e3a-4a74-4cc5-93ff-a185f02f9747))
									- ## ((66f52e42-dae0-4d24-be17-5a5120c81736))
										- ((66f52e4f-a142-4afb-bb8f-10929504f8ff))
										- ((66f52e58-9671-4092-a7b4-431b7e6ad84b))
										- ((66f52e61-3628-4167-880b-9bd9694014fb))
									- ## ((66f52e6a-9a49-4588-b6d6-298a6c2c1520))
										- ((66f52e77-d75e-43e5-a628-f703bcf44a88))
									- ## ((66f52e7f-797c-48b9-a6ef-811f1df7c29f))
										- ((66f52e8b-c2ca-4047-b2db-a7ac6ea5c12f))
										- ((66f52e9a-4acb-4173-9b12-b0908c7604be))
											- ((6457bcad-7919-46a4-a9c0-8bb0ddf40189)) authoriser can be used alternatively
											- Token-based
											- Request is parameter-based
									- ## ((66f52f2b-956f-4d3a-a5ff-6fd7126d0215))
										- Amazon Cognito user pools exchange authentication tokens for AWS credentials.
										  logseq.order-list-type:: number
											- **False**
											  logseq.order-list-type:: number
												- Amazon Cognito identity pools exchange authentication tokens for AWS credentials
												  logseq.order-list-type:: number
										- User and identity pools can be used together for authentication and authorization solutions.
										  logseq.order-list-type:: number
											- **True**
											  logseq.order-list-type:: number
										- To define the permissions for members of a group, you can assign an AWS Identity and Access Management (IAM) role to an Amazon Cognito group.
										  logseq.order-list-type:: number
											- **True**
											  logseq.order-list-type:: number
										- The JSON Web Token (JWT) payload section contains encoded information about the claim of the key.
										  logseq.order-list-type:: number
											- **True**
											  logseq.order-list-type:: number
										- When using third-party federation, developers must use identity pools.
										  logseq.order-list-type:: number
											- **False**
											  logseq.order-list-type:: number
												- Third-party federation is supported for both user pools and identity pools.
												  logseq.order-list-type:: number
										- Amazon Cognito identity pools can provide AWS credentials for unauthenticated users.
										  logseq.order-list-type:: number
											- **True**
											  logseq.order-list-type:: number
									- ((66f530b8-204c-4c66-b9d7-f4de1f1eb9f5))
										- OAuth2
										- OIDC
										- JWT
								- # ((66f530cf-bc4a-4be2-a430-92fa470c3f25))
								  collapsed:: true
									- ## ((66f54e3f-0afb-42f3-abdd-57108c95e33f))
										- By the end of this module, you will be able to:
											- Identify risks associated with traditional software development practices
											- Describe how DevOps addresses risks associated with traditional software development practices
											- Configure an AWS Serverless Application Model (AWS SAM) template to deploy a serverless application
											- Describe various AWS SAM deployment strategie
									- ## ((66f54e6b-aa2c-43b6-a987-78ced85e49d3))
										- ((66f54e75-40d1-41aa-9a6b-d50b24f49edc))
										- ((66f54e7e-2675-4954-aa87-f67273b77ab2))
										- ((66f54e86-e0b7-4311-9a78-ccc66432c677))
											- ((63904f39-e11b-4b28-9065-ce6396f67c4c))
											- ((63904f39-62e0-44d6-bd61-d5a6e98444a4))
											- Microservices
											- ((66cd757f-4ffc-4688-beb0-f0f2c2b603ea))
											- Monitoring and logging
											- Communication and collaboration
										- ((66f54e9f-ac4a-4fb7-bc95-2fda1757caaa))
											- ((64b7f676-aaa5-4351-aeee-dcc14b014bae))
											- ((64b7f66c-86f0-443a-b53b-190d004e78e7))
											- ((64b7f64c-8e70-4bf4-8680-2795cb1cc84f))
											- ((64b7f692-54e9-4bcf-95f9-301d3c298b1d))
											- ((64b7f69c-6359-41e8-ae5d-bccf8b1f1a4d))
											- ((64b7f629-76b1-4695-9eec-3caea77b1452))
											- ((663a5791-4799-4f97-a5f2-d2f5a78506c8))
											- ((6463499e-dc33-4af7-bbb7-33338a8a325b))
											- ((6463499e-5ffa-47d2-aeb5-b9a8bce9bc64))
											- ((64b7f73d-a5c9-4ec8-895e-ef8e5ab585d9))
											- etc
									- ## ((66f55054-8723-49c9-ae80-f2f3e5326bc1))
										- ((6620d4c0-1c5f-4f16-bfee-cf33e7cf5ffd))
										- ((66f5505f-c5ee-4015-a7d0-1df669cef976))
										- ((66f55068-ad9f-4e7f-9f15-d3a78e7d5e7e))
										- ((66f55077-15ee-4138-ac84-1824c1771344))
										- ((66f55080-fec8-40fb-aaad-4c1972d90d68))
										- ((66f5508e-f1aa-4c91-a68f-a2cee3c97d0b))
											- SAM resources map to AWS services:
												- Serverless API = ((6529032b-bb04-4660-836b-f33e1ae727ba))
												- Serverless Function = ((6457bcad-7919-46a4-a9c0-8bb0ddf40189))
												- Serverless SimpleTable = ((6463499e-971f-49ad-9136-306a4377fe86))
												- Serverless StateMachine = ((64b7c5ea-fc23-4c8f-bba3-40309679cf7d))
									- ## ((66f55097-9838-4292-bb78-df45c6fde53e))
										- ((66f550a4-c25d-49e2-8073-31abc838ad91))
											- Docker is optional, depends if you want to test the app locally
										- ((66f550ae-ec6c-43dd-bcc0-c211ba1be395))
											- `sam local invoke`
											- `sam local start-api`
											- `sam local generate-event`
										- ((66f550b8-84c5-46e6-b04d-e703c55acfd1))
									- ## ((66f5539e-eeed-4826-a9f3-20e2d7446017))
										- ((66f553ac-6d17-426e-8eef-58af22d23603))
											- Canary
											- Linear
											- All-at-once
										- ((66f5556f-f124-41a7-8a02-57b3c63e68a3))
									- ## ((66f555a3-cf08-4386-88cc-66a0fde927c6))
										- Human error is one of the risks of traditional software deployments.
										  logseq.order-list-type:: number
											- (True) When some deployment processes are manual, the possibility of human error exists. 
											  logseq.order-list-type:: number
										- Infrastructure as code is an important DevOps practice.
										  logseq.order-list-type:: number
											- (True) Infrastructure should be defined in code and tr software.
											  logseq.order-list-type:: number
										- AWS CodePipeline can orchestrate AWS CodeCommit, AWS CodeBuild, and AWS CodeDeploy.
										  logseq.order-list-type:: number
											- (True) AWS CodePipeline integrates with the other Code* services to facilitate automated pipelines.
											  logseq.order-list-type:: number
										- AWS SAM templates are an extension of AWS CloudFormation templates.
										  logseq.order-list-type:: number
											- (True) AWS SAM transforms its templates into AWS CloudFormation templates, which are then processed.
											  logseq.order-list-type:: number
										- You can use AWS SAM to build a serverless application only if it is written in Node.js, Java, Python,
										  logseq.order-list-type:: number
										  or Go.
											- (False) You can use any runtime supported by A mbda. There are a variety AWS Toolkits that work with different combinations of IDEs and runtimes to build and debug your code locally.
											  logseq.order-list-type:: number
										- The sam build command initializes a new AWS SAM project with required parameters.
										  logseq.order-list-type:: number
											- (False) The sam init command initializes a new AWS SAM project with required parameters.
											  logseq.order-list-type:: number
								- # ((66f54fe8-6c33-480d-96f2-1cf2e39585d3))
								  collapsed:: true
									- ## ((66f55b8f-c3d2-4cf2-8c5d-c783280f34a4))
										- By the end of this module, you will be able to:
											- Differentiate between monitoring and observability
											- Evaluate why observability is necessary in modern development and key components
											- Understand Amazon CloudWatch's part in configuring the observability
											- Demonstrate using CloudWatch Application Insights to monitor applications
											- Demonstrate using AWS X-Ray to debug your applications
									- ## ((66f55bc1-fc5b-458a-83de-c97015ea7cd0))
										- ((66f55bcf-8956-48bc-9c8b-d459773dc8c1))
											- The ability to observe, understand and use data
											- Collect
											- Monitor
											- Act
											- Analyse
										- ((66f55c51-3a7e-477e-83fd-e5c5d811d467))
											- It's more than just uptime monitoring
												- Visibility into your application
												- Real-time troubleshooting
												- Customer experience
												- Performance = revenue
										- ((66f55c8a-e483-4cd7-b983-aa212c19d4fd))
										- ((66f55c94-e236-4269-ab7c-84664c3514fc))
											- Logging
												- ((64aff99c-1c8f-4bdd-971d-3b34066116e4)) to centralise logs from everywhere
											- Metrics
												- ((6463499e-5ffa-47d2-aeb5-b9a8bce9bc64)) metrics can load all metrics
											- Tracing
												- ((64b7f73d-a5c9-4ec8-895e-ef8e5ab585d9)) can help you understand your app performance
									- ## ((66f55cf2-8186-4bb8-b396-6a073ae9a349))
										- ((66f55d38-24f1-4d4c-bc73-f1a29aa4482e))
										- ((66f55d43-d655-42ad-b14d-3d0e1af648ab))
											- Memory utilisation is a custom metric as it's hypervisor level. Need to use CloudWatch agent and a custom script for example to push the data to ((6463499e-5ffa-47d2-aeb5-b9a8bce9bc64))
										- ((66f55dbb-e8c8-4427-84b8-44e41d7b44df))
											- Metrics
											- Dimensions
												- Name/value pair that is part of the identity of a metri
											- Alarms
											- Logs
										- ((66f55de1-b464-41e4-9d4b-1046379388fe))
										- ((66f55ef4-8b17-4aba-8873-de40565b42cd))
										- ((66f55f03-8967-4556-adee-630550926d0d))
										- ((66f55f14-dc36-4a6a-8b97-0596b63adc17))
										- ((66f55f21-77c6-4fbb-a95e-091694872fa3))
										- ((66f55f2c-151c-4a1c-9b74-bfd7d210d9f0))
										- ((66f55f3b-8e3b-4880-9fae-31116f5f0463))
									- ## ((66f55f46-a746-4d1f-9896-b2b9b29ef380))
										- ((66f55f55-7a95-4e0b-8e7f-12a106abf4ec))
										- ((66f55f5f-7de5-4e01-a66b-76591a2e5080))
										- ((66f55f98-7714-435f-b641-65033acdeb2b))
										- ((66f55fba-06d3-4b04-a456-f36ce1da9674))
									- ## ((66f55fc9-d7c7-448e-8e0e-6140b67c2520))
										- ((66f56021-f780-428e-9f70-dbeaed9b3b55))
										- ((66f5603d-afb5-4806-a9ca-b45916207b83))
										- ((66f56048-8841-4022-bd23-f6905b5ba6b9))
									- ## ((66f5605c-4dbc-491e-8a2b-f9e86fa4569f))
										- Use CloudWatch Logs to centralise the logs from all of your systems, applications, and AWS services.
										  logseq.order-list-type:: number
											- (True)
											  logseq.order-list-type:: number
										- The three pillars of observability includes logs, traces, and availability.
										  logseq.order-list-type:: number
											- (False) Three pillars of observability includes metrics, trates; and logs.
											  logseq.order-list-type:: number
										- A trace only displays a single subsegment generated by a request.
										  logseq.order-list-type:: number
											- (False) A trace collects all the segments generated by a single request.
											  logseq.order-list-type:: number
										- Traces are a numerical representation of data used to analyse the overall performance and behaviour of a system
										  logseq.order-list-type:: number
											- (False) Metrics, not traces, are a numerical representation of data used to analyze the overall performance and behavior of a system.
											  logseq.order-list-type:: number
										- An alarm watches a single metric over a specified time period, and performs one or more specified actions, based on the value of the metric relative to a threshold over time.
										  logseq.order-list-type:: number
											- (True)
											  logseq.order-list-type:: number
										- Subsegments provide more granular timing information and details about downstream calls that your
										  logseq.order-list-type:: number
										  application made to fulfil the original request.
											- (True)
											  logseq.order-list-type:: number
								- # ((66f5306f-7f24-4215-8db3-49662dc58fd2))
								  collapsed:: true
									- ((66f5308a-a764-41d6-8081-8d1a8f88995a))
									- ((66f53099-a951-4e06-801a-f12f8996e269))
									- ## Overview
									  collapsed:: true
										- You have all of the components created for your application and have learned how to allow access to them from the web. Before adding any more API methods for the remaining functions you need to be able to secure access. In this lab, you will learn how to set up Amazon Cognito to authenticate and authorize users to use your API. With that in place, you will then configure the front-end web application to complete your fully functional application.
										- ![image.png](../assets/image_1727345009885_0.png)
									- ### Objectives
									  collapsed:: true
										- After completing this lab, you will be able to:
											- Create a user pool and an app client for your web application using Amazon Cognito.
											- Add new users and confirm their ability to sign-in using the Amazon Cognito CLI.
											- Configure API Gateway methods to use Amazon Cognito as an authorizer.
											- Verify JWT authentication tokens are generated during API calls.
											- Develop API Gateway resources rapidly using Swagger importing strategy.
											- Set up your web application frontend to use Amazon Cognito and API Gateway configurations and verify the entire application functionality.
									- ## Task 1: Configure Amazon Cognito
									  collapsed:: true
										- **High-Level Instructions**
											- Create an Amazon Cognito user pool named `PollyNotesPool` with only a username attribute and minimal password requirements for testing purpose.
											- Create an Amazon Cognito application client for your application without a secret key.
											- In the AWS Cloud9 terminal, add a new user named `student` and approve it in the user pool using the cognito-idp CLI commands sign-up and admin-confirm-sign-up.
											- Test authentication using the URL from the **testLoginWebsite** output to the left of these instructions.
											- Review JWT token created by your application using .getIdToken().getJwtToken() methods.
										- ### Task 1.1: Create an Amazon Cognito user pool with an app client
										  collapsed:: true
											- Password policy - custom, 6 length
											- Password requirements - unselect all, temporary passwords set by admins expire in `7` days
											- No MFA
											- Uncheck `Enable self-service account recovery`
											- `Next`
											- Check `Enable self-registration`
											- Uncheck `Allow Cognito to automatically send messages to verify and confirm`
											- `Next`
											- Configure message delivery: `Send email with Cognito`
											- `Next`
											- User pool name: `PollyNotesPool`
											- Uncheck `Use the Cognito Hosted UI`
											- Initial app client:
												- App type: `Public client`
												- App client name: `PollyNotesWeb`
												- Client secret: `Don’t generate a client secret`
											- `Next` > `Create user pool`
										- ### Task 1.2: Add a new user to the user pool
											- Open ((64b7f629-76b1-4695-9eec-3caea77b1452))
												- In the terminal add 3 variables
													- `apiURL='[apiURL]'`
														- `apiURL='https://kxw57htlzk.execute-api.us-east-1.amazonaws.com/Prod'`
													- `CognitoPoolId='[User Pool Id]'`
														- `CognitoPoolId='us-east-1_p4SuBrADh'`
														- See Cognito page for this ID
													- `AppClientId='[App Client Id]'`
														- `AppClientId='7qf2qfjq20hq5uesa8qubdg6be'`
														- On the Cognito user pool page > App integration tab > App client list section > should show the `Client ID`
												- Create a new Amazon Cognito user named **student** with the command below
													- `aws cognito-idp sign-up --client-id $AppClientId --username student --password student`
												- Confirm that user's sign-up
													- `aws cognito-idp admin-confirm-sign-up --user-pool-id $CognitoPoolId --username student`
											- Open ((6463499e-3bb4-49ea-90d5-2df420c0fb1e)) again
												- Open your created user pool > Users tab should show this user with a Confirmed confirmation status
										- ### Task 1.3: Test the user authentication in a simple web page
											- Test application
												- A test login page has been created for you to confirm the Amazon Cognito user and pool.
												- To the left of these instructions, copy the testLoginWebsite value, open that URL in a new web browser tab.
												- This page, takes the values that you copied earlier and the username and password student. As an example of how the login process works, there is JavaScript code on the right, which uses the Amazon Cognito JavaScript SDK. As you enter values in the login form, you will see where those values are used in this sample code.
											- Enter, the User Pool Id and App Client Id in the first two input fields.
												- Note: This information is used to create the poolData variable.
											- Enter `student` in both the Username and Password input fields. > `Login`
											- Using the **.getIdToken().getJwtToken()** methods on the return of successful authentication, a **JSON Web Token** or **JwtToken** is retrieved. JSON Web Tokens are an open, industry standard RFC 7519 method for representing claims securely between two parties.  You can decode the token at [JWT.IO](https://jwt.io) if you would like to verify the claim.
									- ## Task 2: Configure Amazon API Gateway to use Amazon Cognito as an authorizer
									  collapsed:: true
										- **High-Level Instructions**
											- Create an Amazon API Gateway authorizer `PollyNotesPool` for your existing API **PollyNotesAPI** that expects `Authorization` as the token source
											- Configure the existing **/notes** GET AND POST methods to use the new Authorizer
											- Update the mapping templates to transform the request using the Amazon Cognito username (`"$context.authorizer.claims['cognito:username']"`) as the UserId
										- ### Task 2.1: Create an Amazon API Gateway authorizer for the PollyNotesAPI using the console
											- Open ((6529032b-bb04-4660-836b-f33e1ae727ba)) > open the API I made earlier > select `Authorizers` in the sidebar > Create authorizer
												- **Authorizer Name**: `PollyNotesPool`
												- **Type**: `Cognito`
												- **Cognito User Pool**: `PollyNotesPool`
												- **Token source**: `Authorization`
												- **Token Validation**: Leave empty
											- Click the authorizer > Test authorizer > paste the authorisation token from task 1 web app
												- The Response contains the claim information that was returned from Amazon Cognito that you can use in your application. You will be using the cognito:username value (`"student"`) in future steps.
										- ### Task 2.2: Configure the existing methods to use the new Authorizer
											- The next few procedures walk you through the steps to secure the two existing API methods with the authorizer. You will also replace the static UserId mapping template with dynamic information from the authorization claim.
											- Go to Resources > GET
												- Method Request tab > Edit
													- For **Authorization**, choose **PollyNotesPool** under **Cognito user pool authorizers**
													- `Save`
												- Integration request tab > Edit
													- Mapping tenplates section
													- Template body
														- ```json
														  {
														      "UserId": "$context.authorizer.claims['cognito:username']"
														  }
														  ```
													- `Save`
											- Add the authorizer to the POST method as well. Go to Resources > POST
												- Integration request tab > Edit > Mapping template section
												- Change the mapping template to pull dynamically from the request. Notice that the NoteId and note is also passed to the Lambda function for this method.
												- Template body
													- ```json
													  {
													      "UserId": "$context.authorizer.claims['cognito:username']",
													      "NoteId": $input.json('$.NoteId'),
													      "Note": $input.json('$.Note')
													  }
													  ```
												- `Save`
										- The API is now secured. You will deploy this configuration in the next task.
									- ## Task 3: Create the remaining API resources using a Swagger file
										- Intro
											- In this task, you will create all the remaining resources and methods for the application. Your Lambda functions were already created in previous labs and the code will not need to be modified.
											- API gateway allows you to use the Swagger specification to export and import configuration information. This is a much quicker method than using the AWS Management Console.
										- **High-Level Instructions**
											- Review the Swagger file. `~/environment/api/PollyNotesAPI-swagger.yaml` It includes all the remaining API resource definitions needed for your application
											- Replace the placeholders in the Swagger file to customize it for your lab
											- Merge the Swagger file to create Amazon API Gateway resources
											- Update the AWS Lambda function permissions for the newly created API resources
											- Verify that the resources imported are correct using the Amazon API Gateway console
										- ### Task 3.1: Customize the Swagger file for your lab
											- ((663b2925-dac6-4051-ba45-c1bd7069907e)) file full code (pre-script)
											  collapsed:: true
												- ```yaml
												  ---
												  securityDefinitions:
												    PollyNotesPool:
												      type: "apiKey"
												      name: "Authorization"
												      in: "header"
												      x-amazon-apigateway-authtype: "cognito_user_pools"
												      x-amazon-apigateway-authorizer:
												        type: "cognito_user_pools"
												        providerARNs:
												        - "[Cognito_Pool_ARN]"
												  swagger: "2.0"
												  info:
												    title: "PollyNotesAPI"
												  basePath: "/Prod"
												  schemes:
												  - "https"
												  paths:
												    /notes/search:
												      get:
												        consumes:
												        - "application/json"
												        produces:
												        - "application/json"
												        parameters:
												        - name: "text"
												          in: "query"
												          required: true
												          type: "string"
												        responses:
												          "200":
												            description: "200 response"
												            schema:
												              $ref: "#/definitions/Empty"
												            headers:
												              Access-Control-Allow-Origin:
												                type: "string"
												              Access-Control-Allow-Methods:
												                type: "string"
												              Access-Control-Allow-Headers:
												                type: "string"
												        security:
												        - PollyNotesPool: []
												        x-amazon-apigateway-integration:
												          httpMethod: "POST"
												          uri: "arn:aws:apigateway:[AWS_Region]:lambda:path/2015-03-31/functions/arn:aws:lambda:[AWS_Region]:[AWS_AccountId]:function:search-function/invocations"
												          responses:
												            default:
												              statusCode: "200"
												              responseParameters:
												                method.response.header.Access-Control-Allow-Methods: "'*'"
												                method.response.header.Access-Control-Allow-Headers: "'*'"
												                method.response.header.Access-Control-Allow-Origin: "'*'"
												              responseTemplates:
												                application/json: "#set($inputRoot = $input.path('$'))\n[\n#foreach($elem\
												                  \ in $inputRoot)\n {\n  \"NoteId\" : \"$elem.NoteId\",\n  \"Note\"\
												                  \ : \"$elem.Note\"\n} \n#if($foreach.hasNext),#end\n#end\n]"
												          requestTemplates:
												            application/json: "{\n    \"UserId\": \"$context.authorizer.claims['cognito:username']\"\
												              ,\n    \"text\": \"$input.params('text')\"\n}"
												          passthroughBehavior: "when_no_templates"
												          contentHandling: "CONVERT_TO_TEXT"
												          type: "aws"
												      options:
												        consumes:
												        - "application/json"
												        produces:
												        - "application/json"
												        responses:
												          "200":
												            description: "200 response"
												            schema:
												              $ref: "#/definitions/Empty"
												            headers:
												              Access-Control-Allow-Origin:
												                type: "string"
												              Access-Control-Allow-Methods:
												                type: "string"
												              Access-Control-Allow-Headers:
												                type: "string"
												        x-amazon-apigateway-integration:
												          responses:
												            default:
												              statusCode: "200"
												              responseParameters:
												                method.response.header.Access-Control-Allow-Methods: "'GET,OPTIONS'"
												                method.response.header.Access-Control-Allow-Headers: "'*'"
												                method.response.header.Access-Control-Allow-Origin: "'*'"
												          requestTemplates:
												            application/json: "{\"statusCode\": 200}"
												          passthroughBehavior: "when_no_match"
												          type: "mock"
												    /notes/{id}:
												      post:
												        consumes:
												        - "application/json"
												        produces:
												        - "application/json"
												        parameters:
												        - name: "id"
												          in: "path"
												          required: true
												          type: "string"
												        responses:
												          "200":
												            description: "200 response"
												            schema:
												              $ref: "#/definitions/Empty"
												            headers:
												              Access-Control-Allow-Origin:
												                type: "string"
												              Access-Control-Allow-Methods:
												                type: "string"
												              Access-Control-Allow-Headers:
												                type: "string"
												        security:
												        - PollyNotesPool: []
												        x-amazon-apigateway-integration:
												          httpMethod: "POST"
												          uri: "arn:aws:apigateway:[AWS_Region]:lambda:path/2015-03-31/functions/arn:aws:lambda:[AWS_Region]:[AWS_AccountId]:function:dictate-function/invocations"
												          responses:
												            default:
												              statusCode: "200"
												              responseParameters:
												                method.response.header.Access-Control-Allow-Methods: "'*'"
												                method.response.header.Access-Control-Allow-Headers: "'*'"
												                method.response.header.Access-Control-Allow-Origin: "'*'"
												          requestTemplates:
												            application/json: "{\n    \"VoiceId\": $input.json('$.VoiceId'),\n    \"\
												              UserId\": \"$context.authorizer.claims['cognito:username']\",\n    \"\
												              NoteId\": \"$input.params('id')\"\n}"
												          passthroughBehavior: "when_no_templates"
												          contentHandling: "CONVERT_TO_TEXT"
												          type: "aws"
												      delete:
												        consumes:
												        - "application/json"
												        produces:
												        - "application/json"
												        parameters:
												        - name: "id"
												          in: "path"
												          required: true
												          type: "string"
												        responses:
												          "200":
												            description: "200 response"
												            schema:
												              $ref: "#/definitions/Empty"
												            headers:
												              Access-Control-Allow-Origin:
												                type: "string"
												              Access-Control-Allow-Methods:
												                type: "string"
												              Access-Control-Allow-Headers:
												                type: "string"
												        security:
												        - PollyNotesPool: []
												        x-amazon-apigateway-integration:
												          httpMethod: "POST"
												          uri: "arn:aws:apigateway:[AWS_Region]:lambda:path/2015-03-31/functions/arn:aws:lambda:[AWS_Region]:[AWS_AccountId]:function:delete-function/invocations"
												          responses:
												            default:
												              statusCode: "200"
												              responseParameters:
												                method.response.header.Access-Control-Allow-Methods: "'*'"
												                method.response.header.Access-Control-Allow-Headers: "'*'"
												                method.response.header.Access-Control-Allow-Origin: "'*'"
												          requestTemplates:
												            application/json: "{\n    \"UserId\": \"$context.authorizer.claims['cognito:username']\"\
												              ,\n    \"NoteId\": \"$input.params('id')\"\n}"
												          passthroughBehavior: "when_no_templates"
												          contentHandling: "CONVERT_TO_TEXT"
												          type: "aws"
												      options:
												        consumes:
												        - "application/json"
												        produces:
												        - "application/json"
												        responses:
												          "200":
												            description: "200 response"
												            schema:
												              $ref: "#/definitions/Empty"
												            headers:
												              Access-Control-Allow-Origin:
												                type: "string"
												              Access-Control-Allow-Methods:
												                type: "string"
												              Access-Control-Allow-Headers:
												                type: "string"
												        x-amazon-apigateway-integration:
												          responses:
												            default:
												              statusCode: "200"
												              responseParameters:
												                method.response.header.Access-Control-Allow-Methods: "'DELETE,OPTIONS,POST'"
												                method.response.header.Access-Control-Allow-Headers: "'*'"
												                method.response.header.Access-Control-Allow-Origin: "'*'"
												          requestTemplates:
												            application/json: "{\"statusCode\": 200}"
												          passthroughBehavior: "when_no_match"
												          type: "mock"
												  definitions:
												    Empty:
												      type: "object"
												      title: "Empty Schema"
												  x-amazon-apigateway-gateway-responses:
												    DEFAULT_4XX:
												      responseParameters:
												        gatewayresponse.header.Access-Control-Allow-Methods: "'GET,OPTIONS'"
												        gatewayresponse.header.Access-Control-Allow-Origin: "'*'"
												        gatewayresponse.header.Access-Control-Allow-Headers: "'*'"
												    DEFAULT_5XX:
												      responseParameters:
												        gatewayresponse.header.Access-Control-Allow-Methods: "'GET,OPTIONS'"
												        gatewayresponse.header.Access-Control-Allow-Origin: "'*'"
												        gatewayresponse.header.Access-Control-Allow-Headers: "'*'"
												  ```
											- In ((64b7f629-76b1-4695-9eec-3caea77b1452)) terminal use these commands to replace the variables for your lab
												- ```bash
												  region=$(curl http://169.254.169.254/latest/meta-data/placement/region -s)
												  
												  acct=$(aws sts get-caller-identity --output text --query "Account")
												  
												  poolId=$(aws cognito-idp list-user-pools --max-results 1 --output text --query "UserPools[].Id")
												  
												  poolArn="arn:aws:cognito-idp:$region:$acct:userpool/$poolId"
												  ```
											- Run the commands below to update the swagger file place holders with the variables you just created
												- ```bash
												  sed -i "s~\[Cognito_Pool_ARN\]~$poolArn~g" ~/environment/api/PollyNotesAPI-swagger.yaml
												  
												  sed -i "s~\[AWS_Region\]~$region~g" ~/environment/api/PollyNotesAPI-swagger.yaml
												  
												  sed -i "s~\[AWS_AccountId\]~$acct~g" ~/environment/api/PollyNotesAPI-swagger.yaml
												  ```
										- ### Task 3.2: Merge the Swagger file to the existing API
									- ## Task 4: Configure the frontend web application
										- Intro
											- Now that the API has been configured and secured, you can deploy the web front end. This web application is serverless and hosted on Amazon S3. All processing is performed by the client’s web browser. The framework that it was written in requires you to build the application to optimize it for web distribution. Before you build and deploy, you need to customize the configuration to use your API.
										- **High-Level Instructions**
											- Update your application `web/src/Config.js` file to refer to the Amazon Cognito user pool and API.
											- Build the web application and download dependencies with npm.
											- Update the Amazon S3 website bucket with the latest application files.
											- **Command:** Run the command below to create a bucket variable. Be sure to replace *WEBBUCKETNAME* with the **WebBucketName** value from the left side of the lab page: `webBucket=WEBBUCKETNAME`
										- ### Task 4.1: Configure the web application for your lab
									- ## Task 5: Test the web application functionality
										-
								- ## Sample exam questions
								  collapsed:: true
								  See skillbuilder.aws - search `developer questions`
									- A company notices performance degradation in one of its production web applications. The application is running on AWS services and uses a microservices architecture. The company suspects that one of these microservices is causing the performance issue.
									  Which AWS solution should the company use to identify the service that is contributing to higher application latency?
										- Correct
											- A) AWS X-Ray service map
										- Incorrect
											- B) AWS CloudTrail event history
											- C) Amazon EventBridge events
											- D) AWS Trusted Advisor performance report
									- A developer needs to query a relational database from an AWS Lambda function. The Lambda function will be called frequently. The developer needs to avoid the latency introduced by the initial JDBC connection to the database in subsequent invocations of the Lambda function.
									  How can the developer ensure the database connection is reused by Lambda?
										- Correct
											- B) Initialize the database connection within the Lambda function code but outside the handler method.
										- Incorrect
											- A) Initialize the database connection outside the Lambda function code as a Lambda function environment variable.
											- C) Store the database connection string in AWS Systems Manager Parameter Store. Ensure the Lambda function handler initializes the database connection within the handler method.
											- D) Store the database connection string in the Lambda function code. Ensure the function handler initializes the database connection within the handler method.
									- ![image.png](../assets/image_1727360098355_0.png)
									- A developer tests code running on the developer's laptop. The code is using the AWS SDK for Python (Boto3) to access AWS services. The .aws/credentials file is set up with the user's IAM user name and password. The developer runs the code and receives this error message:
									  An error occurred (InvalidAccessKeyId)
									  Which action will resolve this error?
										- Correct
											- D) Replace the IAM user name and password with an access key ID and a secret access key
										- Incorrect
											- A) Move the IAM user name and password to the .aws/config file.
											- B) Place the Amazon Resource Name (ARN) of a valid IAM role in the AWS_PROFILE environment variable.
											- C) Move the user name and password to environment variables.
									- #+BEGIN_TIP
									  There are discount offers for the exam if you can't get sponsored by your company
									  #+END_TIP
								- # ((66f55003-2776-43ec-9764-1063f494de1c))
								- # ((66f55015-f963-4041-a810-f0259dd4f5d9))
								- [Learning Resources]
									- [AWS Power Hour: Associate Certification](https://pages.awscloud.com/GLOBAL-Traincert-other-LS-AWS-Power-Hour-Associate-Certification-2023-reg.html)
									- [Self-paced digital training on AWS - AWS Skill Builder](https://explore.skillbuilder.aws/learn/course/13757/play/121171/aws-certified-developer-associate-official-practice-question-set-dva-c02-english-v2)
									- https://aws.amazon.com/certification/certified-developer-associate/
									- FAQs on product pages e.g. [Amazon DynamoDB FAQs](https://aws.amazon.com/dynamodb/faqs/)
									-
						- [AWS Certified Developer - Associate (DVA-C02) | Pluralsight](https://app.pluralsight.com/library/courses/aws-certified-developer---associate-dva-c01/table-of-contents)
						  collapsed:: true
							- # Introduction
								- DVA-C02 exam info
									- 130 minutes long
									- 65 questions
									- $150
									- Qualification valid for 3 years
									- Exam domains
										- 32% 1) Development with AWS
										  collapsed:: true
											- Task Statement 1: Develop code for applications hosted on AWS.
												- Knowledge of:
													- • Architectural patterns (for example, event-driven, microservices, monolithic,
													- choreography, orchestration, fanout)
													- • Idempotency
													- • Differences between stateful and stateless concepts
													- • Differences between tightly coupled and loosely coupled components
													- • Fault-tolerant design patterns (for example, retries with exponential
													- backoff and jitter, dead-letter queues)
													- • Differences between synchronous and asynchronous patterns
												- Skills in:
													- • Creating fault-tolerant and resilient applications in a programming
													- language (for example, Java, C#, Python, JavaScript, TypeScript, Go)
													- • Creating, extending, and maintaining APIs (for example, response/request
													- transformations, enforcing validation rules, overriding status codes)
													- • Writing and running unit tests in development environments (for example,
													- using ((6620d4c0-1c5f-4f16-bfee-cf33e7cf5ffd))
													  id:: 65d89c1b-c922-4c8d-8c3f-c9e9d1947fa6
													- • Writing code to use messaging services
													- • Writing code that interacts with AWS services by using APIs and AWS SDKs
													- • Handling data streaming by using AWS services
										- 26% 2) Security
										- 24% 3) Deployment
										- 18% 4) Troubleshooting and Optimisation
								- https://d1.awsstatic.com/training-and-certification/docs-dev-associate/AWS-Certified-Developer-Associate_Exam-Guide.pdf
									-
							- # Beginner's Guide to IAM
							- # Beginner's Guide to EC2
							- # S3
							- # Introduction to Serverless Computing
							- # DynamoDB
							- # KMS and Encryption on AWS
							- # Other AWS Services
							- # Developer Theory
							- # Advanced ((64b81154-09ce-46c2-993a-0451497bcf3c))
							- # Monitoring
						- Webinars
							- Meta
								- Program Guide pdf
								  ![Program Guide_APCR_DEV_EMEA.pdf](../assets/Program_Guide_APCR_DEV_EMEA_1710669138482_0.pdf)
							- Session 1 - Kickoff
							  collapsed:: true
								- Resources
									- APN Logon: https://partnercentral.awspartner.com/partnercentral2/s/SelfRegister
									- Skill Builder Logon: https://explore.skillbuilder.aws/learn/signin
									- Certifications Logon: https://www.aws.training/certification
									- https://partners.awscloud.com/EMEA-Tech-Talks-2023.html
								- Exam info
									- 130m long, 65 questions (50 scored)
									- 72% to pass
									- No negative points - so pick something always
									- $150
									- You can flag your questions to easily review them at the end of the test and change your answers
								- Exam contents
									- ((6529032b-bb04-4660-836b-f33e1ae727ba)) is commonly used with ((6457bcad-7919-46a4-a9c0-8bb0ddf40189)), good thing to practice together
									- https://serverlessland.com is a good resource
										- Example Code > Patterns > see examples of how you can combine different services together
							- [[2024-03-11 Monday]] Session 2
							  collapsed:: true
								- 5 practice questions
									- Q1) What combination of AWS services can be used so that customers can make HTTP API calls, serverless compute containing the business logic that processes the incoming API calls and corresponding microservices data can be persistently stored
										- Answers:
											- ((6529032b-bb04-4660-836b-f33e1ae727ba)) - so customers can make HTTP API calls
											- ((6457bcad-7919-46a4-a9c0-8bb0ddf40189)) - serverless compute containing the business logic that processes the incoming API calls
											- ((6463499e-971f-49ad-9136-306a4377fe86)) - corresponding microservices data can be persistently stored
										- Wrong: ((6463499d-63a1-485e-bf7e-1bae513fd542)) doesn't do any of these
									- Q2) Company wants to process large JSON, these need to be processed as soon as they arrive, there can be days between files being added or minutes
										- Answer:
											- ((6463499e-42ab-4a58-8911-df6138dfee8f)) to store files, ((6457bcad-7919-46a4-a9c0-8bb0ddf40189)) to process them
										- Wrong:
											- ((63a06e59-4078-4357-b478-dda42326daf4)) to store files isn't suitable because you don't need fast concurrent read/write, just need a simple store. Also there isn't EFS event triggers, so can't initiate ((6457bcad-7919-46a4-a9c0-8bb0ddf40189)) that way
									- Q3) How to communicate securely from ((6463499e-bd2d-4c48-b05b-bdddeb7d8bba)) to ((6463499e-42ab-4a58-8911-df6138dfee8f))
										- Answer:
											- ((6463499e-177d-4f57-a6c6-9c947d98a39a)) endpoint - allows communicating through the AWS network without public internet transfer
										- Wrong:
											- Internet Gateway - no because it goes over public internet
											- VPN connection - no it's excessive, you can just use a VPC since you're only communicating within AWS
											- NAT Gateway - no this allows communicating between a VPC and the public internet, something different. Private NAT Gateway has a cost, unlike VPC
									- Q4) About security groups between a 3-tier application: 1) a web app, 2) a RESTful API, 3) a SQL Server database
										- Answer:
											- webapp-sg: Allows ports 80 and 443 from 0.0.0.0/0 (anyone)
											- api-sg: Allow port 443 from webapp-sg
											- db-sg: Allow port 1433 from logic-sg (arbitrary port)
									- Q5) IAM policy: understanding conditions
										- Answer:
											- If you have multiple conditions it means all conditions must be met, not one or another
											- This means that the request be **initiated** from this VPC, not that the request uses a VPC endpoint in it
												- ```json
												  "Condition": {
												    "StringEquals": {
												      "aws:SourceVpc": "vpc-111bbb22"
												    }
												  }
												  ```
								- Demo
									- ((64b7f629-76b1-4695-9eec-3caea77b1452)) - looks like ((63209272-1088-4824-a762-4ac7ded04b0a)) cloud
									- ((63904f39-62e0-44d6-bd61-d5a6e98444a4)) : ((63a04cfd-4c07-4f11-be92-fa0f531c527b))
										- {{embed ((63a04cfd-4c07-4f11-be92-fa0f531c527b))}}
							- [[2024-03-18 Monday]] Session 3
							  collapsed:: true
								- 5 practice questions
									- 1) A developer configures ((64b7f692-54e9-4bcf-95f9-301d3c298b1d)) to install an app on ((6463499e-bd2d-4c48-b05b-bdddeb7d8bba)) instances in an ((649d9b65-1b7f-4e96-acae-91bcacd198d5)) group. Where should the developer place the appsec.yml file?
										- A) In the root directory structure of the application source code
										- Wrong answers
											- In the same ((6463499e-42ab-4a58-8911-df6138dfee8f)) bucket as the app source code bundle
											- Directly in the CodeDeploy console (this is instead relevant to ((6457bcad-7919-46a4-a9c0-8bb0ddf40189)) )
											- In the `.exextensions` folder in the app's source code (this is instead relevant to ((6463499d-63a1-485e-bf7e-1bae513fd542)) )
									- 2) A dev needs to query a relational DB from an ((6457bcad-7919-46a4-a9c0-8bb0ddf40189)). It will be called frequency, so the dev needs to avoid the latency introduced by the initial JDBC connection to the database in subsequent invocations of the ((6457bcad-7919-46a4-a9c0-8bb0ddf40189)). How can the dev ensure the db connection is reused by ((6457bcad-7919-46a4-a9c0-8bb0ddf40189))?
									  id:: 65f82fc5-d088-41c3-a1e3-57ead198db88
										- Answer:
											- Initialise the database connection with the Lambda function code but outside the handler method
												- Best practices in docs: "initialise SDK clients and dataase connections outside of the function handler and cache static assets locally in `/tmp` directory"
										- Wrong
											- Initialise the database connection outside the Lambda function as a Lambda function environment variable
												- Wrong because the dev still needs to initialise it even if it's stored as an env var
											- Store the db connection string in ((64b80795-b0df-423c-a9f6-0b4e1cc37ff5)) Store. Ensure the ((6457bcad-7919-46a4-a9c0-8bb0ddf40189)) handler initialises the databse connection with the handler method
											- Store the db connection string in the Lambda function code. Ensure the function handler iniitalises the database connection within the handler method
									- 3) A dev uses the AWS SDK for C++ to retrieve data from a ((6463499e-971f-49ad-9136-306a4377fe86)) table. The data is sometimes retrieved using a known key, and sometimes the key is not known, resulting in multiple items being returned. The dev wants to ensure the code only returns one item when retrieving data without keys. Which ((6463499e-971f-49ad-9136-306a4377fe86)) setting will meet these requirements?
										- Answer
											- Set the scan limit parameter to 1
										- Wrong
											- Set the parallel scan operation 1
												- This is for parallelising to speed up scans. It'll still reeturn the same amount
											- Set the query filter expression to 1
												- You'll filter the results but not define that 1 is the maximum number of results to return
											- Set the query page-size value to 1
												- This is for pagination - it'll just visibly reduce the number of results
									- 4) A company built a warehouse fulfillment application using ((64b7c5ea-fc23-4c8f-bba3-40309679cf7d)). ..The application must reassign interrupted activities to another worker as soon as possible. If an activity fails 3 times then the state machine should fail.
										- Answer
											- Set the task's `HeartbeatSeconds` attribute to 30 seconds. Set the `Retry.MaxAttempts` attribute to 3
										- Wrong
											- Set the state machine's `States.Timeout` attribute to 30 seconds. Set the state machine's `Retry.MaxAttempts` attribute to 3
												- `States.Timeout` is not assignable, this refers to an error code
											- Set the task's `HeartbeatSeconds` attribute to 30 seconds. Set the state machine's `States.TaskFailed` attribute to 3
												- The `States.TaskFailed` attribute is not settable, it's an error code
											- Set the task's `TimeoutSeconds` attribute to 30 seconds.  Set the state machine's `Retry.MaxAttempts` attribute to 3
												- Instead you want to check if the task is not running, if it isn't then try again
									- 5) An ecommerce company deploys more than 20 services behind ((6529032b-bb04-4660-836b-f33e1ae727ba)). There's complex interactions between them, how to identify why some API calls have slow response times. What's the quickest way to identifying the underlying cause of performance issues?
									  id:: 65f835cf-3690-4d30-a021-101ae3dace55
										- Answer
											- Configure and use ((64b7f73d-a5c9-4ec8-895e-ef8e5ab585d9)) to find the service invocations with slow response times. Use ((6463499e-5ffa-47d2-aeb5-b9a8bce9bc64)) metrics and logs to discover their performance issues
												- ((64b7f73d-a5c9-4ec8-895e-ef8e5ab585d9)) is built to quickly identify issues such as slowdowns so should be consulted first. ((6463499e-5ffa-47d2-aeb5-b9a8bce9bc64)) has the full logs so can be consulted after
										- Wrong answers
											- Use ((6463499e-5ffa-47d2-aeb5-b9a8bce9bc64)) metrics to find the service invocations with slow response times. Configure and use ((64b7f73d-a5c9-4ec8-895e-ef8e5ab585d9)) to examine these services to discover their performance issues
											- Use ((6463499e-5ffa-47d2-aeb5-b9a8bce9bc64)) Logs to find the service invocations with slow response times. Use ((6463499e-fe31-4613-8b61-e232816b6ddb)) to examine these services to discover their performance issues
											- Use ((6463499e-fe31-4613-8b61-e232816b6ddb)) to find the service invocations with slow response times. Configure and use ((64b7f73d-a5c9-4ec8-895e-ef8e5ab585d9)) to examine these services to discvoer their performance issues
								- ## Lab: Serverless Architectures using ((6463499e-5ffa-47d2-aeb5-b9a8bce9bc64)) Events and Scheduled Events with ((6457bcad-7919-46a4-a9c0-8bb0ddf40189))
									- ((6463499e-5ffa-47d2-aeb5-b9a8bce9bc64)) Events to react to the creation of an ((6463499e-bd2d-4c48-b05b-bdddeb7d8bba)) instance
							- ? Session 4
							  collapsed:: true
								- 5 practice questions
									- 1) A company notices performance degradation in their app and they want to analyse what microservices might be causing the issue of higher application latency
										- ((64b7f73d-a5c9-4ec8-895e-ef8e5ab585d9)) service map
										  Creates a map of services and includes trace data to see how each service connects to each other and where latency might be
										- Wrong answers
											- ((6463499e-fe31-4613-8b61-e232816b6ddb)) event history
												- Tracks API calls, not for application performance issues
											- ((64b7bc1b-9bf1-4590-a835-6f42a199d644)) events
												- Tells you about resource utilisation, but not latency
											- AWS Trusted Advisor performance report
												- Real-time advice, it's got a different usecase
									- 2) An application runs on EC2 instances behind an Application ((6463499e-9ecf-4800-bf1f-65704c310016)), managed by an ((649d9b65-1b7f-4e96-acae-91bcacd198d5)). App needs to be multi-device and seamlessly handle the state persisting across laptop, smartphones and tablets
										- Store session state infromation in an Amazon ElastiCache for Redis cluster
											- Stores data in one location no matter what device you use
										- Wrong answers
											- Implement sticky sessions at the Application Load Balancer
												- It means that your sessions will continue to use the same underlying EC2 instance, but this doesn't solve multi-diverse
											- Implement session state information storage in a local file on the webserver
												- This means if your load balancer sends you to a different underlying EC2 instance then that state data is no longer accessible
											- Store session state information in ((64b80795-b0df-423c-a9f6-0b4e1cc37ff5)) State Manager
												- Used to manage the state of an instance e.g. what version of a package it uses
									- 3) What combination of steps should a dev team take to configure ((6457bcad-7919-46a4-a9c0-8bb0ddf40189)) functions to meet requirements to regularly update the code and use stable code in production
										- Create a new Lambda version every time a new code release needs testing
										- Create two Lambda function aliases. Name one as Production and the other as Development. Point the Production alias to the production-ready qualified ((6613fb1f-5b00-4a13-9958-7a99505c0403)) version. Point the Development alias to the $LATEST version
										- Wrong answers
											- Create a new Lambda layer every time a new code release needs testing
												- Lambda layers are used to add additional code or content e.g. extra dependencies, circumvent Lambda limits. Not for just new version updates
											- Create two Lambda function aliases. Name one as Production and the other as Development. Point the Production alias to the production-ready Lambda layer ((6613fb1f-5b00-4a13-9958-7a99505c0403)). Point the Development alias to the $LATEST layer ARN
											- Create two Lambda function aliases. Name one as Production and the other as Development. Point the Production alias to the production-ready qualified ((6613fb1f-5b00-4a13-9958-7a99505c0403)) version. Point the Development alias to the variable LAMBDA_TASK_ROOT
												- This variable is used for the path to the code. It's not related to versioning the code
									- 4) A dev has written several apps that read and write to the same ((6463499e-971f-49ad-9136-306a4377fe86)) table. Each time the data is modified the change should be sent to an external API. How to accomplish this task?
										- Enable ((6463499e-971f-49ad-9136-306a4377fe86)) Streams on the table
										- Configure an ((6457bcad-7919-46a4-a9c0-8bb0ddf40189)) function to poll the stream and call the external API
										- Wrong answers
											- Configure an event in ((64b7bc1b-9bf1-4590-a835-6f42a199d644)) that publishes the change to an ((64b7bb46-67a7-438e-9cef-11d2ce9f4162)) data stream
												- It can't detect updates to ((6463499e-971f-49ad-9136-306a4377fe86)) tables
											- Create a trigger in the ((6463499e-971f-49ad-9136-306a4377fe86)) table to publisht he change to an ((64be4f03-3f36-4a12-8bab-2da48da56049))
												- Can't enable triggers for ((6463499e-971f-49ad-9136-306a4377fe86)) tables
											- Deliver the stream to an ((64b7c595-93d7-46b1-9900-853028feed64)) topic and subscribe the API to the topic
												- Can't deliver streams to SNS topic
									- 5) Each time a dev publishes a new version of an ((6457bcad-7919-46a4-a9c0-8bb0ddf40189)) function, all dependent event source mappings need to be updated with the reference to the new version's ((6613fb1f-5b00-4a13-9958-7a99505c0403)). These updates are time-consuming and error-prone. Which combination of actions should the dev take to avoid performing these updates when publishing a new Lambda version?
										- Point a Lambda alias to a new version of the Lambda function
										- Update the event source mappings with the Lambda alias ARN
										- **Wrong answers**
											- Update event source mappings with the ARN of the Lambda layer
												- No because layers are about additions to the Lambda function, not new versions
											- Create a Lambda alias for each published version of the Lambda function
												- This will create separate ARNs for each alias. Every time you create a new version you'll still have to update the event source mappings to that version's Lambda alias
											- Point a Lambda alias to a new Lambda function alias
												- Can't point from one alias to another, can only point to a Lambda function version
							- ? Session 5
							  collapsed:: true
								- 5 practice questions
									- 1) A company has an inventory system that receives sporadic inventory updates from a fulfillment system in the form of large JSON files. While many files can be sent in a short time period, days can pass with no files sent. The company wants to process these files as soon as they arrive
										- Send the JSON files to an ((6463499e-42ab-4a58-8911-df6138dfee8f)) bucket. Configure an ((6457bcad-7919-46a4-a9c0-8bb0ddf40189)) function with an S3 event source to process the S3 objects
										- **Wrong answers**
											- Send the JSON files to ((63a06e59-4078-4357-b478-dda42326daf4)). Configure a ((6457bcad-7919-46a4-a9c0-8bb0ddf40189)) function with an ((63a06e59-4078-4357-b478-dda42326daf4)) event source to process the files
											- Send the JSON files to ((63a06e59-4078-4357-b478-dda42326daf4)). Schedule an ((6457bcad-7919-46a4-a9c0-8bb0ddf40189)) function to process the files once every hour
											- Send the JSON files to an ((6463499e-42ab-4a58-8911-df6138dfee8f)) bucket. Schedule an ((6457bcad-7919-46a4-a9c0-8bb0ddf40189)) function to process the S3 objects once each hour
									- ((65f82fc5-d088-41c3-a1e3-57ead198db88))
									- 3) A dev builds an application using AWS SDK for Python (Boto3) to query an ((6463499e-971f-49ad-9136-306a4377fe86)) table. When the app is tested on an ((6463499e-bd2d-4c48-b05b-bdddeb7d8bba)) instance it returns an `AccessDenied` error. The EC2 is associated with an existing IAM role named `myRole`
										- Create a new ((64b81154-09ce-46c2-993a-0451497bcf3c)) policy with the necessary ((6463499e-971f-49ad-9136-306a4377fe86)) permissions. Attach this policy to the `myRole` ((64b81154-09ce-46c2-993a-0451497bcf3c)) role
										- **Wrong answers**
											- Create a new ((64b81154-09ce-46c2-993a-0451497bcf3c)) role with the necessary ((6463499e-971f-49ad-9136-306a4377fe86)) permissions. Attach this ((64b81154-09ce-46c2-993a-0451497bcf3c)) role as an additional role on the ((6463499e-bd2d-4c48-b05b-bdddeb7d8bba)) instance
											- Run `aws sts assume-role` by using the `myRole` ((6613fb1f-5b00-4a13-9958-7a99505c0403)). Obtain the access key ID and the secret access key from the output. Run the `aws configure` command to store these values on the ((6463499e-bd2d-4c48-b05b-bdddeb7d8bba)) instance
											- Query `http://169.254.169.254/latest/meta-data/iam/security-credentials/myRole` to obtain the access key ID and the secret access key. Run the `aws configure` command to store these values on the EC2 instance
									- 4) ((65f835cf-3690-4d30-a021-101ae3dace55))
									- 5) A dev wants to deploy ((65d89c1b-c922-4c8d-8c3f-c9e9d1947fa6)) application with AWS SAM CLI. THe dev using the ((6544c9ef-05f1-41f8-8062-a6f5dc3cc6ad)) in an ((64b7f629-76b1-4695-9eec-3caea77b1452)) environment for dev and has run the `sam build` command to prep the app for deployment. The next day the dev connects to the same ((64b7f629-76b1-4695-9eec-3caea77b1452)) environment attempts to deploy the app using `sam deploy`, which shows the error `Invalid (or missing) template path (path must be workspace-relative, or absolute)`
										- Change the working directory to the root of the ((6620d4c0-1c5f-4f16-bfee-cf33e7cf5ffd)) application
										- **Wrong answers**
											- Rename the `template.yaml` file that was created by the `sam build` command to `deploy.yaml`
											- Place the `template.yaml` file that was created by the `sam build` command into the `.deploy` directory
											- Reinitialising the AWS SAM application with the `sam init` comment
					- [Learning Resources]
						- https://cantrill.io/2018/06/19/Passing-the-aws-certified-developer-associate-exam.html
						  collapsed:: true
							- ((6463499e-971f-49ad-9136-306a4377fe86))
							  collapsed:: true
								- Know the basics - what are TABLES, what are ITEMS, what is an ATTRIBUTE
								- Understand the key structure of a table, so PARTITION (PK) and SORT(SK) keys.
								- Know which DDB operations can occur on one PK, which on a range of PK’s, which can filter based on one or more SK’s or a range of SK’s.
								- How does security work in DDB - can access be restricted to only a table level? or can you restrict at a more fine-grained level. if you can be more granular with permissions - what can you restrict on.
								- Get used to the outputs of the various DDB commands. get-item, query, scan - what does it look like if they return data, what if they don’t?
								- Know that using the SCAN operation is almost NEVER preferred. But understand when it’s needed. What are it’s problems? (hint: performance). How can you minimise issues with the SCAN operation.
								- Can everything related to DDB be done with the CLI/API and GUI? anything which cant?
								- Understand performance of a DDB table - WCU, RCU and PARTITIONS. How do partitions impact performance? what causes additional partitions to be created?
								- Rapid changes of WCU and RCU is almost NEVER a good idea. Understand WHY!
								- Related to the above point - understanding why DDB tends not to be ideal for sudden bursts of read/write is good. Also, know how to mitigate against burst. How can DAX help, what about SQS, what about elasticache?
								- Be comfortable with the READ and WRITE size in DDB. Know how eventual and immediate consistency for reads impacts the RCU needed. Be able to calculate how many RCU and WCU are needed for a given number of reads or writes of a certain size and how eventual/immediate consistency changes this calculation. I’m going to have a blog post dedicated to this soon.
								- Be very comfortable with Global (GSI) and Local (LSI) secondary indexes for DDB. What’s the difference? which one allows alternative SK and PK? which one doesn’t? are there limits to how many you can have? are there limits on WHEN they can be created? How is performance allocated and controlled for both?
							- ((6463499e-bd2d-4c48-b05b-bdddeb7d8bba))
								- Understand how EC2 `instance roles` work, when are they applied, can they be changed? does the instance need to be stopped, restarted or terminated?
								- Whats the AWS recommended method to obtain the EC2 internal, external, elastic IP from inside the instance, how exactly is it accomplished.
								- Inside an EC2 instance, what order are credentials processed - Roles/profiles etc.
								- If permissions are changed on a role, do they change immediately? if not, how long?, 
								  if it’s not immediate can it be forced, if so, how?
							- ((6457bcad-7919-46a4-a9c0-8bb0ddf40189)) and ((6529032b-bb04-4660-836b-f33e1ae727ba))
							  collapsed:: true
								- Be comfortable with the different ways a function can be uploaded. Inline, is S3 an option? is uploading a ZIP an option? what about using CloudFormation?
								- Understand the structure of all of the ways a function’s code is provided.
								- Is there a maximum runtime for a lambda function? if so, what is it? If there is and you need something to run for longer, how can you achieve this?
								- What are ((64b7c5ea-fc23-4c8f-bba3-40309679cf7d))? what do they do? how are they different from normal functions?
								- Is there a way to improve the speed of DB connections using Lambda by persisting them? i.e keeping them open between executions of many functions. If so, how is this accomplished
								- Learn the architecture of API gateway, how it works, what its components are and do.
								- Is API gateway resilient? at what level? AZ, Region, Globally?
								- Could you talk step by step about how to deploy something to API Gateway
								- Understand how API Gateway and Lambda interact.
								- How can you rollback within API Gateway/and or Lambda.
								- What are TAGS? what are they used for? what functionality do they offer.
							- Encryption
								- Learn about envelope encryption & how it’s used in AWS.
								- Understand what each different key type in AWS is, and exactly the function of each
								- Are there any limits on using KMS encryption which could impact high-volume usage? any maximum operations per second on KMS encryption/decryption/key management usage?
								- How does ‘re-encryption’ work for various AWS services when using KMS.
								- Understand how S3 encryption works… what keys are used
								- Understand how RDS encryption works - what components are encrypted and when.
								- What AWS services can help with encryption without adding additional COMPUTE requirements.
							- ((64b7b96a-d3b7-416b-9c76-2f6f8ab6a4c1))
								- Be comfortable with how a Queue works, specifically ((64b7c5bd-a765-4700-8546-43162a29aea8))
								- know the difference between FIFO and non FIFO
								- Know how SQS can scale, and how FIFO impacts that.
								- Understand the concept of a item on the Queue,
								- Whats the difference between short polling and long polling?, does long polling impact costs in any way?
								- What’s the function of a dead letter queue.
								- What’s the function of the SQS visibility timeout?
								- How can you avoid double-processing of items in a queue.
								- Understand how kinesis is architected .. what are shards?
								- Is Kinesis FIFO? does single shard or multi-shard make a difference?
								- When would you use ((64b7ba97-a707-4786-a823-3a0ca7b2d177)) vs SQS, single consumers, multiple consumers?
								- Understand the differences between SQS and ((64b7c595-93d7-46b1-9900-853028feed64)), which one would you use to notify individuals or teams of people. Which one would allow integration of a logging/mgmt application application into AWS.
								- Be comfortable with how to configure ((64b7ed98-c4a6-422a-89da-31ef57526783)), how to use SES from a developer perspective. understand the limits of SES and where you WOULD and WOULDN’T use it.
								- Research datapipeline and understand its role in the AWS ecosystem for a developer. Why would you use it, how, what can it integrate with.
							- ((64b81154-09ce-46c2-993a-0451497bcf3c)) and Security
								- Understand the limits of IAM, how many users, how many groups.
								- When to use USERS, GROUPS and ROLES.
								- When is federation a requirement?
								- What can IAM federate with?
								- Understand the IAM policy document structure, be able to read policies.
								- ARN’s, Wildcards, Fine-grained policies.
								- Are you comfortable with the best practice ways of storing keys, passwords and other sensitive information and making it available to other AWS services such as EC2?
								- What are the best practices for authenticating large numbers of users - say development teams for AWS - IAM accounts, using roles, using federation to another ID store.
								- Be comfortable with Roles - `TRUST` and `ACCESS` policies.
								- Know how `sts:AssumeRole` functions from a developer perspective.
							- ((6463499e-42ab-4a58-8911-df6138dfee8f))
								- A good understanding of the architecture of S3 is essential
								- Bucket’s, Object’s, metadata.
								- Can you add custom metadata to an object, does it need a specific format? is there a specific name which needs to be used?
								- Is an S3 bucket flat or does it have folders? (hint `the folders arent real`)
								- Does S3 have partitions? how does S3 determine which partition to store objects in?
								- Does S3 have performance limits? how can you influence these, how is your object naming related to this?
								- Does S3 allow encryption? how does this work? what options are there for encryption. Does S3 use envelope encryption? which encryption should be selected if a customer wants to control keys.
								- How does key rotation work in S3? whats it’s function.
								- How can you prevent an S3 bucket storing objects which aren’t encrypted? is there an AWS best practice way of handling this?
								- S3 performance management is a big deal, it would be **really** good to be 100% comfortable with object naming and how it relates to performance.
								- Understand S3 billing … based on space, transfer and operations. Understand how to optimise costs for using S3 by choosing as storage class, and knowing which operations to use … learn the limits at a high level for GET and PUT.
							- ((6463499d-63a1-485e-bf7e-1bae513fd542))
								- Understand the architecture of elastic beanstalk.
								- It’s a PAAS product - when WOULD you use it, when WOULDNT you. What types of apps does it suit and what type doesn’t it work well with.
								- How is access to a DB provided via elasticbeanstalk.
								- How does deployment work in EB, different rollout methods, their pros and cons.
								- How does scaling work? what scaling options exist.
								- How can EB be customised, what are the various files which can be used.
								- How is software deployed into an EB environment
								- Where is that software stored pre deployment, during deployment and afterwards.
								- What about application versions?
								- What about environment swaps? how does that work.
								- really ensure you understand deployment methods - ensuring a certain capacity is maintained.
							- ((6463499e-dc33-4af7-bbb7-33338a8a325b))
								- Be comfortable knowing how to use CloudFormation to deploy things into AWS.
								- Specifically, how to deploy serverless applications into AWS using CloudFormation
								- Understand templates & stacks, and how resources are updated and replaced based on template changes.
								- from a development perspective, understand changesets
								- Be comfortable interacting with CloudFormation from the API and CLI.
							- Monitoring
								- ((64b7f73d-a5c9-4ec8-895e-ef8e5ab585d9)) and the ability to trace had a major place in this exam. Study and understand how x-ray works and how it can be beneficial to a Developer
								- know what xray works with, and how it can be integrated.
								- understand it’s limits and main capabilities.
								- Be comfortable with ((6463499e-fe31-4613-8b61-e232816b6ddb)) - how it works globally and regionally. Understand how to use it to diagnose errors you may see in your applications. What if an application experiences a bucket not found .. how could you use cloud trail to diagnose this.
								- Know how services log to ((6463499e-5ffa-47d2-aeb5-b9a8bce9bc64)) - for instance if Lambda isn’t logging to ((6463499e-5ffa-47d2-aeb5-b9a8bce9bc64)) even though you know its running, be able to diagnose why!
							- ((64b7b97b-7aaf-4b4e-aabe-39727e50151e))
								- Be comfortable at a high level with the architectural basics for RDS/Aurora and DDB
								- Understand how read-replicas can be used not only to add resiliance, but also allow read operations to scale beyond a single server.
								- Understand the best practice ways of providing the read replica server details to an application. Hostnames? IP’s? how to obtain these at scale, across many application servers.
							- ((6463499e-529d-478c-822f-2ff43f26b6bf))
								- Understand at a foundational level what ‘in memory caching’ is. What it does, how it works, the advantages and disadvantages.
								-
								- Know the sizes AWS offers, and the capabilities and limitations of each engine. Sharding, clustering, backups, replication, speed, customisability.
								- Can elasticache be used with DDB? can it be used for user sessions.
								- Can it be used to cache S3? what about SQL databases like RDS and Aurora?
							- Misc
								- Be confortable with how to implement (from a development perspective) good global performance and resiliency. When to use ELB’s, R53, Multiple Buckets or multiple DynamoDB tables with replication. When is a CDN preferable over having content locally.
								- From a developer perspective understand how to access Load Balancer logs to determine the real IP address of clients connecting to your services.
								- Research how to fault find with Load Balancers, for the various difference HTTP error codes, how would you determine the root cause and rectify.
								- Research the basics of containers, docker and how to utilise ECS.
								- Understand the best ways, and more importantly the best practise ways to give specific containers access to AWS services - can roles be used? are these assigned to a container host or containers themselves.
								- What is a launch configuration, how is it used?
								- What is an autoscaling group, how is it used, how does it relate to a launch configuration. Can you scale using an autoscaling group based on number of users? if so, how would you accomplish that?
								- Do you understand when and where storage services in AWS are appropriate? can S3 be mounted to an EC2 instance? if not, which service can be?
								- If you needed to make application data available to many EC2 instances… what storage service would be the most appropriate?
								- Be able to diagnose the reasons for slow application performance based on given data. Understand the various steps, login, profile access, API access, data access.
								- Research how cognito works, what does it do, how does it help provide sync services to mobile apps/devices.
						- ![AWS-Certified-Developer-Associate_Exam-Guide.pdf](../assets/AWS-Certified-Developer-Associate_Exam-Guide_1728726202517_0.pdf)
					- Related: ((6463499e-7e3f-4d66-89b4-cf300a0dcda7))
				- AWS Certified SysOps Administrator - Associate
				- AWS Certified Solutions Architect - Associate
				  id:: 64b1187f-6149-43de-9c0f-889e0dfb1596
				  collapsed:: true
					- Reviews
						- [Solution Architect Associate is what I'd recommend to start with. Practitioner is for non-technical people, Developer Associate and Sysops Associate are just marginally different than SA, often focusing on services which are marginally useful at best (few people use AWS CI/CD solutions and it makes up most of the difference for developer cert), I wouldn't bother with them](https://news.ycombinator.com/item?id=37907669)
				- AWS Certified Data Engineer - Associate
			- L3 - Professional
				- AWS Certfied DevOps Engineer - Professional
				- AWS Certified Solutions Architect - Professional
			- Speciality
				- Advanced Networking
				- Machine Learning
				- Security
		- Free courses
			- [AWS Partner: Well-Architected Best Practices (Technical)](https://explore.skillbuilder.aws/learn/course/2426)
			  id:: 64c791d0-134f-4886-949c-277337514d1f
			- [AWS Partner: Accreditation (Technical)](https://explore.skillbuilder.aws/learn/course/internal/view/elearning/1096/aws-partner-accreditation-technical)
			  id:: 64c76fd7-dd44-4574-8954-440906695483
			  collapsed:: true
				-
			- [AWS Partner: Sales Accreditation (Business)](https://explore.skillbuilder.aws/learn/course/internal/view/elearning/13258/aws-partner-sales-accreditation-business)
			  id:: 64c76f3d-a326-4300-b44e-771442b94c69
			  collapsed:: true
				- ^^Skipped the content to immediately try the test^^
				- There's a 20-question test at the end. Can also have a new tab and read the content during the untimed test
					- When is a Partner-originated and led opportunity ready to be submitted to the APN Customer Engagements (ACE) Program? [Select THREE]
						- There is a clear project description with how your company’s solution(s) addresses customer requirements 
						  Correctly checked
						- There is customer consent to share the opportunity details with AWS
						- It is an active opportunity with a target close date in the future
					- ((64a419f7-d7f8-4aaf-be6e-d617989f17dc))
					- When referring to vendor lock-in, what is  usually the underlining concern? Switching costs
					- Where can organization see the greatest business benefits when modernizing? [Select THREE.]
						- Increased business agility
						- Increased efficiency of developers
						- Improved return on investment (ROI) and reduction of total cost of ownership (TCO)
					- What topic becomes an opportunity for discussion when a customer is concerned about the cost of cloud? AWS cost optimisation
					- How does business agility contribute to business value on AWS? [Select TWO.]
						- Getting products and features to market faster
						- Increased experimentation
					- What segments are considered Public Sector by AWS Sales?
						- Government, Education, Nonprofit, Healthcare
					- What are the primary teams involved in co-selling with AWS? [Select THREE.]
						- AWS Partner team, AWS Sales team, AWS Marketplace team
					- What are the best practices when engaging AWS teams? [Select THREE.]
						- Demonstrate solution alignment to customer objectives
						- Own the opportunity and communicate opportunity status often
						- Articulate unique value, such as proven solutions and industry expertise
					- Which of the following are common objections to cloud adoption? [Select THREE.]
						- Increased cost
						- Skills gap
						- Loss of control or visibility
					- What can customers typically expect when it comes to cost savings over time?
						- Customers’ cloud efficiency will improve through various optimizations, even with increased cloud usage.
					- Which of the following examples demonstrate increased staff productivity after migrating to AWS? [Select TWO.]
						- Infrastructure staff eliminates time spent on hardware installation and maintenance
						- Server admins can manage more virtual machines after migration
					- Operational Resilience - The business value that the cloud generates in the form of resiliency includes increased system availability, reduced latency, higher SLA achievement, and better security. Businesses see this through increased availability, improved security, and reduced unplanned outages.
					- What is cloud computing?
						- On-demand delivery of IT resources over the internet with pay-as-you-go pricing
					- Cost savings is the pillar of the AWS Cloud Value Framework which is often the initial focus for customers considering a cloud migration
			- [AWS Partner: Cloud Economics Accreditation](https://explore.skillbuilder.aws/learn/course/internal/view/elearning/1099/aws-partner-cloud-economics)
			  id:: 64c76f40-8126-4293-aa0e-69ad7323e741
			  collapsed:: true
				- [AWS Partner: Cloud Economics](https://explore.skillbuilder.aws/learn/course/1099)
				  id:: 64a40a28-baf2-428e-85d8-79ab03be1e6f
				  collapsed:: true
				  5/10
					- Cloud Economics
						- 2 primary focus areas
							- 1) Business Value
							  collapsed:: true
								- What you discuss with customers pre-sale to help them understand the value of AWS
								- Purpose
								  collapsed:: true
									- Address customer concerns regarding financial components
									- Facilitate progressing to activities that show the full value of moving to the cloud
								- Business value analysis
								  collapsed:: true
									- You want to transition AWS newbies quickly through analysis, so you can get to the stages where you provide them value
									- Value activities
									  collapsed:: true
										- Architectural reviews
										- Proof of concept
										- Workload migration
										-
							- 2) Cloud financial management
							  collapsed:: true
								- Helping customers be successful in financially managing their AWS infrastructure
						- Benefits
							- Increase customer confidence in AWS migration
							- Earn customer trust through proactive cost reduction and optimisation strategies
					- 1) Business Value: *AWS Cloud Value Framework*
					  id:: 64a419f7-d7f8-4aaf-be6e-d617989f17dc
						- What
							- The main benefits for moving businesses to the cloud
						- Aspects
							- **Cost Savings**
							  collapsed:: true
							  Infrastructure cost savings of avoidance from moving to the cloud
								- Cost savings analysis
									- Cost comparison:
									  Compares the total cost of ownership (TCO) for running an on-premises environment with deploying workloads on AWS
									- Business case:
									  Helps your customers compare costs as it evaluates both TCO and non-TCO benefits of migrating to the cloud.
								- 3 ways AWS lowers costs:
									- Consumption-based model
										- Customer only pays for what they use. Preventing overprovision/underprovision
									- AWS pricing models
										- On-Demand
											- Pay for compute capacity by the second with no long-term commitments
										- Savings Plans and Reserved Instances
										  id:: 64a42901-ffd2-4028-b1c5-269b205e4dd0
											- Make a commitment and receive significant discount off compute
											- ((649d9901-5e4b-4deb-88a9-40d0043e2a66))
											- ((649d9949-930d-4e57-8257-3b0f859f7b65))
												- {{embed ((649d9949-930d-4e57-8257-3b0f859f7b65))}}
											- [Comparison](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-purchasing-options.html)
										- Spot Instances
											- Use spare Amazon EC2 caacity at up to 90% off On-Demand prices
									- Frequent price reductions
										- AWS continually lowers costs by increasing efficiencies
										- Savings are passed on to AWS customers automatically
								- Cost savings analysis discussion
									- Make sure all the right stakeholders are present to discuss the cost analysis
									- What to avoid
										- Focusing purely on pricing and discounts, rather than cost analysis
										- Comparing a duplicate of an on-premises environment - instead look where different hardware can be used
										- Bringing up the cost savings discussion late in the decision-making process
										- Only one person making the analysis
							- **Staff Productivity**
							  collapsed:: true
							  Efficiency improvement by reducing or eliminating tasks
								- Typical functions:
									- Server
										- Eliminaed - hardware repair
										- Reduced - patching software, budget/plan server, prep detailed implementation plans
									- Network
										- Eliminated - install/refresh network hardware, network maintenance, returning defective parts
										- Reduced - forecast network traffic for capacity planning, ensure network is running well
									- Storage
									- Application
									- Facilities
									- Security
							- **Operational Resilience**
							  collapsed:: true
							  This is the benefit gained from improving availability, reducing unplanned outages and enhancing security
								- Main focuses: Availability and Security
								- Downtime of servers, storage, database, network, client etc causes a huge loss of revenue for the business
								- Many types of downtime costs:
									- 3rd-party fees
									- Equipment replacement
									- Incidental costs
									- Recovery activities and costs
									- Detection costs
									- Unproductive IT staff
									- Lost revenue
									- Business disruption
								- Cornerstones
									- Operations
										- Causes for failure - human errors, configuration errors, procedural errors, commonplace accidents (e.g. spilling liquid)
										- How AWS helps:
											- Leverages automation
											- Manages services end-to-end
											- Provides system-wide visibility
											- Supports security and governance configuration
											- Monitors API access
									- Security
									- Software
									- Infrastructure
							- **Business Agility**
							  collapsed:: true
							  Deploying new features and applications faster and reducing errors
								- e.g. customer/employee retention, reduced time to deploy, less incidents/defects, etc
								- AWS helps businesses to start new initiatives whilst reducing risks and costs
							- **Sustainability**
							  collapsed:: true
							  Minimising the environmental impact of operations
								- Areas of focus
									- Carbon emission reduction
									- Water conservation
									- Social responsibility
									- Circular economy
									  e.g. zero landfill, recycling, etc
								- Some easy ways to optimise for sustainability
									- Use Instance Scheduler on AWS
									- Choose Serverless
									- Improve power efficiency
									- Use AWS Cost Explorer
								- AWS Customer Carbon Footprint tool
						- Related: ((64a3dff5-efbe-4d9e-9baf-0106aae2dc78))
					- 2) Cloud Financial Management
						- 4 pillars
							- **Measurement and accountability (See)**
							  collapsed:: true
							  Establish cost transparency to ensure visibility
								- Activcities:
								  collapsed:: true
									- Tagging - cost usage mapped to workloads/org structure
									- Establish reporting and monitoring for near real-time decision making
									- Allocate cloud costs by implementing showbacks or chargebacks for cloud spend e.g. commitment-based purchase options, marketplace purchases etc
									- Measuring and reporting cloud efficiency and value KPIs
								- AWS Cost Explorer helps visualise cost and usage
								- Custom dashboards and tools
							- **Cost optimisation (Save)**
							  collapsed:: true
							  Identify waste, build architectures that scale based on demand, and improve cost efficiency
								- Activities:
								  collapsed:: true
									- Avoid technical debt by architecting early on to be cost-effective
									- Identify and eliminate cloud waste
									- Choose the best purchase option to drive down costs e.g. savings plans, reserved instances, spot instances
									- AWS innovation enables them to pass on cost savings through technical upgrades down to customers
							- **Planning and forecasting (Plan)**
							  collapsed:: true
							  Understand current and future costs and IT needs that drive accurate planning
								- Activities:
								  collapsed:: true
									- Improving forecasting accuracy
									- Estimate cloud workloads using AWS tool
									- Quantify cloud business value to learn how to prioritise projects
								- AWS Pricing Calculator - create a cost estimate for a new product
								- AWS Service pricing pages - they have info for other services not in the Pricing Calculator
								- [AWS Pricing API](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/price-changes.html) - programmatically access pricing details and receive alerts
								  id:: 64a6babe-8836-4d19-a205-1268fb2f2c57
								  AKA AWS Price List API
								- AWS Cost Explorer - trend based spending
								- AWS Migration Portfolio Assessment
							- **Cloud financial operations (Run)**
							  collapsed:: true
							  Identify and invest in people, tools and automation
								- Objective:
								  collapsed:: true
									- Make sure customers realise the value of the cost benefits associated with running their workloads on AWSque
								- Activities
								  collapsed:: true
									- Secure executive sponsorship for a CFM function - ensures a programmatic approach to cost management
									- Align stakeholder understanding of cloud cost - creates a self-sustaining cloud aware culture
									- Implement cloud consumption guardrails - improves business agility and cost governance
									- Evolve processes, automation and tools - maintains cost efficiency at scale
								- Cloud Center of Excellence (CoE)
								  collapsed:: true
									- This team is responsible for
									  collapsed:: true
										- Aligning incentives
										- Control adn governance
										- Drive automaiton
										- Report
										- Set up KPIs
									- AWS partners should encourage clients to setup a CoE
									- CoE should address these questions
									  collapsed:: true
										- Candidates for Reserved Instances and Savings Plans
										- Reasons for not buying those
										- Elsatic workload support
										- Well-architected reviews
										- etc
								- Tools for monitoring and reporting metrics
								- Best practices for automation
								  collapsed:: true
									- Identify always-on instances - candidates for reserved instances or savings plans
									- Identify underutilised instances - candidates for downsizing
									- Identify idle instances
									- Automate storage aging - e.g. from S3 Standard to S3 Standard-IA, then to Glacier
									- Create a status dashboardR
									- Report on savings
								- Scheduling
								  collapsed:: true
									- ((6463499e-5ffa-47d2-aeb5-b9a8bce9bc64)) to setup custom schedules for start/stopping various AWS services
					- Migration Portfolio Assessment (MPA)
						- Tool to help teams to transition to cloud by providing cost savings analysis + migration planning reports
						- MPA is available to Select, Advanced and Premier Partners
			- ((64a6c664-aba8-4ec6-ad46-e5fb31f396c9))
	- Ecosystem
		- ((638d061d-e696-4f04-933c-35f8836e125d))
		- [GitHub - cdklabs/cdk-nag: Check CDK applications for best practices using a combination of available rule packs](https://github.com/cdklabs/cdk-nag)
		  For AWS SDK
		-
	- [Learning Resources]
		- https://roadmap.sh/aws
		-