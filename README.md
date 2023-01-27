# How to setup S3 bucket with CloudFront


1. Create an S3 bucket, enable versioning
2. Do not edit any permissions, enable bucket for static hosting
3. Create a distribution on CloudFront. 
4. Pick the origin domain as the s3 bucket, it would automatically use the bucket name as the name of the origin. 
5. For origin access pick “Origin access control settings (recommended)”. Create an Origin access control setting, and give it any name. CloudFront will provide a policy statement that you would copy and add to the s3 bucket policy after creating the distribution. 
6. Leave the remaining settings as default until you reach the ‘Viewer Protocol Policy, you can select HTTP and HTTPS. 
7. For the ‘Allowed HTTP methods’, select “GET, HEAD”
8. Leave ‘restrict viewer access’ to No
9. Leave the Cache key and origin requests settings as default
10. Functional associations should be left as default. 
11. In the settings section, the Price class should be set as default for best performance. Leave web ACL as default. 
12. The Alternate domain name should be left as default unless you have a domain name registered with either Route 53 or other domain registrars. 
13. If you added an SSL certificate to your domain name, you can add it here.
14. Supported HTTP versions should be left as default. 
15. Remember to set the default root object to your default file e.g index.html. 
16. Leave standard logging and IPV6 setting as default. 
17. Now create the distribution. 

It would take up to 15 minutes for the CloudFront DNS to be able to receive traffic.

Since Cloudfront allows for 1 TB of data transfer out per month and 10,000,000 HTTP or HTTPS Requests per month . I would add my cloudfront DNS here. This distribution would be deleted a week from today. 

