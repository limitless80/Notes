`About`
**IAM** is a Root account created by default, it should not be used and shared, it's a global service provided by the **AWS**. 

`Group`
**Users** are the people of your organization, and can be grouped 
**Group** can be composed of only Users, not of other group
In AWS a user can not be any group, and also be in multiple group.
![](https://i.imgur.com/q2Alw5b.png)

`Permission`
So for a user to get access to a specific service in AWS, the user is provided with a **JSON** Documents called polices. basically these polices are like a key-code to access the service, the polices look-something-like this.

![](https://i.imgur.com/1jeditG.png)

In AWS there is a principle that "Don't provide permission to user more than he needed", for security reason and cost to pay to AWS.
****
`Policies Structure`
Consists of 
- Version: policy language version,always includes "2012-10-17" -- (The version Number)
- ID: an identifier for the policy (optional)
- Statement:one of more individual statements (required)
`Statements consists of`
- Sid: an identifier for the statement (optional)
- Effect: whether the statement allows or denies access(Allow,Deny)
- Principal: account/user/role to which this policy applied to
- Action: list of actions this policy allow or denies
- Resource: list of resources to which the actions applied to 
- Condition:conditions for when this policy is in effect(optional)

`The Password policy`
- Accounts holding higher privileges can set the password policy to require certain combination of characters , require particular characters etc
- AWS has two security protections
	- Password protection
	- Multi Factor Authentication
		- Virtual MFA(authentication apps)
		- U2F (Universal 2nd Factor )Security Key  {ex - yubi key}
		- Hardware TOTP(physical pager kind of devices that work the same as authentication apps )

`IAM Roles for Services`
To give Permissions to AWS services to perform actions on our behalf and access other services allowed we will provide permission to that service through ***IAM*** user access

`IAM Guidlines & Best Practices`
- Don't use the root account except for AWS account Setup
- One physical user = One AWS user
- ***Assign users to groups*** and assign permissions to groups
- create a ***strong password policy***
- Use and enforce the use of ***Multi Factor Authentications(MFA)***
- Create and use ***Roles*** for giving permissions to AWS services
- Use Access Keys for Programmatic Access(CLI/SDK)
- Audit permissions of your account using IAM Credentials Report & IAM Access Advisory
- ***Never share IAM user & Access Key*** 


