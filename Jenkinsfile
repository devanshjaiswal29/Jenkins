pipeline {
    agent any  // Run on any available Jenkins agent

    environment {
        DOTNET_ROOT = '/usr/share/dotnet' // Adjust if needed
    }

    stages {
        stage('Clone Repo') {
            steps {
                // Jenkins auto-clones your repo, so this is optional
                echo 'Cloning repository...'
            }
        }

        stage('Install Frontend Dependencies') {
            steps {
                dir('frontend') {
                    echo 'Installing frontend packages...'
                    bat 'npm install'
                }
            }
        }

        stage('Build Frontend') {
            steps {
                dir('frontend') {
                    echo 'Building frontend...'
                    bat 'npm run build'
                }
            }
        }

        stage('Build Backend') {
            steps {
                dir('backend') {
                    echo 'Building backend...'
                    bat 'dotnet build'
                }
            }
        }

        stage('Run Tests') {
            steps {
                echo 'No tests yet'
                // Add npm test or dotnet test here
            }
        }

        // Optional
        stage('Deploy') {
            steps {
                echo 'Add your deployment logic here'
            }
        }
    }
}
