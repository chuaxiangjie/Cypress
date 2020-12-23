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
    > Make sure you already have a package.json file in the above target path before installing cypress package

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






## Sonarqube project (Scan)

#### Scan .Net project



```diff
#### Navigate to .Net project root directory


dotnet sonarscanner begin /k:"NumberGenerator" /d:sonar.cs.nunit.reportsPaths=C:\Users\ran_d\source\repos\NumberGenerationNew\Tests\**\TestResults\TestResults.xml /d:sonar.cs.opencover.reportsPaths=C:\Users\ran_d\source\repos\NumberGenerationNew\Tests\**\Coverage\*.opencover.xml


Parameters explain
- /k:"NumberGenerator" - refer to sonarqube project name
- /d:sonar.cs.nunit.reportsPaths - specify Nunit unit tests result
- /d:sonar.cs.opencover.reportsPaths - specify Nunit unit tests coverage

```

```
#### Build solution

dotnet build NumberGenerator.sln

```


```
#### Execute test to generate test results/coverage files

dotnet test --logger "trx;LogFileName=TestResults.trx" ^            --logger "nunit;LogFileName=TestResults.xml" ^            --results-directory ./Coverage ^            /p:CollectCoverage=true ^            /p:CoverletOutput=Coverage\ ^            /p:CoverletOutputFormat=opencover ^            /p:Exclude="[nunit.*]*

```

```
#### Sonarscan end

dotnet sonarscanner end

```
