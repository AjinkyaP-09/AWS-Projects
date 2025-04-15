# Deploy a sample React app using AWS Amplify

![](./images/Screenshot%202025-04-14%20172327.png)

## What is AWS Amplify?

AWS Amplify is a set of tools and services that makes it easy to build full-stack web and mobile apps, especially those that use serverless backends. It’s great for developers who want to quickly build and deploy scalable apps on AWS with minimal setup.

## What are we doing in this project?

We are creating a simple React based website that shows a message "Hello from AWS Amplify project of Ajinkya!!!" when we hit the domain.
The files are in the repo and you can just fork them and try on your end.

## Let's try AWS Amplify!!!

## Prerequisites:

1. AWS account
2. GitHub account
3. A basic React app (or any frontend project) on GitHub

## Steps to setup the app:

### Step-1:

- Create a basic React repo locally using
  `npx create-react-app amplify-test`
- Go to that directory
  `cd amplify-test`
- Run below command to run it
  `npm run start`
- Check the localhost:3000 on the browser to see the default react output
  ![](./images/Screenshot%202025-04-14%20171116.png)
- Modify src/App.js to view our custom message "Hello from AWS Amplify project of Ajinkya!!!"

```
import logo from './logo.svg';
import './App.css';

function App() {
  return (
    <div className="App">
      <h1>Hello from AWS Amplify project of Ajinkya!!!</h1>
    </div>
  );
}

export default App;
```

- Reload the localhost page to view this message
  ![](./images/Screenshot%202025-04-15%20093154.png)

### Step-2:

- Now our project is ready so push it to the github repository
- Run below commands one after other in the integrated terminal

```
git init
git remote add origin https://github.com/AjinkyaP-09/AWS-Projects.git
git add .
git commit -m "Initial commit"
git branch -M main
git push -u origin main
```

- I have put details as per my repo, you can put name as per your repository name.

### Step-3:

- Go to AWS Amplify dashboard using [AWS Amplify](https://console.aws.amazon.com/amplify)
  ![](./images/Screenshot%202025-04-14%20172327.png)
- Clcik on Deploy app.
- Choose source code provider as GitHub and click on next.
  ![](./images/Screenshot%202025-04-14%20172402.png)
- As soon as you click on next, it redirects to put GitHub account details.
- Put the details and give permissions to AWS Amplify to access your project repository.
- Choose project repository and when you come on "Add repository and branch" page select the repository.
- Select the branch.
- Tick "My repo is Monorepo" as our project is based on single folder.
- Enter the correct folder path in monorepo root directory, in my case my `package.json` is present at Project-3/apmlify-test so I have mentioned that path.
- Do the same, mention the path of the folder where `package.json` is present.
  ![](./images/Screenshot%202025-04-15%20090434.png)
- Click on next and go to "App settings".
- Enter App name.
- if you are seeing auto-detected framework as "React", then you are on correct path.
  If not then check your yml file looks something like this by clicking edit YML file:

```
version: 1
applications:
  - frontend:
      phases:
        preBuild:
          commands:
            - npm ci --cache .npm --prefer-offline
        build:
          commands:
            - npm run build
      artifacts:
        baseDirectory: build
        files:
          - '**/*'
      cache:
        paths:
          - .npm/**/*
    appRoot: Project-3/amplify-test
```

- Enter Frontend build command: npm run build
- Build output directory: build
  ![](./images/Screenshot%202025-04-15%20090454.png)
- Click on next to review settings and deploy the app.

### Step-4:

- After clicking on save and deploy, it will redirect to App Overview page and show the status as deploying.
- Wait for some time as it may take 2-3 minutes to build the app.
- Once the app is deployed, it will show status as deployed and a domain will be provided.
  ![](./images/Screenshot%202025-04-15%20091324.png)
- Open the domain to see the deployed app and our message.
  ![](./images/Screenshot%202025-04-15%20095737.png)
- In case of any failure while deployment or build, we can track build or deployment issues by clicking on main.

_In this way, we can deploy and test small apps using AWS Amplify_
