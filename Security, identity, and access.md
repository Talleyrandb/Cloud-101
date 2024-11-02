


# AWS IAM: Users and Groups
## IAM Users:
*  An IAM user is an identity that represents a single person or application. Each user has specific permissions assigned to them, allowing them to perform actions on AWS resources. For example, a user might have permissions to launch EC2 instances or access S3 buckets.
    IAM users have long-term credentials, such as passwords and access keys, which provide permanent access to specified resources. 
## IAM Groups:
*  An IAM group is a collection of IAM users. It allows you to manage permissions for multiple users collectively, simplifying the administration of access rights. For instance, you could create a group named Admins, granting all members administrator permissions.
*  When a user is added to a group, they automatically inherit the group's permissions. This means if you need to grant similar permissions to several users, you can simply add them to the appropriate group instead of assigning permissions individually.
### Example Scenario in AWS:
*  Creating a Group: Suppose you have a team of developers. You create a group called Developers and attach a policy that allows them to deploy applications.
*  Adding Users: You add users like Alice and Bob to the Developers group. Both Alice and Bob now have permissions defined by the group's policy.
*  Managing Permissions: If Charlie joins the team, you can simply add him to the Developers group without needing to configure individual permissions for him 
# Microsoft Entra ID: Users and Groups
In Microsoft Entra ID (formerly kowns as Azure Active Directory), the concepts of users and groups are similar but tailored for Microsoft's ecosystem. Entra ID Users:
## Entra ID user
*  Rrepresents an individual account that can authenticate against Azure services. Each user has attributes such as email addresses, roles, and assigned licenses.
*  Users can be assigned direct roles or permissions that dictate what resources they can access within Azure.
## Entra ID Groups:
*  An Entra ID group is a logical collection of users that simplifies permission management. For example, you might create a group called Finance Team, granting all members access to financial applications.
*  Groups can be used for role-based access control (RBAC), allowing you to assign roles at the group level rather than individually.
### Example Scenario in Microsoft Entra ID:

*  Creating a Group: You create a group named HR Team, which includes all human resources personnel.
*  Assigning Roles: You assign the group a role that allows access to employee records.
*  Adding Users: When new HR staff join, you simply add them to the HR Team group, granting them immediate access without additional configuration.
## Key Differences

|Feature|	AWS IAM	|Microsoft Entra ID|
| ----------- | ----------- | ----------- |
|User Credential	|Long-term credentials (passwords, keys)	|Account credentials with roles|
|Group Management	|Permissions managed via policies	|Role-based access control (RBAC)|
|User Types| Individual IAM users|	Individual accounts with attributes|

## Types of users 

|type    | Description|
| ----------- | ----------- | 
|root user| When you first create an cloud account, you begin with one sign-in identity that has complete access to all cloud services and resources in the account. |
|users    | An user is an identity within your cloud account that has specific permissions for a single person or application.  |
|user groups|An user group is an identity that specifies a collection of cloud users. |
|roles|An cloud role is an identity within your cloud account that has specific permissions. It's similar to an cloud user, but isn't associated with a specific person|

# AWS IAM Roles
AWS Identity and Access Management (IAM) roles are a way to grant permissions to entities you trust. An IAM role is similar to a user, but it is not associated with a specific person or entity. Instead, it can be assumed by anyone who needs it, including AWS services, applications, or users.

### Example of an IAM Role
*  Role Creation: You create a role named S3ReadOnlyRole.
*  Trust Policy: This role can be assumed by an EC2 instance.
*  Permissions Policy: The role allows read access to all objects in a specific S3 bucket.
When an EC2 instance assumes S3ReadOnlyRole, it can access the S3 bucket without needing to embed AWS credentials in the application running on that instance.

## Azure Role-Based Access Control (RBAC)
Azure RBAC is an authorization system that provides fine-grained access management to Azure resources. It allows you to manage who has access to Azure resources and what they can do with those resources.

Example of Azure RBAC

*  Role Definition: You create a custom role called VMOperator, which allows starting and stopping virtual machines but not deleting them.
*  Security Principal: A user named Alice is part of the DevOps group.
*  Role Assignment: You assign the ```VMOperator``` role to Alice at the resource group level containing several virtual machines.

