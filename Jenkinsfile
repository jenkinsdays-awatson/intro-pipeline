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
    stage('Deploy') {
      input {
        message 'Should we continue?'
      }
      steps {
        echo 'Continuing with deployment'
      }
    }
  }
  environment {
    MY_NAME = 'Adam'
  }
  parameters {
    string(name: 'Name', defaultValue: 'whoever you are', description: 'Who should I say hi to?')
  }
}