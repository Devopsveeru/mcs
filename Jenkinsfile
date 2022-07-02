pipeline{
  agent any
  stages{
     stage("Maven Build"){
       steps{
            sh "mvn clean package"    
        }
    }
     stage("deploy-dev"){
       steps{
          sshagent(['deploy']) {
          sh "scp -rp target/* nisha@65.0.27.124:/home/ec2-user"
          }
        }
    }
    }
}
