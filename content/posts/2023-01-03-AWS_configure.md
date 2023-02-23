+++
author = 'Jesse Lima'
title = "15 AWS Configure Command Examples to Manage Multiple Profiles for CLI"
tags = ["AWS", "cli", "config"]
date = "2023-01-03"
category = ["reference", "commands", "tech"]
+++


To use AWS CLI, you need to first make sure your AWS access key credentials are configured properly.

Once you have your AWS access_key_id and secret_access_key, you can either manually add them to the credentials file, or use aws configure command to set it up on your local machine.

This tutorials explains all the options available in aws configure command along with how to manage multiple profiles:

First Time Configuring AWS Credentials – Default Profile
~/.aws Directory – Config and credentials File for Default Profile
Edit Default Profile Credentials – Connect to Different AWS Account
Create Multiple AWS Profiles – Dev and Prod
~/.aws Directory – Config and credentials File for Multiple Profiles (Dev and Prod)
Switching Between Different AWS Profiles using –profile Option
Switching Between Different AWS Profiles using AWS_PROFILE Env Variable
View Profile Information using list Option
Change Default Config and Credentials FileName and Location
View a Specific Profile Parameter Value using get Option
Set a Specific Profile Parameter Value using set Option
Add New Model using add-model Option

1. First Time Configuring AWS Credentials – Default Profile
When you execute aws configure command without any argument, you’ll be configuring aws credentials as your default profile.

$ aws configure
AWS Access Key ID [None]: AAABBBCCCDDDEEEFFFGG
AWS Secret Access Key [None]: aaabbbcccdddeeefffggghhhiiijjjkkklllmmmn
Default region name [None]: us-east-1
Default output format [None]: text
In the above:

[None] – This indicates that you don’t have any existing access-key-id/secret-access-key setup on your system for default profile, and will prompt you for new values.
Region Name – This is optional. If you leave this empty, you should specify region in all your AWS CLI commands using –region parameter, else you’ll get an error message.
Output – This is optional. If you leave this empty, the output of all AWS CLI will be in json format. Available output options are: json, text, table


Create Multiple AWS Profiles – Dev and Prod
When you are connecting to multiple AWS account just using the default profile, you’ve to keep changing the values of access_key_id and secret_access_key, which is not practical.

In that case, you can create multiple profiles.

Let us say you need to use AWS CLI commands to access your AWS-dev account and AWS-prod account. In this case, create a dev profile and a prod profile as explained below.

First, create dev profile as shown below. Use access_key_id and secret_access_key values of your AWS-dev account:

$ aws configure --profile dev
AWS Access Key ID [None]: DEVBBBCCCDDDEEEFFDEV
AWS Secret Access Key [None]: devbbbcccdddeeefffggghhhiiijjjkkklllmdev
Default region name [None]: us-east-1
Default output format [None]:
Next, create prod profile as shown below. Use access_key_id and secret_access_key values of your AWS-prod account:

$ aws configure --profile prod
AWS Access Key ID [None]: PRODBBCCCDDDEEEFPROD
AWS Secret Access Key [None]: prodbbcccdddeeefffggghhhiiijjjkkklllprod
Default region name [None]: us-west-2
Default output format [None]:


6. Switching Between Different AWS Profile using –profile Option
By default, AWS CLI will use credentials from default profile. For example, the following command will list all the EBS volumes using your default profile credentials.

aws ec2 describe-volumes
If you want to connect to a different AWS account. For example to connect to AWS-dev account, use the dev profile as shown below:

aws ec2 describe-volumes --profile dev
The following will connect to prod profile:

aws ec2 describe-volumes --profile prod
Please note that the following commands are exactly the same. Both will use the default profile:

aws ec2 describe-volumes

aws ec2 describe-volumes --profile default

7. Switching Between Different AWS Profiles using AWS_PROFILE Env Variable
Specifying profile option in all your CLI can be bit cumbersome. To avoid this, you can set your profile using AWS_PROFILE environment variable.

First, set your AWS_PROFILE to connect to AWS-dev account.

export AWS_PROFILE=dev
From now on, any AWS CLI commands that you execute will connect to the AWS-dev account. You don’t need to specify –profile option anymore.

The following commands will use dev profile credentials (not the default credentials), as we’ve set the AWS_PROFILE to dev.

View Profile Information using list Option
The easy way to view all the profiles that you’ve configured on your system is to view the content of config and credentials files.

cat ~/.aws/config

cat ~/.aws/credentials
The list option in the aws configure command will display the information about the current profile as shown below.