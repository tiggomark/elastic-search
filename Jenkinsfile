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
        sh "docker run --name $PROJECT_NAME --net cluster-network -e 'discovery.type=single-node' -p 9200:9200 -p 9300:9300 -d docker.elastic.co/elasticsearch/elasticsearch:7.17.5"
        echo "Deploy de ${PROJECT_NAME} para o ambiente ${environment} finalizado com sucesso"

    }

}



