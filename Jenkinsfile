pipeline {
    agent any

    tools {
        maven 'MVN_HOME'     // Jenkins Maven tool name configured under "Global Tool Configuration"
    }

    stages {

        stage('Git Clone') {
            steps {
                echo "Cloning the Git repository..."
                git branch: 'main', url: 'https://github.com/sravandevops09/hiring-app.git'
            }
        }

        stage('Maven Compilation') {
            steps {
                echo "Running Maven build..."
                sh 'mvn clean compile'
            }
        }
    }

    post {
        success {
            echo "✅ Build completed successfully!"
        }
        failure {
            echo "❌ Build failed. Please check logs!"
        }
    }
}
