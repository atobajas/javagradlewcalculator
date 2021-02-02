pipeline {
    agent any
    stages {
        stage('Checkout external proj') {
            steps {
                git branch: 'master',
                    url: 'https://github.com/atobajas/javagradlewcalculator.git'

                sh "ls -lat"
            }
        }

        stage('Compile') {
            steps {
                echo "Compile solution java: calculator"
                sh '''
                    chmod +x gradlew
                    ./gradlew
                '''
            }
        }

        stage('Unit tests') {
            steps {
                echo "Test solution: calculator"
                sh './gradlew test'
            }
        }
    }
}