pipeline {
    agent any
    stages {
        
        stage ('Package') {

            steps {
                withMaven(maven : 'apache-maven-3.5.4') {
					bat 'cd C:\Program Files (x86)\Jenkins\workspace\Mulesoft'
                    bat 'mvn clean package'
                }
            }
        }
        
    }
}

