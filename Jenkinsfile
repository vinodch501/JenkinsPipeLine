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
        
    }
}
