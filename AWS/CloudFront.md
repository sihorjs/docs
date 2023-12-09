# CloudFront

Uses **edge locations** to serve cached content

## For S3

- Setup OAC (origin access control) in CloudFront distribution, i.e. give cloudfront access to S3 bucket.
- Update S3 bucket policy.

## Limitations:

- Geo - allow or block list of countries
- Price classes - all, class 200, class 100

## **AWS global accelerator**

- proxies requests to the closest region without cache
- uses Anycast IP in order to connect to edge locations.
- good for HTTP that require static IP addresses
