# How to add AWS Cross Account Role

When adding an AWS Cross Account Role, you're enabling one AWS account to access resources in another AWS account. This is crucial for managing resources across different accounts efficiently. Here's a step-by-step guide on how to set this up:

## 1. Select a trusted entity 

Go to IAM roles and create roles, in the create roles we will have AWS account which needs to be selected.

Example:

![TrustedEntity](/docs/images/trusted-entity.png)

## 2. Add an AWS account

After selecting the AWS account option enter OpsBeacon AWS account id:

Example:

![RunParser](/docs/images/aws-account.png)

## 3. Attach a policy

After that attach any policy/permissions you want. For example to provide AWS SSM RunCommand permission on a specific instance id:

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "ssm:SendCommand"
            ],
            "Resource": [
                "arn:aws:ssm:us-east-1::document/AWS-RunShellScript",
                "arn:aws:ec2:us-east-1:<youraccountid>:instance/<instanceid>"
            ]
        },
        {
            "Effect": "Allow",
            "Action": [
                "ssm:ListCommands",
                "ssm:ListCommandInvocations"
            ],
            "Resource": "*"
        }
    ]
}
```

## 4. Giving role name

> **Important!** Give your role OpsBeaconCrossAccountRole name. This is important - don't change this name.

Example:

![RoleName](/docs/images/role-name.png)

Review the settings and policies attached to the role. Once confirmed, click "Create role" to finalize.

## 5. Role ARN

Copy the role ARN

Example:

![RoleARN](/docs/images/role-arn.png)
