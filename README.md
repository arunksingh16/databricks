# Databricks
Databricks Deployment on AWS using Terraform [https://aws-quickstart.github.io/quickstart-databricks-unified-data-analytics-platform/]

### What is Databricks?
Databricks excels at enabling data scientists, data engineers, and data analysts to work together on uses cases like:

- Applying advanced analytics for machine learning and graph processing at scale
- Using deep learning for harnessing the power of unstructured data such for AI, image interpretation, automatic translation, natural language processing, and more
- Making data warehousing fast, simple, and scalable
- Proactively detecting threats with data science and AI
- Analyzing high-velocity sensor and time-series IoT data in real-time
- Making GDPR data subject requests easy to execute


### Databricks workspace
A unified environment(accessed via browser based UI) that your team uses for accessing all of their Databricks assets. You can create multiple workspaces or can have one. 
Please note A Databricks account represents a single entity for purposes of billing and support; it can include multiple workspaces.


### Architecture
Each databricks env has two planes - control and data plane
> Control Plane - The control plane includes the backend services that Databricks manages in its own AWS account
> Data Plane - compute resources in your AWS account is called the Classic data plane.

Please note You can use Databricks connectors so that your clusters can connect to external data sources outside of your AWS account to ingest data or for storage.

### What is E2 Architecture
Databricks specific, new arch released in 2020 which comes with a lot new features.

### Databricks specific supported region in AWS
https://docs.databricks.com/administration-guide/cloud-configurations/aws/regions.html


### Databricks datasets for test
https://docs.databricks.com/data/databricks-datasets.html

### Apache Spark


### Delta Lake
Delta Lake is a key component of the Databricks lakehouse architecture. Databricks has built-in support for Delta Lake, and the latest Databricks Runtimes include performance enhancements for even more speed and performance.
https://docs.databricks.com/delta/index.html

### Cloudformation
https://github.com/aws-quickstart/quickstart-databricks-unified-data-analytics-platform


### Terraform template overview

`In the private subnets:`
Databricks clusters of Amazon Elastic Compute Cloud (Amazon EC2) instances.
One or more security groups to enable secure cluster connectivity.
>
`In the public subnet:`
A network address translation (NAT) gateway to allow outbound internet access.

`An Amazon Simple Storage Service (Amazon S3) bucket`
to store objects such as cluster logs, notebook revisions, and job results.

`A VPC endpoint` 
for access to S3 artifacts and logs.

`A cross-account AWS Identity and Access Management (IAM) role` to enable Databricks to deploy clusters in the VPC for the new workspace. Depending on the deployment option you choose, you either create this IAM role during deployment or use an existing IAM role.
