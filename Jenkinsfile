@Library("Shared") _
pipeline{
    agent{ label "One"}
    stages{
        stage("Hello"){
            steps{
             script{
                hello()
            }   
            }
        }
        stage("code"){
            steps{
                script{
                clone("https://github.com/Rakesh-Billy/django-notes-app.git", "main")
                }
            }
        }
        stage("build"){
            steps{
                script{
                    docker_build("notes-app", "latest", "rakeshbilly")
                }
            }
        }
        stage("push to dockerHub"){
            steps{
                script{
                    docker_push("notes-app", "latest", "rakeshbilly" )
                }
            }
        }
        stage("deploy"){
            steps{
                script{
                    docker_compose()
                }
            }
        }
    }
}
