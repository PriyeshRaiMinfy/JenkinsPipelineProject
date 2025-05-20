# Jenkins Pipeline Project - HelloJenkins
This project showcases a simple CI/CD pipeline configured using Jenkins. The goal is to demonstrate how to create, run and visualize a Jenkins pipeline with basic stages : Build, Test, Deploy and Cleanup.

## Jenkins dashboard
- Open Jenkins via `https://localhoast:8080`
- login
- **Dashboard** -> **Build Queue** -> **Build Executor Status**

--- Jenkins Dashboard
![Jenkins Dashboard before Job Creation](<screenshots/Dashboard.png>)
--- Console Output Before Job Creation
![Console Output Before Job Creation](<screenshots/ConsoleOutput_Before.png>)

```
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
                sh 'sleep 5' // Simulate build time
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'sleep 3' // Simulate test time
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                sh 'sleep 2' // Simulate deployment
            }
        }
        stage('Cleanup') {
            steps {
                echo 'Cleaning up...'
                sh 'sleep 1'
            }
        }
    }
    post {
        success {
            echo 'Pipeline executed successfully!'
        }
        failure {
            echo 'Pipeline execution failed!'
        }
    }
}
```


--- Stage View
![Stage View](<screenshots/StageView.png>)


--- Status
![Status](<screenshots/Status.png>)


--- Console Output After creating the Job
![Console Output After creating the Job](<screenshots/ConsoleOutput_After.png>)


--- Jenkins Dashboard After Job Creation
![Jenkins Dashboard After Job Creation](<screenshots/Dashboard_AfterJobCreation.png>)

--- Stages
![Stages](<screenshots/Stages.png>)

