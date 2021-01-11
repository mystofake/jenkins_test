@NonCPS
def lintFiles(){
    for (changeLogSet in currentBuild.changeSets) {
        for (entry in changeLogSet.getItems()) {
            for (file in entry.getAffectedFiles()) {
                echo "Testing..."
                def filePath = file.path
                def extension = filePath.split('\\.').last()
                echo filePath
                echo extension
                if((extension == "jsonnet") || (extension == "libsonnet"))
                {
                    echo "Linting..."
                    sh """
                    echo ${filePath}
                    """
                }
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
                script{
                    lintFiles()
                }
            }
        }
    }
}
