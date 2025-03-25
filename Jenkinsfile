pipeline{

    agent any

    stages{
        stage('Build'){
            agent{
                docker{
                    image "node:23-alpine"
                    reuseNode true
                }
            }
            steps{
                // ceci pour tracer lors des nouveaux build pour voir ci on a zaper la version node
                sh '''
                    ls -la
                    node --version
                    npm --version
                    npm ci
                    npm run build
                    ls -la
                '''
            }
        }
    }
}