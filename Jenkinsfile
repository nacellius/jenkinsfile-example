def exampleDef = "test string here"
def echoParams(options = [], param2, param3){
    for (i in options){
        sh "echo ${i}" 
    }
}

pipeline {
    agent any // instructs Jenkins to allocate an executor and workspace for the entire pipeline
    stages {
        stage("Hello") {
            steps {
                echo "Hello World"
                echo "World Hello"
            }
        }
        stage("Function") {
            steps {
                echo "$exampleDef"
                echoParams(["one", "yee", "yarp"], 2, 3 )
            }
        }
    }
    post {
        always {
            echo "this post condition will always run"
        }
    }
}