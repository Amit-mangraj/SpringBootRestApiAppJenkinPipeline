node {
  stage('Git Clone') {
    git url : 'https://github.com/Amit-mangraj/SpringBootRestApiAppJenkinPipeline.git', branch : 'main'
  }
  stage('Maven Build') {
    def mvn = tool 'maven';
      sh "${mvn}/bin/mvn clean package -DskipTests -Dsonar.projectKey=VendorRestApiSpringBootApp -Dsonar.projectName='VendorRestApiSpringBootApp'"
  }

 stage('SonarQube analysis') {
    withSonarQubeEnv('sonarVersion10.2-server') { // You can override the credential to be used
      sh 'mvn admin:sonar'
    }
  }
}
