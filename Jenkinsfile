pipeline {
    agent {
        docker {
            image 'node:6-alpine'
            args '-p 3000:3000'
        }
    }
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
			agent {
                docker {
                image 'mysql/mysql-server'
                args '--name test -e MYSQL_ROOT_PASSWORD=root -d'}
            }
            steps {
                sh 'npm run test'
            }
        }
    }
}
