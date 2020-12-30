pipeline {
    agent {
        kubernetes {
        label "jenkins-worker-terra-${UUID.randomUUID().toString()}"
            defaultContainer 'jnlp'
            yaml '''
                apiVersion: v1
                kind: Pod
                spec:
                containers:
                    - name: jnlp
                    image: jenkins/jnlp-slave
                    tty: true
                    pull: always
                    - name: ubuntu
                    image: ubuntu
                    tty: true
                    pull: always
                '''
        }
    }
    options {
        timestamps()
    }

    stages {
        stage("Build"){
            steps{
                container(jnlp){
                    sh 'printf "Building..."'
                    sh 'ls'
                    sh 'sleep 1s'
                }
            }
        }
        stage("Test"){
            steps{
                container(ubuntu){
                    sh 'printf "Building..."'
                    sh 'ls'
                    sh 'sleep 1s'
                }
            }
        }
    }
}
