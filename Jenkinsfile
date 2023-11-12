pipeline {
  agent any
  environment {
    NEW_VERSION = "1.3.0"
    SERVER_CRENDENTIALS = credentials("server-credentials")
  }
  stages {
    stage("build") {
      steps {
        echo "building the application..."
        echo "building version ${NEW_VERSION}"
      }
      stage("test") {
        steps {
          echo "testing the application..."
        }
      }
      stage("deploy") {
        steps {
          echo "deploying the applications..."
          echo "deploying with ${SERVER_CRENDENTIALS}"
          sh "${SERVER_CRENDENTIALS}"
        }
      }
  }
}
