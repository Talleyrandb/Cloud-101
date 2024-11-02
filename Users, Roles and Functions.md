


# AWS IAM: Users and Groups
## IAM Users:
*  An IAM user is an identity that represents a single person or application. Each user has specific permissions assigned to them, allowing them to perform actions on AWS resources. For example, a user might have permissions to launch EC2 instances or access S3 buckets.
    IAM users have long-term credentials, such as passwords and access keys, which provide permanent access to specified resources. 
## IAM Groups:
*  An IAM group is a collection of IAM users. It allows you to manage permissions for multiple users collectively, simplifying the administration of access rights. For instance, you could create a group named Admins, granting all members administrator permissions.
*  When a user is added to a group, they automatically inherit the group's permissions. This means if you need to grant similar permissions to several users, you can simply add them to the appropriate group instead of assigning permissions individually.
### Example Scenario in AWS:
*  Creating a Group: Suppose you have a team of developers. You create a group called Developers and attach a policy that allows them to deploy applications.
    Adding Users: You add users like Alice and Bob to the Developers group. Both Alice and Bob now have permissions defined by the group's policy.
    Managing Permissions: If Charlie joins the team, you can simply add him to the Developers group without needing to configure individual permissions for him 
# Microsoft Entra ID: Users and Groups
In Microsoft Entra ID (formerly kowns as Azure Active Directory), the concepts of users and groups are similar but tailored for Microsoft's ecosystem. Entra ID Users:
## An Entra ID user
*  Rrepresents an individual account that can authenticate against Azure services. Each user has attributes such as email addresses, roles, and assigned licenses.
    Users can be assigned direct roles or permissions that dictate what resources they can access within Azure.
## Entra ID Groups:
*  An Entra ID group is a logical collection of users that simplifies permission management. For example, you might create a group called Finance Team, granting all members access to financial applications.
    Groups can be used for role-based access control (RBAC), allowing you to assign roles at the group level rather than individually.
### Example Scenario in Microsoft Entra ID:

*  Creating a Group: You create a group named HR Team, which includes all human resources personnel.
    Assigning Roles: You assign the group a role that allows access to employee records.
    Adding Users: When new HR staff join, you simply add them to the HR Team group, granting them immediate access without additional configuration.
## Key Differences

|Feature|	AWS IAM	|Microsoft Entra ID|
| ----------- | ----------- | ----------- |
|User Credential	|Long-term credentials (passwords, keys)	|Account credentials with roles|
|Group Management	|Permissions managed via policies	|Role-based access control (RBAC)|
|User Types| Individual IAM users|	Individual accounts with attributes|
