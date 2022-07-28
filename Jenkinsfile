#!groovy

PROJECT_NAME = "elastic-search"
PROJECT_KEY = "tiggomark"
SCM = "GITHUB"


node {


    def branch = "master"
    def environment = "prod"
    def tagVersion = "dev"

    stage(name: 'Checkout from SCM') {
        echo 'Checking out from scm'
        checkout scm
    }



    stage(name: 'Deploy to Docker Container') {
        echo 'Deploying images to docker container'
        sh "docker-compose up"
        echo "Deploy de ${PROJECT_NAME} para o ambiente ${environment} finalizado com sucesso"

    }

}



