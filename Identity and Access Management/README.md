# AWS Identity and Access Management (IAM)

AWS Identity and Access Management (IAM) is a security service that enables you to securely manage access to AWS resources. With IAM, we can create identities, assign permissions, and control who can access specific AWS services and resources.

Instead of sharing the AWS Root account with everyone, IAM allows you to create separate users and assign only the permissions they need. This makes your AWS environment more secure and easier to manage.

## Why do we use IAM?

IAM helps us:

- Secure AWS resources by controlling access
- Create individual identities for users and applications
- Enforce the Principle of Least Privilege
- Reduce reliance on the Root User for everyday tasks

## Authentication vs Authorization

### Authentication

Authentication verifies the identity of a user.

**Question answered:** Who are you?

AWS supports authentication using:

- Username and password (AWS Management Console)
- Access Key ID and Secret Access Key (CLI / SDK)
- Temporary credentials (via IAM Roles and STS)

### Authorization

Authorization determines what an authenticated user is allowed to access.

**Question answered:** What are you allowed to do?

Permissions are managed using IAM Policies.

## Main Components of IAM

### 1. IAM User

An IAM User is an identity created within an AWS account that represents a person or an application requiring access to AWS resources.

Each user can have:

- Console login access
- Programmatic access (CLI/SDK)
- Permissions through policies

### 2. IAM User Group

A User Group is a collection of IAM users.

Instead of giving permissions to each user one by one, we add users to a group.

Example:

Developers Group → EC2 and S3 access
Admin Group → Full AWS access

This makes permission management much easier.

### 3. IAM Policy

A Policy is a JSON document that defines permissions.

It controls:

- Which AWS services can be accessed
- What actions are allowed
- Which resources can be used

Example:

Read-only access to S3
Full access to EC2

Policies can be attached to:Users,Groups and Roles 

### 4. IAM Role

An IAM Role is a temporary identity that provides permissions without using permanent credentials.

Roles are commonly used by:

- EC2 instances
- Lambda functions
- Other AWS services

Unlike IAM Users, Roles do not have a username or password.

## 🔑 Difference Between Root User and IAM User

| **Feature**                     | **Root User**                                                  | **IAM User**                                                               |
| ------------------------------- | -------------------------------------------------------------- | -------------------------------------------------------------------------- |
| **Created When**                | Automatically created when you create an AWS account           | Created manually by the AWS administrator                                  |
| **How You Log In**              | Uses the AWS account email and password                        | Uses a separate IAM username and password                                  |
| **Access**                      | Has complete access to all AWS services and resources          | Only has the permissions assigned to it                                    |
| **Can Permissions Be Limited?** | ❌ No, it always has full access                                | ✅ Yes, permissions can be customized using IAM policies                    |
| **Used for Daily Work?**        | ❌ No, it should only be used for important account-level tasks | ✅ Yes, it is meant for daily work and administration                       |
| **Can Create Other IAM Users?** | ✅ Yes                                                          | ✅ Yes, if the required permissions are granted                             |
| **Best Practice**               | Use only for account setup, billing, and emergency tasks       | Use for everyday AWS operations following the Principle of Least Privilege |

## Best Practices

- ✅ Never use the Root User for everyday tasks.
- ✅ Enable Multi-Factor Authentication (MFA), especially for the Root User.
- ✅ Follow the Principle of Least Privilege.
- ✅ Use IAM Groups to manage permissions efficiently.
- ✅ Use IAM Roles instead of sharing long-term credentials whenever possible.
- ✅ Rotate access keys regularly and avoid sharing credentials.

## Conclusion

AWS IAM is the foundation of AWS security. By creating IAM users, organizing them into groups, assigning permissions through policies, and using roles for temporary access, organizations can securely manage access to AWS resources while following security best practices.