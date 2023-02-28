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
	    echo "#####Copying Global property file to src\\main\\resources#####"
        bat "powershell Copy-Item ${SECRET_FILE_ID} -Destination src\\main\\resources"

        echo "#####Deleting Local Global property file present in src\\main\\resources#####"
        bat "powershell Remove-Item src\\main\\resources\\global-dev.properties"

        echo "#####Renaming Global property file in Jenkins to global-dev.properties#####"
        bat "powershell Rename-Item src\\main\\resources\\secret_file_jenkins global-dev.properties"

        echo "#####Creating Mule Application artifact#####"
        bat 'mvn clean install'
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