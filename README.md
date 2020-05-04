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
[pip](https://sdk-for-java.amazonwebservices.com/latest/aws-java-sdk.zip)
