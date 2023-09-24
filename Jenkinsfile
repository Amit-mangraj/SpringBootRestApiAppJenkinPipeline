node {
  stage('Git Clone') {
    git url : 'https://github.com/Amit-mangraj/SpringBootRestApiAppJenkinPipeline.git', branch : 'main'
  }
  stage('SonarQube Analysis') {
    def mvn = tool 'maven';
    withSonarQubeEnv() {
      sh "${mvn}/bin/mvn clean install -DskipTests -Dsonar.projectKey=VendorRestApiSpringBootApp -Dsonar.projectName='VendorRestApiSpringBootApp'"
    }
  }
}
