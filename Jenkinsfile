pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "mymaven"
    }  

    stages {
        stage('Compile') {
            agent any
            steps {
              scripts{
                echo "COMPILING"
                sh "mvn compile"    
                           
            }           
        }
        stage('UnitTest') {
            agent any
            steps { 
              scripts{
                echo "Running unit test"
                sh "mvn test"
            }
            post{
                always{
                    junit 'target/surefire-reports/*.xml'
                }
            }           
        }
        stage('package') {
            agent any
            steps {
                script{
                  echo "creating package"
                  sh "mvn package"
                }
               
              
            }           
        }
        }
        
        }
        
    }
}
