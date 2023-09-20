node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def mvn = tool '3.9.4';
    withSonarQubeEnv() {
      sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=VendorRestApiSpringBootApp -Dsonar.projectName='VendorRestApiSpringBootApp'"
    }
  }
}
