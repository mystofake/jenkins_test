pipeline {
    agent {
        kubernetes {
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
    - name: golang
      image: golang
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
                sh 'printf "Building..."'
                sh 'hostname'
                sh 'ls -l'
                sh 'touch newFileBuilt'
                sh 'pwd'
                sh 'sleep 1s'
            }
        }
        stage("Test"){
            steps{
                container('golang'){
                    sh 'printf "Building..."'
                    sh 'hostname'
                    sh 'ls -l'
                    sh 'pwd'
                    sh 'go version'
                    sh 'sleep 1s'
                }
            }
        }
    }
}
