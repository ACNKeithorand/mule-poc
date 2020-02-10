pipeline {
    agent any
    stages {
        
        stage ('Package Stage') {

            steps {
                withMaven(maven : 'apache-maven-3.5.4') {
                    sh 'mvn clean package'
                }
            }
        }
        
    }
}
