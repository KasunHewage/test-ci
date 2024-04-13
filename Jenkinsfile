node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def mvn = tool 'Sonar Instance';
    withSonarQubeEnv() {
      sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=KasunHewage_test-ci_9294f20d-91bb-4e0d-ad95-fb5a9cde365e -Dsonar.projectName='test-ci'"
    }
  }
}
