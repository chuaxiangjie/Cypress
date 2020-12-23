# Cypress with Angular

A modern javascript library that provides UI End-to-End Testing https://www.cypress.io/

## Getting Started

These instructions will get you a copy of the software and running on your local machine for development and testing purposes.

### Prerequisites

What things you need to install the software and how to install them

#### Windows Environment

1. Frontend + Backend Application

2. Install Cypress via npm: (***Skip this step for NumberGeneration project***)

In this example, i will be installing cypress package in my frontend (Angular) project

```
cd /frontend-project/ClientApp/e2e

npm install cypress --save-dev

```

| :memo:        | Make sure you already have a package.json file in the above target path before installing cypress package      |
|---------------|:------------------------|

For more information, please refer to the official website https://docs.cypress.io/guides/getting-started/installing-cypress.html#npm-install

Once installed, you should see the following files in node_modules folder

<img src="https://user-images.githubusercontent.com/5947398/102973374-92012b00-4537-11eb-82dd-9d39d92cf595.png" width="600" />


## Writing Test Cases

The following diagram illustrates the recommended cypress test project structure

I have included a regression spec.ts file which covers multiple test scenerios, eg. login, create numbermaster, create numberformats, generate number

<img src="https://user-images.githubusercontent.com/5947398/102974294-3e8fdc80-4539-11eb-9946-207bd7fb627b.png" width="600" />

For more information, please refer to the official website https://docs.cypress.io/guides/core-concepts/writing-and-organizing-tests.html#Configuring-Folder-Structure


## Execute End To End Testing

Before we start executing cypress e2e test, we need to start our backend and frontend applications.


#### Start Backend application

Navigate to backend .Net Core application 

```
dotnet run
```

#### Start Frontend application

Navigate to frontend Angular application 

```
dotnet run
```
Ensure both applications are running and working

In this example, the frontend application is running on http://localhost:5000

Now, we have a running UI application and we must configure cypress to include "baseUrl": "http://localhost:5000" in cypress.json file.

<img src="https://user-images.githubusercontent.com/5947398/102975731-7730b580-453b-11eb-9de3-2836c0eb99eb.png" width="600" />



| :memo:        | Cypress requires the target UI url address     |
|---------------|:------------------------|


#### Begin Cypress Test

Navigate to frontend Angular application 

```
cd /frontend-project/ClientApp/e2e
```

Open cypress Test runner

```
npx cypress open
```

<img src="https://user-images.githubusercontent.com/5947398/102989348-71919a80-4550-11eb-8166-62d4eaa16657.png" width="600" />

Click the Run 1 Integration Spec to begin

<img src="https://user-images.githubusercontent.com/5947398/102989536-bae1ea00-4550-11eb-91a8-a56d31d21096.png" width="600" />

Cypress test runner will automatically execute each test case.

