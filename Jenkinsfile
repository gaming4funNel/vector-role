pipeline {
    agent {
            label 'linux'
    }
    stages {
        stage('git clone') {
            steps {
                git branch: 'main', credentialsId: 'e80b5742-92b1-4d3a-8ba4-564ecdfb9ba3', url: 'https://github.com/gaming4funNel/vector-role.git'
                }
            }
        stage('install apps') {
            steps {
                sh "pip3 install  'molecule==3.5.2' 'molecule_docker'"
            }
        }
        stage('molecule test') {
            steps {
                sh "molecule --version"
                sh "molecule test"
            }
        }
    }
}