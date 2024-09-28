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

### Explaination- Policies Inheritance
- Alice, Bob, Charles are in **Developers** group
- Charles, David are in **Audit Team** group
- David, Edward are in **Operations** group
- Fred is not in a group

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

## IAM - Password Policy
- You can setup a password policy:
    - Set a minimum password length
    - Require specific character types:
        -  including uppercase letters
        - lowercase letters
        - numbers
        - non-alphanumeric characters
    - Allow all IAM users to change their own passwords
    - Require users to change their password after some time (password expiration)
    - Prevent password re-use

## Multi Factor Authentication - MFA
- Users have access to your account and can possibly change configurations or delete resources in your AWS acccount.
- You want to protect your Root Accounts and IAM users
- MFA = your password + security device you own (could be your phone)
- > **Ismael**: password + MFA => Successful login
- Main benefit of MFA: if a password is stolen or hacked, the account is not compromised.

**Examples of Virtual MFA device**: Support for multiple tokens on a single-device.
- Google Authenticator
- Microsoft Authenticator
- Authy

**Universal 2nd Factor(U2F) Security Key**: Support for multiple root and IAM users using a single security key
- **YubiKey** by Yubico (3rd party)

**MFA devices options in AWS**
- Hardware Key Fob MFA Device by Gemalto (3rd party)
- Hardware Key Fob MFA Device for AWS GovCloud(US) by SurePassID (3rd party)

## How can users access AWS?
- To access AWS, you have three options:
    - **AWS Management Console** (protected by password + MFA)
    - **AWS Command Line Interface (CLI)**: protected by access keys
    - **AWS Software Developer Kit (SDK)** - for code: protected by access keys
- Access Keys are generated through the AWS Console
- Users manage their own access keys
- Access Key Id ~= username
- Secret Access Key ~= passwoed
> Don't share them.

