pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/diwakar237/sep17_3.git'
            }
        }
        stage ('Parallel Checks') {
            parallel {
                stage('Frontend Check') {
                    steps {
                        bat '"C:\\Users\\lekha\\AppData\\Local\\Programs\\Python\\Python312\\python.exe" frontend_check.py'
                    }
                }
                stage('Backend Check') {
                    steps {
                        bat '"C:\\Users\\lekha\\AppData\\Local\\Programs\\Python\\Python312\\python.exe" backend_check.py'
                    }
                }
            }
        }
        stage('Summary') {
            steps {
                echo 'Both frontend and backend checks are complete.'
            }
        }
    }
}
```[cite: 1]

Copy this entire block, replace the contents of your `Jenkinsfile` with it, and push the changes to GitHub. When you click **Build Now** in Jenkins, it will bypass the system settings and use the exact location of your Python installation directly.
