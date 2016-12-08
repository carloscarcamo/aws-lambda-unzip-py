# aws-lambda-unzip-py
Python AWS Lambda function to extract zip files uploaded to S3.

The zip file will be deleted at the end of the operation.

## Permissions
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

# TODO
You might know the limitations of AWS Lambda. The limitation of maximum execution duration per request could cause problems when unzipping large files, also consider the memory usage.

* Improve performance (if possible) for large files
* Extract files where the zip file was uploaded
