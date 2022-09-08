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
        sh "docker service create --name $PROJECT_NAME  \
            --network cluster-network-overlay \
            -p 9200:9200 \
            -p 9300:9300 \
            -e node.name=es01 \
            -e cluster.name=es-docker-cluster \
            -e cluster.initial_master_nodes=es01 \
            -e 'ES_JAVA_OPTS=-Xms256m -Xmx256m' \
            -d docker.elastic.co/elasticsearch/elasticsearch:7.17.5"
        echo "Deploy de ${PROJECT_NAME} para o ambiente ${environment} finalizado com sucesso"

    }
 //-e 'ES_JAVA_OPTS=-Xms256m -Xmx256m' \
 // -e bootstrap.memory_lock=true \
}



