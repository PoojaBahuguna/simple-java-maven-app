pipeline {
    
    agent {
        label 'master'
    }
    tools {
            maven 'mvn-3.6.0'
        }

    stages {

    stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
    
    stage('Test') {
          steps {
              sh 'mvn test'
          }
          post {
              always {
                  junit 'target/surefire-reports/*.xml'
              }
          }
    	}
   }
}
