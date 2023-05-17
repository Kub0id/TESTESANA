pipeline {
    agent any

    stages {
        stage('install-pip-deps') {
            steps {
                echo 'Installing all required depdendencies..'
            }
        }
      stage('deploy-to-dev') {
            steps {
                echo 'Deploying to dev'
            }
        }
      stage('tests-on-dev') {
            steps {
                echo 'Testing on developments'
            }
        }
      stage('deploy-to-staging') {
            steps {
                echo 'Das ist staging grounds'
            }
        }
      stage('tests-on-preprod') {
            steps {
                echo 'Preproduction on testing'
            }
        }
      stage('deploy-to-prod') {
            steps {
                echo 'Deploying to productions'
            }
        }
      stage('tests-on-prod') {
            steps {
                echo 'Testing FINAL production'
            }
        }
    }
}
