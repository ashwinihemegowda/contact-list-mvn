pipeline {

    agent any
    

    tools {
        maven "Maven"
    }

    environment {
        NEXUS_VERSION = "nexus3"
        NEXUS_PROTOCOL = "http"
        NEXUS_URL = "52.66.252.13:8081"
        NEXUS_REPOSITORY = "maven-nexus-repo"
        NEXUS_CREDENTIAL_ID = "nexus-user-credentials"
    }

    stages {

        stage("Clone code from VCS") {
            steps {
                script {
                   git branch: 'nexus-poc', url: 'https://github.com/sshelake25/contact-list-mvn.git'
                }
            }
        }

        stage("Maven Build") {
            steps {
                script {
                    sh "mvn package -DskipTests=true"
                }
            }
        }

        stage("Publish to Nexus Repository Manager") {
            steps {
                script {
                   echo "Hello World"
                }
            }
        }
    }
}