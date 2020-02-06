pipeline {
    agent any
    stages {
        
       stage ('checkout') {
        steps {
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'git_mulesoft', url: 'git@github.transurban.com:Dpal/billing-1.0.0-snapshot-mule-application.git']]])
        }
       }
        stage ('Package Stage') {

            steps {
                withMaven(maven : 'apache-maven-3.5.4') {
                    sh 'mvn clean package'
                }
            }
        }
        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'apache-maven-3.5.4') {
                    sh 'mvn test'
                }
            }
        }
        stage ('Deploy Stage') {
            steps {
                withMaven(maven : 'apache-maven-3.5.4') {
                    sh 'mvn deploy  -DmuleDeploy'
                }
            }
        }
    }
}
