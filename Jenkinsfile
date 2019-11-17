pipeline {
    agent any
 triggers {
        githubPush()
    }
    tools {
        maven 'Maven' 
    }

    stages {
        stage ('Compile Stage') {

            steps {
                
                    sh 'mvn clean compile'
                
            }
        }

        stage ('Testing Stage') {

            steps {
               
                    sh 'mvn test'
                
            }
        }


        stage ('Deployment Stage') {
            steps {
                
                    println('deploying')
                
            }
        }
          stage('Build in feature') {
             when {
                branch 'Nithin/*'  
            }
            steps {
                println("Testing")
            }
        }
        stage('Deliver in dev') {
             when {
                branch 'development'  
            }
            steps {
                println("Testing")
            }

        }
        stage('Deliver in prod') {
             when {
                branch 'master'  
            }
            steps {
                println("Testing")
            }
        }
    }
}
