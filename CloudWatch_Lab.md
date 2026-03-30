# EC2 → CloudWatch Lab

## Goal
- Send logs from an EC2 instance to AWS CloudWatch
- View logs in CloudWatch
- Start thinking like a cloud security engineer

## Steps Completed
1. Created an EC2 instance.
2. Configured the EC2 instance to generate logs (e.g., system logs, application logs).
3. Installed and configured the CloudWatch Agent on EC2.
4. Started sending logs from EC2 to CloudWatch.
5. Verified logs in CloudWatch.

## Notes / Next Steps
- Make sure IAM roles allow EC2 to push logs to CloudWatch.
- Check log groups and streams in CloudWatch to confirm data is being sent.
- Explore CloudWatch Insights for querying logs.
- Practice monitoring and alerting as a cloud security engineer.

## References
- [AWS CloudWatch Documentation](https://docs.aws.amazon.com/cloudwatch/)
- [Setting Up CloudWatch Agent](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/install-CloudWatch-Agent.html)
