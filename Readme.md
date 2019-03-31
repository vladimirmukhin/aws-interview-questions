<h2> General questions </h2>

1. Explain the advantage of a cloud over traditional data center.
2. What is shared responsibility model?
3. What is the difference between IaaS, PaaS and SaaS?
4. What is the difference between Public cloud and Private cloud?
5. What requirements should be met in order for physical datacenter to be considered as Private cloud?
6. What is AWS Well-Architected framework? What are the main "pillars" of AWS Well-Architected?
7. Describe AWS Global infrastructure.
8. What is AWS partition?
9. What is region?
10. What is availability zone?
11. What is edge location?
12. What tool can be used in order to estimate AWS infrastrcture costs beforehand?
13. What storage options exist on AWS?
14. What compute options exist on AWS?
15. What database options exist on AWS?
16. What services can be used for monitoring AWS resources?
17. What services can be used for automating provisioning process on AWS?

<h2> Questions by service </h2>
<h3> Networking </h3>

1. What components of AWS VPC are needed in order to establish network SSH connection to an EC2 instance.
2. What possible ways to connect to the web service running on AWS exist?
3. What types of Load Balancers exist on AWS? What are the difference between them?
4. What is AWS Direct Connect? What SLA is provided by direct conect AWS Direct Connect?
5. What HA Options are available for Direct connect?
6. Explain the difference between AWS WAF, security group and network ACL. What tool would you choose?
7. What options for connecting multiple VPCs are available. How do you make a decision about what particular option to choose?

<h3> Amazon S3 </h3>

1. How much total available space does Amazon S3 provide?
2. What is the maximum file size that can be uploaded to Amazon S3?
3. Is there any reason why we may need to split a file before starting to upload it to Amazon S3?
4. What is the maximum file size that can be uploaded to Amazon S3 in a single PUT operation?
5. What is bucket policy?
6. Explain the following bucket policy:
```
{
   "Version":"2012-10-17",
   "Statement":[
      {
         "Effect":"Allow",
         "Action":[
            "s3:ListAllMyBuckets"
         ],
         "Resource":"arn:aws:s3:::*"
      },
      {
         "Effect":"Allow",
         "Action":[
            "s3:ListBucket",
            "s3:GetBucketLocation"
         ],
         "Resource":"arn:aws:s3:::examplebucket"
      },
      {
         "Effect":"Allow",
         "Action":[
            "s3:PutObject",
            "s3:PutObjectAcl",
            "s3:GetObject",
            "s3:GetObjectAcl",
            "s3:DeleteObject"
         ],
         "Resource":"arn:aws:s3:::examplebucket/*"
      }
   ]
}
```
7. In the policy provided previosly, what is the reason to have `"Resource":"arn:aws:s3:::examplebucket"`
and
`"Resource":"arn:aws:s3:::examplebucket/*"`
separated into two different blocks?
8. A user is browsing your website and finds a funny picture that he would like to share with a colleague. He copies an URL and sends it via messager. When a colleague is trying to open a link, he receives 403 error. The website infrastructure is completely hosted on AWS. What could be the reason for the issue?
9. What is object availability and object durability?
10. What can we do to increase object durability and object availability?
11. What Amazon S3 storage types exist?
12. What is object lifecycle management?
13. What encryption options exist in Amazon S3?
14. Amazon Glacier is an extremely low-cost cloud storage that can be used as a long-term backup. What risks should be considered before choosing AWS Glacier as a backup storage?
15. What Amazon S3 features can prevent from exposing confidential data to the public Internet?
16. Access settings for your AWS account does not allow public S3 buckets but we still need to publish a static website hosted on Amazon S3. How can we acheive the goal without having to change public access settings?
17. How to share a file located in Amazon S3 with another AWS account?
18. How to share a file located in Amazon S3 with somebody who does not have an AWS account?

<h3> Amazon EC2 </h3>

1. What is instance type? What instance types exist?
2. What is instance generation? What instance generation should be choosen?
3. How is the "t" instance type different from other instance types?
4. What is Auto-Scaling groups?
5. What is the difference between horizontal and vertical scaling? What kind of scaling is acheived with Auto-Scaling?
6. How does Amazon decides about what particular instance in an Auto-Scaling group should be terminated?
7. What can be done in order to prevent an isntance from being terminated during troubleshooting via SSH?
8. How to setup post-actions for instances that are terminated by Auto-Scaling?

<h3> Databases </h3>

1. What is the difference between relational and non-relational databases?
2. What are use cases for relational databases?
3. What relational database options are provided by AWS?
4. How to replicate an RDS instance to another availability zone?
5. How to replicate an RDS instance to another region?
6. What is the difference between Multi-AZ deployment and Read-Replica?
7. What else except for High-availability can be acheived using Read-Replicas and Multi-AZ?
8. What is the difference between manual and automated RDS snapshots?
9. What are use cases for non-relational databases?
10. What non-relational database options are provided by AWS?
11. In DynamoDB there is a "scan" command. Usually, it's not a good idea to run a table scan. Why?
12. What is primary key in DynamoDB? What kind of primary keys exist?
13. What is secondary index? How is it different from primary key?
14. What is the difference between local secondary index and global secondary index?
15. What is the maximum size of a DynamoDB item? How to workaround this limitation?
16. In what cases DynamoDB should NOT be used?

<h3> CloudFormation </h3>

1. What major sections can be specified in CloudFromation template?
2. What is the only section mandatory in CloudFormation template?
3. What is the maximum number of parameters that can be passed to a single CloudFormation template?
4. What is the maximium number of resources that can be declared in a single CloudFormation template?
5. How to workaround the limitations described during previous two sections?
6. What is AWS CloudFormation update behaviors? What update behaviors exist?
7. How to predict what happens with an AWS resource during CloudFormation stack update and avoid the risk of accidential deletion?
8. What other options are available to prevent accidental deletion of CloudFormation resources?

<h3> AWS Identity and Access Management </h3>

1. What basic steps should be performed in order to secure newly created AWS account?
2. What is PARC?
3. You have created an IAM user and applied AdministratorPolicy policy to it. When trying to download a file from S3 you receive Access Denied. You are able to access other services. What could be the reason for the issue?
4. How to configure EC2 isntance to be able to connect to AWS services?
5. Once you attached an IAM role to an EC2 instance, your AWS CLI starts to authenticate without any changes. What steps should you perform if you have an application written on C that should be authenticated in AWS
6. Write an IAM policy for a user that is able to create another IAM users with limited permission scope?
7. What should be done in order to access resources located in one AWS account while being authenticated in another AWS account? What problems could be solved using such approach?

<h3> Security on AWS </h3>

1. What governance and logging options are avilable on AWS?
2. What tools can be used in order to discover compromised AWS resources?
3. What steps should be performed in case of having an instance compromised?
4. What encryption options are available in AWS? How to decide what encryption option is needed for a particular case?
5. What steps should be performed in order to encrypt an EC2 instance that already exists?
6. What steps should be performed in order to share encrypted EBS snapshot with another AWS account?

<h3> AWS Lambda </h3>

1. In what cases AWS Lambda should NOT be used?
2. How does AWS Lambda integrates with another AWS services?