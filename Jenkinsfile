pipeline {
  agent {
    label 'jdk8'
  }
  stages {
    stage('Hi') {
      steps {
        echo "Hello, ${params.Name}!"
        sh 'java -version'
      }
    }
    stage('Get Kernel') {
      steps {
        script {
          try {
            KERNEL_VERSION = sh (script: "uname -r", returnStdout: true)
          } catch(err) {
            echo "CAUGHT ERROR: ${err}"
            throw err
          }
        }

      }
    }
    stage('Say Kernel') {
      steps {
        echo "${KERNEL_VERSION}"
      }
    }
  }
  environment {
    MY_NAME = 'Adam'
  }
  post {
    aborted {
      echo 'Why didn\'t you push my button?'

    }

  }
  parameters {
    string(name: 'Name', defaultValue: 'whoever you are', description: 'Who should I say hi to?')
  }
}