lintFiles(){
    for (changeLogSet in currentBuild.changeSets) {
        for (entry in changeLogSet.getItems()) {
            for (file in entry.getAffectedFiles()) {
                sh '''
                echo ${file.getPath()}
                '''
            }
        }
    }
}
pipeline {
    agent any
    options {
        timestamps()
    }

    stages {
        stage("Lint"){
            steps{
                lintFiles()
                sh 'printf "Building..."'
                sh 'hostname'
                sh 'ls -l'
                sh 'touch newFileBuilt'
                sh 'pwd'
                sh 'sleep 1s'
            }
        }
    }
}
