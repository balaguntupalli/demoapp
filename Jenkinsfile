pipeline {
    agent any

    stages {
        stage('build') {
            app = docker.build("devproject-bala/nginx")
        }
        stage('Push images') {
            docker.withRegistry('https://asia.gcr.io', 'gcr:devproject-bala') {
                app.push("${env.BUILD_NUMBER}")
                app.push("latest")
            }
        }
    }
}
