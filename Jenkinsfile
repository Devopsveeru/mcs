node {
  stage('SCM') {
    checkout scm
  }
  stage('build') {
     mvn clean install 
   }     
  stage('SonarQube Analysis') {
    def mvn = tool 'Default Maven';
    withSonarQubeEnv() {
      sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=veera"
    }
  }
}
