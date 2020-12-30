pipeline {
    agent any
    options {
        timestamps()
    }

    stages {
        stage("Build"){
            steps{
                sh 'printf "Building..."'
                sh 'sleep 1s'
            }
        }
        stage("Test"){
            steps{
                sh 'printf "Testing..."'
                sh 'sleep 1s'
            }
        }
    }
}
