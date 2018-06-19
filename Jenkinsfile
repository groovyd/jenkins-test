pipeline {
    agent any
    
	environment {
        DISABLE_AUTH = 'true'
        DB_ENGINE    = 'sqlite'
    }
	
	stages {
        stage('build') {
            steps {
                bat 'python --version'
                bat 'env'
            }
        }
    }
	
	post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
            mail to: 'daryl.fortney@keysight.com',
              subject: "Localhost Jenkins SUCCESS",
              body: "Woot!"
        }
        failure {
            echo 'This will run only if failed'
        }
        unstable {
            echo 'This will run only if the run was marked as unstable'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
    }
}
