#S3 Transfer Manager Demo

###Set up Cognito
First we will need to set up Cognito, which is the recommended way of 
providing authentication. Do this through the AWS Console. Download or copy the starter code that it will output.

###Set up permissions
Now that you've set up Cognito, we need to set up the IAM permissions.

1. Go to https://console.aws.amazon.com/iam/home
2. Select Roles
3. Select the appropriate unauthenticated role from your identity pool
4. Select attach role policy, under the permissions tab
5. Find S3 full access, and attach it to the role.
6. Take note of the "Role ARN" under the "Summary" tab; we'll need this later

###Setting up the project
You'll need to set up the project for your environment. If you are going to
build the project from command line, run the command

    android update project -p <path_to_project> -t android-10

assuming android is already in your path. If not, you can find it in
"<path_to_sdk>/tools".

###Changing Constants
Before you try to compile the app, you'll first need to change the values in
com.amazonaws.demo.s3_transfer_manager.Constants to match the things on your
specific AWS account. 

Change all of these to be the corresponding values on your account

    public static final String AWS_ACCOUNT_ID = "YOUR_ACCOUNT_ID";
    public static final String COGNITO_POOL_ID = 
            "YOUR_COGNITO_POOL_ID"
    public static final String COGNITO_ROLE_UNAUTH = 
            "YOUR_COGNITO_ROLE_UNAUTH";
    public static final String BUCKET_NAME = "YOUR_BUCKET_NAME";

###Compiling
Now that you have done all of that, you can compile the app. To do this from the
command line, just run

    ant debug

from the root project directory, assuming you have ant installed. After 
compiling, you can install by running

    ant installd

also from the root directory. You can do compile and install all at once with

    ant debug install

as well.
