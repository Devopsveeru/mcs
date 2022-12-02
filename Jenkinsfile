pipeline{
  agent any
  stages{
     stage("Maven Build"){
       steps{
            sh "mvn clean package"
            sh "mv target/*.jar target/mcs.jar"
             }
          }
  }
}    
