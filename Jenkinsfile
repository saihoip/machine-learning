pipeline {
  agent any
  parameters {
    string(name: "VERSION", defaultValue: "", description: "version to deploy on prod")
    choice(name: "VERSION", choices: ["1.0.0", "1.1.0", "1.2.0"], description: "")
    booleanParam(name: "execteTests", defaultValue: true, description: "")
  }
  environment {
    NEW_VERSION = "1.3.0"
    SERVER_CRENDENTIALS = credentials("server-credentials")
  }
  stages {
        stage('Build') {
            steps {
                echo 'Building..'
                nodejs('Node-10.17') {
                    sh 'yarn install'
                }
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}