pipeline {  
    agent any  

    stages {  
        stage('Build') {  
            steps {  
                echo 'building ...'
                // sh 'docker stop jServer'  
                // sh 'docker rm jServer'  
                sh 'docker build -t jserver https://github.com/francislung1994/docker.git#main'  
            }  
        }  

        stage('Deploy') {  
            steps {  
                echo 'deploying ...'
                sh 'docker container run -p 3000:3000 jserver'  
                // sh 'kubectl apply -f deployment.yaml'  
            }  
        }  
    }  

    post {
        always {
            echo 'Jenkins pipeline completed.'
        }
    }
}
