pipeline {
    agent any

    stages {
        stage('npm-install') {
            steps {
                echo "Branch is ${GIT_BRANCH}..."
                echo "Performing npm build..."
                bat 'npm install'
            }
        }

        stage('Build') {
            steps {
                echo 'Building..'
                bat 'npm run-script prodbuild'
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
                bat 'rmdir /q/s node_modules'
              }
        }
    }

    post {
      success {
        mail to: 'test@example.com', subject: 'The Pipeline failed', body: '${BUILD_URL}'
      }
    }

}
