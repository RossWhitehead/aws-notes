# AD

Options:
* AWS Federated Authentication with ADFS
* AWS Managed Microsoft AD
* AD Connector
* Simple AD

## AWS Federated Authentication with ADFS
![](https://d1.awsstatic.com/security-center/SecurityBlog/federated_auth_with_adfs_25.dc86ecbfbbf80af3f553e7374d2a55ad1afb7016.png)


## AWS Managed Microsoft AD

* Actual Microsoft Windows Server Active Directory (AD), managed by AWS in the AWS Cloud.
* Enables the creation of a trust relationship with existing AS infrastructure, enabling the use od AD credentials from an AD hosted on-premise.
* 2 editions:
    * Standard - for small and medium organisations. Up to 5,000 employees and 30,000 directory objects
    * Enterprise - up to 500,000 directory objects.

## AD Connect

* A directory gateway with which you can redirect directory requests to your on-premises Microsoft Active Directory without caching any information in the cloud.
* Does not support AD transitive trusts. For each on-premises domain, including child domains in an AD forest that you want to authenticate against, you must create a unique AD Connector.
* Cannot be shared with other AWS accounts.
* Is not multi-VPC aware, which means that AWS applications like WorkSpaces are required to be provisioned into the same VPC as your AD Connector.

## Simple AD

* A Microsoft Active Directory–compatible directory from AWS Directory Service that is powered by Samba 4. 
* Supports basic Active Directory features such as user accounts, group memberships, joining a Linux domain or Windows based EC2 instances, Kerberos-based SSO, and group policies.
* Does not support multi-factor authentication (MFA), trust relationships, DNS dynamic update, schema extensions, communication over LDAPS, PowerShell AD cmdlets, or FSMO role transfer. 
* Not compatible with RDS SQL Server. 
