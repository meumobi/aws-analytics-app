# FUP

## 20220701 #1

I'm [setting up an AWS backend and integrating that backend with your Angular web app](https://docs.amplify.aws/start/q/integration/angular/):

- Bootstrap a new Angular app
- Add Angular 6+ Support
- Create new Amplify backend
- Install Amplify libraries

```sh
% amplify init
Note: It is recommended to run this command from the root of your app directory
? Enter a name for the project awsanalyticsapp
The following configuration will be applied:

Project information
| Name: awsanalyticsapp
| Environment: dev
| Default editor: Visual Studio Code
| App type: javascript
| Javascript framework: angular
| Source Directory Path: src
| Distribution Directory Path: dist/aws-analytics-app
| Build Command: npm run-script build
| Start Command: ng serve

? Initialize the project with the above configuration? Yes
Using default provider  awscloudformation
? Select the authentication method you want to use: AWS profile

For more information on AWS Profiles, see:
https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-profiles.html

? Please choose the profile you want to use default
Adding backend environment dev to AWS Amplify app: d2rnhlk57o6wrv
⠋ Initializing project in the cloud...
...
%
```

### CommonJS dependencies

Current install raised a lot of warnings `CommonJS or AMD dependencies can cause optimization bailouts.`
To remove these warnings should [configure angular.json to allow commonJS dependencies](https://angular.io/guide/build#configuring-commonjs-dependencies).
I don't remember how it was [done automaticaly on previous project](https://github.com/meumobi/amplify-app/commit/1afd38ac0557085171095e1d07acbda511b60297?diff=split#diff-2d2675bb4687601a5c7ccf707455132f90f3516a33716185687e5c41df59ac7d).
