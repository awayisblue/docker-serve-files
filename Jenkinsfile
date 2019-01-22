pipeline {
    agent {
        label 'docker'
    }
    stages {
        stage('Deploy') {
            when { branch 'master' }
            steps {
                script {
                    def name = 'docker-serve-files'
                    def registry = 'https://docker.io'
                    def namespace = 'awayisblue'
                    echo "Deploying to ${name} in ${registry}"
                    docker.withRegistry(registry) {
                        def image = docker.build("${namespace}/${name}:${env.BUILD_ID}")
                        image.push()
                        image.push('latest')
                    }
                }
            }
        }
    }

    post {
      always {
        echo 'clean up!'
        cleanWs()
      }
    }
}