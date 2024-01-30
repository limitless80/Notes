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