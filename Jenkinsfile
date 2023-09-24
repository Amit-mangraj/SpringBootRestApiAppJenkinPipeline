node {
  stage('Git Clone') {
    git url : 'https://github.com/Amit-mangraj/SpringBootRestApiAppJenkinPipeline.git', branch : 'main'
  }
  stage('Maven Build') {
    def mvn = tool 'maven';
      sh "${mvn}/bin/mvn clean package -DskipTests -Dsonar.projectKey=VendorRestApiSpringBootApp -Dsonar.projectName='VendorRestApiSpringBootApp'"
  }

 stage('SonarQube analysis') {
    withSonarQubeEnv(credentialsId: 'sqa_91d635a7b99d7c6e8369a0a6a1d650c4c97e4b20', installationName: 'sonar-token') { // You can override the credential to be used
      sh 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.7.0.1746:sonar'
    }
  }
}
