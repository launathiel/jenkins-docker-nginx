node {
    stage('Checkout') {
            checkout scm
    }

    stage('testing'){
        echo "testing .."
        echo "testing success!"
    }

    stage('Build'){
        sh "docker build -t my-custom-nginx ."
        echo "Image build complete"
    }

    stage('Run App'){
        sh "docker run -p 8080:80 my-custom-nginx"
        echo "Application started!"
    }

}