## Comparison of AWS IAM Roles and Azure RBAC
|Feature	|AWS IAM Roles	|Azure RBAC|
| ----------- | ----------- | ----------- |
|Purpose	|Grant permissions to entities on AWS	|Manage access to Azure resources|
|Key Components|	Trust Policy, Permissions Policy	|Security Principal, Role Definition, Role Assignment|
|Assumable By|	Users, services, applications	|Users, groups, service principals|
|Scope of Access	|Limited to AWS resources	|Can be assigned at multiple levels (subscription, resource group)|
|Flexibility|	Roles can be assumed dynamically	|Roles are assigned statically based on definitions|
## Functions 
## AWS functions 
AWS Lambda enables you to run code without provisioning or managing servers. It automatically scales your applications by running code in response to events, such as changes in data or system state. You only pay for the compute time you consume, making it a cost-effective solution for many applications.

### Examples

*  File Processing:
        When a file is uploaded to an S3 bucket, it triggers a Lambda function that processes the file (e.g., generating thumbnails for images).
        Example: A user uploads an image to S3, which invokes a Lambda function to create a thumbnail and store it back in S3.
*  Real-Time Data Processing:
        AWS Lambda can process streaming data from Amazon Kinesis. For instance, you can set up a Kinesis stream that captures website click data and use a *  Lambda function to analyze this data in real-time.
        Example: A Lambda function polls Kinesis every few seconds to process new records as they arrive
*  Webhook Processing:
        Lambda can be used to handle incoming webhooks. For example, when a payment is processed through an online service, the webhook triggers a Lambda function that updates your database accordingly

## Azure Functions is Microsoft's serverless computing service that allows you to execute code in response to events. 

### Examples

*  HTTP Trigger:
        An Azure Function can be set up to respond to HTTP requests. For example, you could create an API endpoint that processes user registration data.
        Example: A user submits a registration form on your website; this triggers an Azure Function that saves the user's details to a database.
*  Timer Trigger:
        You can schedule Azure Functions to run at specific intervals. For instance, you might want a function that cleans up old records from your database every night at midnight.
        Example: A timer-triggered function runs nightly to delete records older than 30 days from an SQL database.
*  Blob Storage Trigger:
       Azure Functions can respond to new blobs being added to Azure Blob Storage.
        Example: When a new video file is uploaded, an Azure Function could automatically transcode it into different formats for streaming.
### Comparison Table
|Feature	|AWS Lambda	|Azure Functions|
| ----------- | ----------- | ----------- |
|Event Triggers|	S3, DynamoDB, API Gateway	|Blob Storage, HTTP requests, Timer|
|Pricing Model	|Pay-per-use	|Pay-per-execution|
|Language Support	|Node.js, Python, Java, C#, Ruby	|C#, JavaScript, Python, Java|
|Scaling	|Automatic scaling	|Automatic scaling|
|Development Tools	|AWS SDKs	|Azure SDKs and CLI|

## Lambda and VPC Integration
AWS Lambda functions can access resources such as Amazon RDS databases, Amazon ElastiCache clusters, and other services that are only reachable within a specific VPC. When you attach a Lambda function to a VPC, it operates within the network boundaries of that VPC, allowing for secure communications with those resources.
### Steps to Configure Lambda Functions for VPC Access
1. Create or Identify Your VPC
Before configuring your Lambda function, ensure you have a VPC set up with the necessary subnets and security groups:

*  Subnets: Choose private subnets where your resources (like RDS or ElastiCache) are located.
*  Security Groups: Define security groups that allow inbound and outbound traffic as needed.

