pipeline {
    agent none
        stages {
            stage ('Cloning a repository') {
                agent {label 'slave01'}
                steps {
                    git 'https://github.com/sumana4197/jenkins-pipeline.git'
                    echo "cloning is successfull"
                }
            }
            stage ('build the artifact is successfull') {
                agent {label 'slave01'}
                steps {
                    sh 'mvn clean install'
                    echo "building the artifact is successfull"
                }
            }
            stage ('deploying the artifact to tomcat') {
                agent {label 'slave01'}
                steps { 
                    sh 'cp /home/ubuntu/.m2/repository/com/datica/java-war-deploy-example/0.1-SNAPSHOT/java-war-deploy-example-0.1-SNAPSHOT.jar /home/ubuntu'
                    echo "deploying is successfull"
                }
            }
            stage ('testing the source code') {
                agent {label 'slave01'}
                steps {
                    echo "testing is successfull"
                }
            }
        }
    }
