pipeline {
    agent {
        label {
            label 'master'
            customWorkspace "${JENKINS_HOME}/${BUILD_NUMBER}/"
        }
    }
    environment {
        Go111MODULE='on'
    }
    stages{
        stage('Test') {
            steps{
                git 'https://github.com/MohamadYussef/Go-App-CICD-Pipeline'
                //sh 'go test ./...'    //If You want to run the tests you need Go installed on your jenkins machine
            }
        }

        stage('Build') {
            steps {
                script{
                    app = docker.build("mohamadyussef/go-webapp-sample")
                }
            }
        }
        stage('Run') {
            steps {
                sh "docker run -p 8000:8000 -d mohamadyussef/go-webapp-sample"
            }
        }
        
    }
} 
