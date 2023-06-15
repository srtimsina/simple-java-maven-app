pipeline {
    agent any
    stages {
        stage('UnitTest') {
            steps {
                echo "Hello, we are learning Jekins pipeline as a code"
                echo "Running Unitest"
            }
        }
        stage('Build') {
            steps {
                echo "Building the code"
                sh 'pwd'
                sh 'mvn -f pom.xml clean install'

                post {
                success {
                    echo "Now Archiving the Artifacts...."
                    archiveArtifacts artifacts: '**/*.jar'
                }
            }
            }
        }
        stage('DeployStaging') {
            steps {
                echo "Deploying to staging env"
            }
        }  
        stage('DeployProd') {
            steps {
                echo "Deploying to prod env"
            }
        }    
    }
}
