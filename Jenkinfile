pipeline {
    agent any
    stages {
        stage('Build Application') {
            steps {
                sh 'nvn -f pom.xml clean package'
            }
            post {
                success {
                    echo 'Now Archiving the Artifact'
                    archiveArtifact artifacts: '**/*.war'
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