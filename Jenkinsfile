def CONTAINER_NAME="nginx-container"

node {
    stage('Checkout') {
        checkout scm
    }

    stage('testing'){
        echo "testing .."
        echo "testing success!"
    }

    stage("Image Prune"){
        imagePrune(CONTAINER_NAME)
    }

    stage('Build'){
        sh "docker build -t my-custom-nginx ."
        echo "Image build complete!"
    }

    stage('Run App'){
        sh "docker run -d --rm -p 8080:80 --name nginx-container my-custom-nginx"
        echo "Application started!"
    }
}

def imagePrune(containerName){
    try {
        sh "docker image prune -f"
        sh "docker stop $containerName"
        sh "docker rm $containerName"
    } catch(error){}
}