## IAM: Users & Groups

> IAM = Identity and Access Management, Global service

- **Root account** created by default, shouldn't be used or shared
- **Users** are people within your organization, and can be grouped
- **Groups** only contain users, not other groups
- Users don't have to belongs to a group, and user can belong to muliple groups

## IAM: Permissions

- **Users or Groups** can be assigned custom policies (in JSON format), these policies define the **permissions** of the users.
- In AWS you appply the **least privilege principle**, don't give more permissions than a user needs.
> ![IAM Policies inheritance](/2.IAM/iam-permission.png)

## IAM Policies Structure
- Consists of
    - **Version**: policy language version, always include "2012-10-17".
    - Id: an identifier for the policy (optional)
    - **Statement**: one or more individual statements (required).
- Statements consists of
    - Sid: an identifier for the statement (optional)
    - **Effect**: whether the statement allows or denies access (Allow, Deny)
    - **Principla**: account/user/role to which this policy applied to
    - **Action**: list of actions this policy allows or denies
    - **Resource**: list of resources to which the actions applied to
    - Condition: conditions for when this policy is in effect (optional)

![Sample Policy](/2.IAM/iam-policies-structure.png)