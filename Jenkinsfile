node {
    stage('Checkout') {
        checkout scm
    }

    stage('testing'){
        echo "testing .."
        echo "testing success!"
    }

    stage('Clean'){
        sh "docker rm nginx-container"
        echo "delete success!"
    }

    stage('Build'){
        sh "docker build -t my-custom-nginx ."
        echo "Image build complete!"
    }

    stage('Run App'){
        sh "docker run -d -p 8080:80 --name nginx-container my-custom-nginx"
        echo "Application started!"
    }
}
