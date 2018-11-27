#Usecase of Security Data
It is difficult to make a logical model ahead of time -> This means that unsupervised, or semi-supervised learning is impossible.

Problem: Screen reading is not scalable.  P(detection_using_screen_reading) <= 0.1
Goal: Alerts should be P(x) = .95 actionable.

Alert {
WHo can access it?
Where did it come from?
When?
What?
}



Data Sources for Security out of the box in AWS
* AWS Cloudwatch
* AWS VPC Flow Logs
* AWS Inspector --> CVEs
* AWS Guard Duty  --> Account Issues
* AWS Macie --> S3 Objects + S3 Buckets (AWS E & W only)
* AWS WAF --> Edge only

Note: S3 Public Buckets is a big issue.

Data Pipeline -- Supervised Learning

Source -> Lambda / Kinesis (Normalize) -> S3 Bucket -> Amazon Athena (Apache Hive) && Amazon Quicksight -> Amazon SageMaker == New Source

Reinforcing Loop: 
Low level event => High Confidence of Severity of Event
Mid level event => High Confidence of Supervision
High level event => High Confidence of Actionable Incident