pipeline{
    agent any
    stages{
    stage('Stop old Container'){
        steps{
            bat 'docker rm -f company-website1 || exit 0'
        }
    }
    stage('Checkout Code'){
        steps{
            echo 'Pulling code from Github'
            checkout scm
        }
    }
    stage('Build Docker Image'){
        steps{
            echo 'Building Docker Image'
            bat 'docker build -t company-website1 .'
        }
    }
    stage('Run docker container'){
        steps{
            echo 'Running Docker container'
            bat 'docker run -d -p 8070:80 company-website1'
        }
    }
   
}
}
