# AWS S3 Integration with IBM Sterling B2B Integrator 6.0.2/6.0.3 and IBM Sterling File Gateway 6.0.3
This article provides details and step by step instructions to integrate IBM Sterling B2B Integrator and IBM Sterling File Gateway Integration with AWS S3 Service. 
## Pre-requisite
Audience must have working knowledge of IBM Sterling B2Bi and IBM Sterling File Gateway.

In today's cloud era there are multiple cloud storage services hosted by vendors and AWS Simple Storage Services (AWS S3), hosted by Amazon is one of them. You can use AWS S3 to store and retrieve any amount of data at any time, from anywhere on the web.

Earlier, to integrate AWS S3 with IBM Sterling B2B Integrator a custom service had to be defined. With IBM Sterling B2B Integrator 6.0, the AWS S3 Client Service was introduced, making the integration easier. Integrating AWS S3 with IBM Sterling B2B Integrator creates seamless connectivity with the cloud storage. In Sterling B2B Integrator 6.0.2 version, the service was enhanced to post messages to an existing AWS S3 bucket.

By using this service, we can perform the following operations:

•	GET, PUT, DELETE files

•	Create or delete a directory from AWS S3

•	Post objects either from a mailbox or a file system to AWS S3

In the following sections, we provide step by step instructions to integrate Sterling B2B Integrator and Sterling File Gateway with AWS S3.

## Install AWS S3 Libraries into IBM Sterling B2Bi Instance
NOTE: The following instructions are common for both Sterling B2B Integrator and Sterling File Gateway.

1.	Download latest AWS SDK from Amazon WebServices.
[latest AWS SDK](https://sdk-for-java.amazonwebservices.com/latest/aws-java-sdk.zip)

2.	Install the SDK using the install3rdParty.sh script from the /bin directory of IBM Sterling B2B Integrator installation directory.

3.	Update the dynamicclasspath.cfg file, which is available in the /properties directory of Sterling B2B Integrator installation directory to avoid conflict with other class files.

4.	Run setup.sh.

## Integrate IBM Sterling B2B Integrator with AWS S3

NOTE: Complete the following steps if you are using only Sterling B2B Integrator.

1.	Create a business process to fetch messages from a defined location and post to AWS S3 bucket using the AWSS3ClientService. For example, fetching files from a staging directory.
Note: When you create the business process, you must provide secret key and access key of the related AWS user in the business process. Additionally, you must provide the filename and mailbox message ID in the business process.

2.	Execute the BP manually.

3.	Login to AWS Management Console - S3 Service to verify that the message/object is posted into the correct bucket.

## Integrate IBM Sterling File Gateway with AWS S3 Service

NOTE: Complete the following steps if you are using IBM Sterling File Gateway.

1.	Create a custom protocol business process to fetch messages from a defined location and post to AWS S3 bucket using the AWS S3 Client Service.

Note: When you create the custom protocol business process, you must provide secret key and access key of the related AWS user in the business process. Additionally, you must provide the filename and mailbox message ID in the business process.

2.	Provide custom protocol BP details (defined in the step 1) in the AFTExtension tag, available in the AFTExtensionsCustomer.xml file, which is in the following path - <B2BiInstallationDirectory>/container/Applications/aft/WEB-INF/classes/resources/xml 

3.	Provide the definition of the custom protocol business process in the AFTExtensionsCustomer.properties file, which is in the following path - <B2BiInstallationDirectory>/container/Applications/aft/WEB-INF/classes/resources

4.	Set up the following configuration in the Sterling File Gateway dashboard:

a.	Create IBM_SFG_Community – While creating the community, select the Partner Listens for Protocol connection.This will      load AWS S3 custom protocol in the Available Protocol list.

b.	Create IBM_SFG_AWSS3_Producer_Partner – This partner initiates connection

c.	Create IBM_SFG_AWSS3_Consumer_Partner – This partner will listen for connections. Provide Bucket Name, Access Key, and Secret Key value.

d.	Create IBM_SFG_AWSS3_Routing_Channel_Template

e.	Create IBM_SFG_AWSS3_Routing_Channel

5.	Upload files to the appropriate Producer mailbox and await routing.

6.	Check the status of the routed file at Arrived File tab for producer and Deliver tab for consumer in Sterling File Gateway admin console.

7.	Log in to AWS Management Console - S3 service to verify the message/object is posted into the correct bucket.

