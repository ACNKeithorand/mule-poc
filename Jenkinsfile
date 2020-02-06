pipeline {
    agent any
    stages {
        
       stage ('checkout') {
        steps {
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '4d607dee-b679-47f0-9cb5-30e182c800b7', url: 'git@github.transurban.com:ACNKeithorland/mule-poc.git']]])
        }
       }
        stage ('Package Stage') {

            steps {
                withMaven(maven : 'apache-maven-3.5.3') {
                    sh 'mvn clean package'
                }
            }
        }
        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'apache-maven-3.5.3') {
                    sh 'mvn test'
                }
            }
        }
        stage ('Deploy Stage') {
            steps {
                withMaven(maven : 'apache-maven-3.5.3') {
                    sh 'mvn deploy  -DmuleDeploy'
                }
            }
        }
    }
}
