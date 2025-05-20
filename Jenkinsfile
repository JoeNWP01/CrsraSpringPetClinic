pipeline {
    // Define the agent where the pipeline will run. 'any' means it can run on any available agent.
    agent any
    environment {
        APP_PORT = 8090
    }
    // Define the tools section to specify Maven version.
    // This assumes 'mavenV3' is configured in Jenkins Global Tool Configuration.
    tools {
        maven 'mavenV3'
    
    // Define the stages of the pipeline.
    stages {
        // Checkout stage: Gets the source code.
        stage('checkout') {
            steps {
                git branch: "main", url: "https://github.com/JoeNWP01/CrsraSpringPetClinic.git"
            }
        }

        // Build stage: Compiles the project.
        stage('build') {
            steps {
                // Since 'mavenV3' is defined in the 'tools' section,
                // the 'mvn' command will automatically use that Maven installation.
                sh "mvn compile"
            }
        }

        // Test stage: Runs the project tests.
        stage('test') {
            steps {
                sh "mvn test"
            }
        }
    }
}
