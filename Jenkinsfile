pipeline {
  agent any
   environment {

    PATH = "C:\\Windows\\System32"

    }
  stages {
    stage('version') {
      steps {
        bat 'python --version'
        echo "PATH is: ${env.PATH}"
      }
    }

    stage('hello') {
      steps {
        bat 'python hello.py'
      }
    }
//        stage('Example Deploy') {
//             when {
//                 branch 'production'
//                 environment name: 'DEPLOY_TO', value: 'production'
//             }
//             steps {
//                 echo 'Deploying'
//             }
//         }
  }
}