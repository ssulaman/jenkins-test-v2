pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello THIS IS SULAMAN World lol!'
            }
        }
        stage('Get-NGINX-docker'){
            agent{  
              docker{
                  image:'nginx:stable-alpine3.23-perl'    

              }
                steps{ 

                    echo " ok u got the stage syntax writeg well done sulaman!!"
                    sh 'pwd'
                    sh 'ls -lrt'

                    }
            }
        }
    }
}
