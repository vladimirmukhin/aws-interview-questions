<h2> General questions </h2>

1. What is shared responsibility model?
2. What is the difference between IaaS, PaaS and SaaS?
3. What is the difference between Public cloud and Private cloud?
4. What requirements should be met in order for physical datacenter to be considered as Private cloud?
5. What is AWS Well-Architected framework? What are the main "pillars" of AWS Well-Architected?
6. Describe AWS Global infrastructure.
7. What is AWS partition?
8. What is region?
9. What is availability zone?
10. What is edge location?
11. What tool can be used in order to estimate AWS infrastrcture costs beforehand?

<h2> Basic questions </h2>

1. What storage options exist on AWS?
2. What compute options exist on AWS?
3. What database options exist on AWS?
4. What services can be used for monitoring AWS resources?
5. What services can be used for automating provisioning process on AWS?

<h2> Questions by service </h2>
<h3> Networking </h3>

1. What components of AWS VPC are needed in order to establish network SSH connection to an EC2 instance.
2. What possible ways to connect to the web service running on AWS exist?
3. What types of Load Balancers exist on AWS? What are the difference between them?

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
8. What is object availability and object durability?
9. What can we do to increase object durability and object availability?
9. What Amazon S3 storage types exist?
10. What is object lifecycle management?
11. What encryption options exist in Amazon S3?
12. Amazon Glacier is an extremely low-cost cloud storage that can be used as a long-term backup. What risks should you consider before choosing AWS Glacier as a backup storage?
13. What Amazon S3 features can prevent from exposing confidential data to the public Internet?
14. Access settings for your AWS account does not allow public S3 buckets but we still need to publish a static website hosted on Amazon S3. How can we acheive the goal without having to change public access settings?

<h2> Hard questions </h2>

<h2> Practice tasks </h2>

