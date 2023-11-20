pipeline {
    agent any
     
    stages {

       stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Tejas-Pulli/Dockerize.git'
            }
        }
      
        stage('Build') {
            steps {
                sh 'FROM openjdk
                    WORKDIR /app
                    COPY . /app
                    RUN javac sample.java
                    CMD ["java","sample"]'
                echo 'Build App'
            }
        }
      
       stage('Dockerize') {
            steps {
                script {
                    docker.build('myhellojava')
                    docker.withRegistry('https://hub.docker.com', 'dockerid') {
                        docker.image('myhellojava').push()
                    }
                }
            }
    }
}
}
