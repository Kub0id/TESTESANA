pipeline {
    agent any

    stages {
        stage('install-pip-deps') {
            steps {
                echo 'Installing all required depdendencies..'
                powershell 'git clone https://github.com/mtararujs/python-greetings'
                powershell 'ls python-greetings'
                //powershell 'pip install -r python-greetings\requirements.txt'
            }
        }
      stage('deploy-to-dev') {
            steps {
                echo 'Deploying to dev'
                powershell 'git clone https://github.com/mtararujs/python-greetings'
                powershell 'pm2 delete greetings-app-install-pip-deps & set "errorlevel=0"'
            }
        }
      stage('tests-on-dev') {
            steps {
                echo 'Testing on developments'
                powershell 'git clone https://github.com/mtararujs/python-greetings'
                powershell 'pm2 delete greetings-app-install-pip-deps & set "errorlevel=0"'
            }
        }
      stage('deploy-to-staging') {
            steps {
                echo 'Das ist staging grounds'
                powershell 'git clone https://github.com/mtararujs/python-greetings'
                powershell 'pm2 delete greetings-app-install-pip-deps & set "errorlevel=0"'
            }
        }
      stage('tests-on-preprod') {
            steps {
                echo 'Preproduction on testing'
                powershell 'git clone https://github.com/mtararujs/python-greetings'
                powershell 'pm2 delete greetings-app-install-pip-deps & set "errorlevel=0"'
            }
        }
      stage('deploy-to-prod') {
            steps {
                echo 'Deploying to productions'
                powershell 'git clone https://github.com/mtararujs/python-greetings'
                powershell 'pm2 delete greetings-app-install-pip-deps & set "errorlevel=0"'
            }
        }
      stage('tests-on-prod') {
            steps {
                echo 'Testing FINAL production'
                powershell 'git clone https://github.com/mtararujs/python-greetings'
                powershell 'pm2 delete greetings-app-install-pip-deps & set "errorlevel=0"'
            }
        }
    }
}
