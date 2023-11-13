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
    stage("build") {
      steps {
        echo "building the application..."
        echo "building version ${NEW_VERSION}"
      }
      stage("test") {
        when {
          expression {
            params.execteTests == true
          }
        }
        steps {
          echo "testing the application..."
        }
      }
      stage("deploy") {
        steps {
          echo "deploying the applications..."
          echo "deploying version ${params.VERSION}"
        }
      }
    }
  }
}
