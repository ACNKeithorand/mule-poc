pipeline {
    agent any
    stages {
        
        stage ('Package') {

            steps {
                withMaven(maven : 'apache-maven-3.5.4') {
                    bat 'mvn clean package'
                }
            }
        }
        
    }
}

