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
				withCredentials([string(credentialsId: 'jenkins-database-username', variable: 'root')]) {
                        withCredentials([string(credentialsId: 'jenkins-database-password', variable: 'root')]) {
                            def test_database_credentials = buildTestMySQLDatabase {
                                dbUser = env.DATABASE_USERNAME
                                dbPass = env.DATABASE_PASSWORD
                            }
                            echo 'Test Database Name: ' + test_database_credentials.dbName
                            echo 'Test Username: ' + test_database_credentials.testUsername
                            echo 'Test User Password: ' + test_database_credentials.testUserPassword
                        }
                }
            }
        }
        stage('Test') {
            steps {
                sh 'npm run test'
            }
        }
    }
	post {
        always {
            destroyTestMySQLDatabase {
                dbUser = credentials('jenkins-database-username')
                dbPass = credentials('jenkins-database-password')
            }
        }
    }
}
