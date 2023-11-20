pipeline {
    agent any
     
    stages {

       stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/your-username/your-repo.git'
            }
        }
      
        stage('Build') {
            steps {
                echo 'Build App'
            }
        }
        stage('Test') {
            steps {
                echo 'Test App'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploy App'
            }
        }
       stage('Dockerize') {
            steps {
                script {
                    docker.build('your-image-name')
                    docker.withRegistry('https://your-registry-url', 'your-registry-credentials') {
                        docker.image('your-image-name').push()
                    }
                }
            }
    }
}
