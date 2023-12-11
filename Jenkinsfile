pipeline {
    agent any
    stages {
        stage('Build Application') {
            steps {
                sh 'Mvn -f pom.xml clean package'
            }
            post {
                success {
                    echo 'Now Archiving the Artifact'
                    archiveArtifacts artifacts: '**/*.war'
                }
            }
        }

        stage('Test Application') {
            steps {
                echo 'Testing Application'
            }
        }

        stage('Nexus Deploy') {
            steps {
                echo 'Deploying Artifact to Nexus'
            }
        }
    }
}

