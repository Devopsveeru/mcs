node {
  stage('SCM') {
    checkout scm
  }
  stage('build') {
    sh "mvn clean package" 
   }     
  stage('SonarQube Analysis') {
    def mvn = tool 'Default Maven';
    withSonarQubeEnv() {
      sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=veera"
    }
  }
}
