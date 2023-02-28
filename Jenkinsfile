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
        SECRET_FILE_ID = withCredentials('secret-file-id')
        }
      steps {
        echo "####DISPLAYING SECRET_FILE_ID####"
	    echo "Global property file: ${SECRET_FILE_ID}"
	    echo "Global property file: ${SECRET_FILE_ID.USER_PASSWORD}"
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
//  script {
//                     def credentials = readCredentialsFile(file: '/path/to/secret/file')
//                     def username = credentials.username
//                     def password = credentials.password
// SECRET_FILE_ID = credentials('secret-file-id')
                    // use the username and password variables as needed

//                     environment {
//         // define variables to store the secret values
//         SECRET_USERNAME = ""
//         SECRET_PASSWORD = ""
//     }
//
//     stages {
//         stage('Get secret values') {
//             steps {
//                 // use the withCredentials step to get the secret values
//                 withCredentials([file(credentialsId: 'my-secret-file', variable: 'SECRET_FILE')]) {
//                     SECRET_USERNAME = sh(script: "cat ${SECRET_FILE} | grep -oP 'username=\\K.*'", returnStdout: true).trim()
//                     SECRET_PASSWORD = sh(script: "cat ${SECRET_FILE} | grep -oP 'password=\\K.*'", returnStdout: true).trim()