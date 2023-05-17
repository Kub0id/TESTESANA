pipeline {
    agent any

    stages {
        stage('install-pip-deps') {
            steps {
                echo 'Installing all required depdendencies..'
                powershell 'git clone https://github.com/mtararujs/python-greetings'
                powershell 'git clone https://github.com/mtararujs/course-js-api-framework'
                powershell 'ls python-greetings'
                powershell 'pip install -r python-greetings/requirements.txt'
            }
        }
      stage('deploy-to-dev') {
            steps {
                echo 'Deploying-to-dev'
                powershell 'pm2 start python-greetings/app.py --name greetings-app-dep-dev -p 7001'
                powershell 'pm2 delete all'
                powershell 'npm install ".\course-js-api-framework\"'
                powershell 'npm run --prefix course-js-api-framework greetings greetings_dev'
            }
        }
      stage('tests-on-dev') {
            steps {
                echo 'Testing-on-developments'
                powershell 'pm2 start python-greetings/app.py --name greetings-app-test-dev -p 7001'
                powershell 'pm2 delete all'
            }
        }
        stage('tests-on-staging') {
            steps {
                echo 'Testing-on-staging'
                powershell 'pm2 start python-greetings/app.py --name greetings-app-test-dev-on-stg -p 7002'
                powershell 'pm2 delete all'
            }
        }
      stage('deploy-to-preprod') {
            steps {
                echo 'Das-ist-staging-grounds'
                powershell 'pm2 start python-greetings/app.py --name greetings-app-staging-dep -p 7002'
                powershell 'pm2 delete all'
            }
        }
      stage('tests-on-preprod') {
            steps {
                echo 'Preproduction-on-testing'
                powershell 'pm2 start python-greetings/app.py --name greetings-app-test-preprod -p 7003'
                powershell 'pm2 delete all'
            }
        }
      stage('deploy-to-prod') {
            steps {
                echo 'Deploying-to-productions'
                powershell 'pm2 start python-greetings/app.py --name greetings-app-dep-prod -p 7004'
                powershell 'pm2 delete all'
            }
        }
      stage('tests-on-prod') {
            steps {
                echo 'Testing-FINAL-production'
                powershell 'pm2 start python-greetings/app.py --name greetings-test-prod -p 7004'
                powershell 'pm2 delete all'
            }
        }
    }
}
