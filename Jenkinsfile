node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def mvn = tool 'MVN';
    withSonarQubeEnv() {
      sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=KasunHewage_test-ci_aeb6830e-3c6a-438c-bc5b-3995dee3fd1c -Dsonar.projectName='test-ci'"
    }
  }
}