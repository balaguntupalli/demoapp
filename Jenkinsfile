pipeline {
    agent any

    stages {
        stage('build) {
            steps {
               sh "sudo docker build -t asia.gcr.io/devproject-bala/nginx ."
            }
        }
        stage('Push images') {
             docker.withRegistry('https://asis.gcr.io', 'gcr:devproject-bala') {
                myContainer.push("${env.BUILD_NUMBER}")
                myContainer.push("latest")
            }
        }
    }
}
