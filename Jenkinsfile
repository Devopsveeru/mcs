pipeline{
  agent any
  stages{
     stage("Maven Build"){
       steps{
            sh "mvn clean package"
            sh "mv https://get.jenkins.io/war-stable/latest/jenkins.war target/jenkins.war"
        }
    }
     stage("deploy-dev"){
       steps{
          sshagent(['deploy']) {
          sh """
          scp -rp target/jenkins.war test@13.126.162.114:/home/test/apache-tomcat-9.0.63/webapps/
          ssh test@13.126.162.114 /home/test/apache-tomcat-9.0.63/bin/shutdown.sh
          ssh test@13.126.162.114 /home/test/apache-tomcat-9.0.63/bin/startup.sh
            """
          }
        }
    }
    }
}      
