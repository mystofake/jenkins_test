def retrieveFiles(){
    def filesPath = []
    for (changeLogSet in currentBuild.changeSets) {
        for (entry in changeLogSet.getItems()) { // for each commit in the detected changes
            for (file in entry.getAffectedFiles()) {
                def extension = file.path.split('\\.').last()
                if((extension == "jsonnet")||(extension == "libsonnet")){
                    filesPath.add(file.path)
                }
            }
        }
    }
    return filesPath
}

def lintFiles(jsonnetFiles){
    for(i in jsonnetFiles){
        sh """echo ${i}"""
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
                    def jsonnetFiles = retrieveFiles()
                    lintFiles(jsonnetFiles)
                }
            }
        }
    }
}
