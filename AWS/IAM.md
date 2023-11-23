# IAM

```sh
aws configure
aws iam list-users
```

```json
// IAM policy sample
{
  "Version": "2023-11-19",
  "Statement": [
    {
      "Sid": "1",
      "Effect": "Allow",
      "Action": ["s3:GetObject", "s3:PutObject"],
      "Resource": "arn:aws:s3:::mybucket/*",
      "Principal": {
        "AWS": ["arn:aws:iam::123456789012:root"]
      }
    }
  ]
}
```

**Roles** are used for permissions used by AWS services.

## Validation of policies

- IAM credentials report - for all users
- IAM access advisor - permissions for individual user
