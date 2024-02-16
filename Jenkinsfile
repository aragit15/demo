pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "mymaven"
    }  

    stages {
        stage('Compile') {
            steps {
              scripts{
                echo "COMPILING"
                sh "mvn compile"    
                           
            }           
        }
        stage('UnitTest') {
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
