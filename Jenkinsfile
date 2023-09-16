pipeline {
    agent {
        label 'agent'
    }
    stages {
        stage('clear work dir') {
            steps {
                deleteDir()
            }
        }
        stage('clone repo') {
            steps {
                git branch: 'main', url: 'https://github.com/spouk/roles.git'
            }
        }
        stage('run test') {
            steps {
                sh 'export PATH=$PATH:/usr/local/bin; pwd; ls -la; cd simplerole; molecule test'
            }
        }
    }
}