2. Set Up IAM Permissions
Your Lambda function needs permissions to create and manage the Elastic Network Interfaces (ENIs) that allow it to connect to the VPC. You can achieve this by attaching the AWSLambdaVPCAccessExecutionRole policy to your function's execution role.
Example IAM Policy

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "ec2:DescribeSecurityGroups",
        "ec2:DescribeSubnets",
        "ec2:DescribeVpcs",
        "ec2:CreateNetworkInterface",
        "ec2:AttachNetworkInterface",
        "ec2:DeleteNetworkInterface"
      ],
      "Resource": "*"
    }
  ]
}
```
3. Attach Your Lambda Function to the VPC
You can attach your Lambda function to a VPC using the AWS Management Console or AWS CLI.
Using the AWS Console:

 	> Go to the Lambda Management Console.
 	> Select your function.
 	> Navigate to the Configuration tab.
 	> Under VPC, click Edit.
 	> Choose your VPC, then select the appropriate subnets and security groups.
 	> Save your changes.

Using AWS CLI:

```bash
aws lambda update-function-configuration \
  --function-name YourFunctionName \
  --vpc-config SubnetIds=subnet-12345678,SecurityGroupIds=sg-12345678
```
4. Internet Access Considerations
By default, when a Lambda function is attached to a VPC, it loses direct internet access. If your function needs internet access (for example, to call external APIs), you must set up a NAT Gateway or NAT Instance in your VPC:

*  NAT Gateway: A managed service that allows instances in a private subnet to connect to the internet while preventing unsolicited inbound traffic from the internet.

### Example NAT Gateway Setup:

 	> Create a NAT Gateway in a public subnet.
 	> Update the route table associated with your private subnet to route internet-bound traffic through the NAT Gateway.

5. Testing and Validation
Once configured, test your Lambda function to ensure it can access resources within the VPC:

 	> Use logging (e.g., Amazon CloudWatch Logs) to monitor function execution and troubleshoot any access issues.
 	> Verify that security group rules allow traffic from the Lambda function's ENIs to the target resources.
## Azure Function and Azure Virtual Network Integration

Virtual Network Integration enables your Azure Function App to reach resources within a VNet. This integration is primarily for outbound connections, meaning your function can call services inside the VNet but cannot receive inbound traffic from it directly.
Steps to Enable Virtual Network Integration

1. Create or Identify a VNet: Ensure you have a VNet set up in your Azure subscription.
2. Configure the Function App:
 	> Go to your Function App in the Azure portal.
 	> Select Networking from the left menu.
 	> Under VNet Integration, click on Click here to configure.
 	> Choose Add VNet, and select the desired VNet from the dropdown list (it must be in the same region) 
3. Select Subnet: You need to select an empty subnet within the VNet for integration. If you don’t have one, you can create a new subnet during this step.
4. Route All Traffic (Optional): By default, all outbound traffic from your function app is routed through the VNet. You can verify this setting in the networking configuration.

### Example Scenario
Imagine you have a function app that needs to access an Azure SQL Database secured within a VNet:
 	> Create a VNet named myVNet with a subnet called functionsSubnet.
 	> Integrate your function app with myVNet by following the steps above.
 	> Ensure that your SQL Database has firewall rules allowing access from functionsSubnet.


## References:

[IAM user groups](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_groups.html)
[Create IAM user groups](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_groups_create.html)
[Create Azure User](https://learn.microsoft.com/en-us/entra/fundamentals/how-to-create-delete-users?toc=%2Fentra%2Fidentity%2Fusers%2Ftoc.json&bc=%2Fentra%2Fidentity%2Fusers%2Fbreadcrumb%2Ftoc.json)
[Create a Azure group](https://learn.microsoft.com/en-us/entra/identity/users/groups-create-rule)
[identification guide](https://docs.aws.amazon.com/IAM/latest/UserGuide/id.html)
[Entra ID](https://learn.microsoft.com/en-us/entra/)
[Role on Azure](https://learn.microsoft.com/en-us/azure/role-based-access-control/overview?wt.mc_id=DT-MVP-5004771)
[Azure built-in roles](https://learn.microsoft.com/en-gb/azure/role-based-access-control/role-assignments-list-portal)
[IAM roles](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles.html)
[Access Resources in a VPC from Your Lambda Functions](https://aws.amazon.com/ru/blogs/aws/new-access-resources-in-a-vpc-from-your-lambda-functions/)
[title](
[title](
[title](
[title](
[title](
[title](
  

