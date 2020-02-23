### CloudTrail

Create CloudTrail

1)  In the search bar type *CloudTrail*. Once in press *Create Trail*.

![images](images/90c96813e2f7a78296fcf01ccb2b3c34.png)

2)  In the creation wizard add a name for the trail `security-id-ct-demo`. Make
    sure the trail is applied to all regions. Also make sure that all s3 buckets
    are audited.

![images](images/eba0da290a89dde21a74a1d5b6484e99.png)
    
    1. Read/Write events -> All
    2. Log AWS KMS events -> Yes
    3. Insights events -> Yes
    4. Data Events: 
        * S3: Select all S3 buckets in your account 
        * Lambda: Log all current and future functions
    5. Storage location: 
        * Create a new s3 bucket: Yes
        * S3 bucket: `security-id-cloudtrail-logs-<YOUR ACCOUNT ID>-us-east-1`


![images](images/cd20ec8003eec7c5196200f24c5f6cab.png)

4)  Once done make sure that the S3 bucket is created.

![images](images/955ed0bb3071018e5bbbaa9a6d68f7bb.png)

Access the S3 bucket and make sure that the logs are being created.

Explore the contents of the CloudTrail Logs. 

Proceed to the [next lab (GuardDuty)](../02-GuardDuty-Lab/README.md)
