pipeline {
    agent any

    stages {
        stage ('checkout'){
              steps{
                checkout scm
              }
        }

        stage('npm-install') {
            steps {
                echo "Branch is ${env.BRANCH_NAME}..."

                withNPM() {
                    echo "Performing npm build..."
                    sh 'npm install'
                }
            }
        }

        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }

        stage ('clean up') {
              steps{
                echo 'Cleaning up..'
                sh 'rm -rf node_modules'
              }
        }
    }
}