pipeline {
  agent any

  stages {
    stage('version') {
      steps {
        bat 'python --version'
      }
    }

    stage('hello') {
       environment {
        SECRET_FILE_ID = credentials('secret-file-id')
        }
      steps {
        echo "####DISPLAYING SECRET_FILE_ID####"
	    echo "Global property file: ${SECRET_FILE_ID}"
	    echo '''+USER_PASSWORD+'''
	    echo ${USER_PASSWORD}

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