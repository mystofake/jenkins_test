@NonCPS
def lintFiles(){
    for (changeLogSet in currentBuild.changeSets) {
        for (entry in changeLogSet.getItems()) {
            for (file in entry.getAffectedFiles()) {
                echo "Testing..."
                def filePath = file.path
                sh '''
                echo ${filePath}
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
            }
        }
    }
}
