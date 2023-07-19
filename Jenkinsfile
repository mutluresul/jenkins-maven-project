pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'mvn -f hello-app/pom.xml clean install'
            }
            post {
                success {
                    echo "Now Archiving the Artifacts really....."
                    archiveArtifacts artifacts: '**/*.jar'
                }
            
                always {
                    junit 'hello-app/target/surefire-reports/*.xml'
                }
            }
            }
        }
    }