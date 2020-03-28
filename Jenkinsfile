pipeline {
    agent any
        stages {
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
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
         sh 'sshpass -p Jenkins scp -o StrictHostKeyChecking=no webapp/target/*.war root@35.223.149.81:/opt/tomcat/tomcat/webapps/'
      }
   }
    }
}
