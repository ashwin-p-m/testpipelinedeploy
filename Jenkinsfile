pipeline {
    
    agent any
    parameters {

        string name: 'CLIENT_TAG', description: 'Tag for the client application\'s docker image'
        string name: 'SERVER_TAG', description: 'Tag for the server application\'s docker image'

    }
    stages {

        stage('Deploy Application') {

            steps {

                echo 'Deploy Application Started...'
                git url: 'git@github.com:ashwin-p-m/testpipeline.git', credentialsId: 'git-hub-key', branch: 'test-dev'
                echo "Client tag - ${params.CLIENT_TAG}"
                echo "Server tag - ${params.SERVER_TAG}"
                sh 'docker-compose --project-name testdeploy up --build'
                echo 'Deploy Application Finished...'

            }

        }

    }

}