pipeline {
    agent any

    environment {
        PROJECT_DIR="my-app"
    }
    stages {
   
          stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/ahamedmm/JenkinsDemo.git'
            }
        }
        stage('Install Python Dependencies') {
            steps {
                bat 'python -m pip install --upgrade pip'  // Ensure pip is up-to-date
                bat 'pip install -r requirements.txt'
            }
        }
        

        stage('Run App') {
            steps {
                bat 'python app.py'
            }
        }

        stage('Archive Artifacts') {
            steps {
                archiveArtifacts artifacts: '**/*.py', fingerprint: true
            }
        }
    }
}


    


