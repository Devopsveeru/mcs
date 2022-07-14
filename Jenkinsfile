node {
  stage('SCM') {
    checkout scm
  }
  stage('build') {
    sh "mvn clean package" 
   }     
  stage('SonarQube Analysis') {
    def mvn = tool 'sonarqube';
    withSonarQubeEnv() {
      sh "${mvn}/home/ec2-user/sonar-scanning-examples clean verify sonar:sonar -Dsonar.projectKey=veera"
    }
  }
}
