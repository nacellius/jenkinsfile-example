def exampleDef = "test string here" // def; syntax similar to Groovy 

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
                echo "$exampleDef" // use double quotes to support dollar-sign ($) based string interpolation
            }
        }
    }
    post { // stuff to run at the end of all stages
        always {
            echo "this post condition will always run"
        }
    }
}