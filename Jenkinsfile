pipeline {
    
    agent any

    stages {
        
        stage('Get source') {
            steps {
                git url: 'https://github.com/andre-mf/deploy-kub-jnk', branch: 'main'
            }
        }

        stage('Docker Build') {
            steps {
                sh('ls -la')
                sh('pwd')
                script {
                    dockerapp = docker.build("andremf/api-teste:${env.BUILD_ID}",
                    '-f ./api-produto/src/Dockerfile ./api-produto/src')
                }
            }
        }

        // stage('Docker Push Image') {
        //     steps {
        //         script {
        //             docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {
        //                 dockerapp.push('latest')
        //                 dockerapp.push("${env.BUILD_ID}")
        //             }
        //         }
        //     }
        // }

        // stage('Deploy Kubernetes') {
        //     agent {
        //         kubernetes {
        //             cloud 'kubernetes'
        //         }
        //     }

        //     steps {
        //         kubernetesDeploy(configs: '**/k8s/**', kubeconfigId: 'kubeconfig')
        //     }
        // }
    }
}