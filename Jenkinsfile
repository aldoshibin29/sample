pipeline {
  agent any

  stages {
    stage('version') {
      steps {
        bat 'Python 3.9.13'
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