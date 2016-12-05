# aws-lambda-unzip-py
Python AWS Lambda function to extract zip files uploaded to S3.

Files are extracted where the zip file was uploaded. The zip file will be deleted at the end of the operation.

## permissions
To remove the uploaded zip file, the role configured in your Lambda function should have a policy similar to this:

```
{
    "Effect": "Allow",
    "Action": [
        "s3:GetObject",
        "s3:PutObject",
        "s3:DeleteObject"
    ],
    "Resource": [
        "arn:aws:s3:::mybucket"
    ]
}
```
