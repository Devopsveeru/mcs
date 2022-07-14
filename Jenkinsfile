node
{
    

stage('SonarQube Analysis') {
    def scannerHome = tool 'sonarqube'
      withSonarQubeEnv('sonarqube') {
      sh """/home/ec2-user/sonarqube-9.5.0.56709/bin/sonar-scanner-2.6.1
     -D sonar.projectVersion=1.0-SNAPSHOT \
       -D sonar.login=admin \
      -D sonar.password=admin \
      -D sonar.projectBaseDir=/var/lib/jenkins/workspace/jenkins-sonar/ \
        -D sonar.projectKey=veera \
        -D sonar.sourceEncoding=UTF-8 \
        -D sonar.language=java \
        -D sonar.sources=my-app/src/main \
        -D sonar.tests=my-app/src/test \
        -D sonar.host.url=http://13.233.216.213:9000/"""
        }
}
}
