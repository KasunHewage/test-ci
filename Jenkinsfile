pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                // Use Maven to build the project
                sh 'mvn clean package -DskipTests' // Adjust this command according to your Maven setup
                
                // You can add additional Maven goals or options as needed
                // e.g., 'mvn clean package -DskipTests' to skip tests during build
            }
            
            post {
                success {
                    // Archive the generated WAR file
                    archiveArtifacts artifacts: 'target/*.war', onlyIfSuccessful: true
                    
                    // You can add further actions here, such as deploying the WAR file to a server
                }
            }
        }
    }
    
    // You can add additional stages for deployment, testing, etc.
}
