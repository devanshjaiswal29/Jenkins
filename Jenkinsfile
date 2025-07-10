pipeline {
    agent any  // Run on any available Jenkins agent

    stages {

        stage('Install and Build Frontend ') {
            steps {
                dir('frontend') {
                    echo 'Installing frontend packages...'
                    bat 'npm install'
                    bat 'start npm start'
                }
            }
        }
        stage('Build Backend') {
            steps {
                dir('backend') {
                    echo 'Building backend...'
                    bat 'dotnet build'
                    bat 'dotnet run &'
                }
            }
        }
    }
}
