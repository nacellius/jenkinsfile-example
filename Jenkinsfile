def exampleDef = "test string here"
def echoParams(options = [], param2, param3){
    for (i in options){
        sh "echo ${i}" 
    }
    sh "echo param2 is ${param2} and param3 is ${param3}"
}

class User {
    public final String name
    public final Integer id
    
    User(String name) { this.name = name}
    User(String name, Integer id) { 
        this.name = name
        this.id = id
    }
    
    String getName() { "Name: $name" } 
    String getId() { "ID: $id" }   
}

def batman = new User("Bruce Wayne", 2112)
def nightwing = new User("Dick Grayson")

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
        stage("Class") {
            steps {
                echo "$batman.name" // calls getName getter function
                echo "$nightwing.@name" // forces usage of field instead of getter
            }
        }
    }
    post {
        always {
            echo "this post condition will always run"
        }
    }
}