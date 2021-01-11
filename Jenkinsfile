def lintFiles(){
    for (changeLogSet in currentBuild.changeSets) {
        for (entry in changeLogSet.getItems()) {
            for (file in entry.getAffectedFiles()) {
                echo "Testing..."
                filePath = file.getPath()
                echo filePath
                sh '''
                echo filePath
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
