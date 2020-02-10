pipeline {
    agent any
    stages {
        
        stage ('Package Stage') {

            steps {
                withMaven(maven : 'apache-maven-3.5.3') {
                    sh 'mvn clean package'
                }
            }
        }
        
    }
}
