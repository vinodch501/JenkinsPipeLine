pipeline {
    agent any
   
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                    echo "Genrating WAR file"
                '''
            }
        }

        stage ('Build') {
            steps {
                sh 'mvn clean install package' 
            }
                    }
        stage('Deploy to Tomcat'){
            steps(['tomcat-dev']) {
         sh 'sudo scp -o StrictHostKeyChecking=no target/*.war root@35.223.149.81:/opt/tomcat/tomcat/webapps/'
      }
   }
    }
}
