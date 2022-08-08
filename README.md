# Create a dist of this project
1. Run "npm install" and "npm run build".
2. Create a zip of dist.
3. Push that zip to either on s3 or keep it in local.

# Deploy to AWS Amplify Console
Go to https://aws.amazon.com/amplify/console/ to get started.
1. Create a hosting web app on amplify.
2. Choose any mention method you want for uploading the zip on amplify.
3. Provide the App name and Environment Name 
4. Click on save and deploy.

# Deploy to AWS Amplify using aws-cli
Install the cli from here as per respective os https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html
1. Create a hosting web app on amplify:
    aws amplify create-app --name <projectName>
2. Create a environment name on that created app:
    aws amplify create-branch --app-id <appId> --branch-name <branchName>
3. Deploy created zip on amplify using aws cli:
    aws amplify start-deployment --app-id <appId> --branch-name <branchName> --source-url "<s3bucket url>"
    
