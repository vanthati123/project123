node {
    stage('Checkout') {
        // Checkout the code from a version control system
        // For example, from a Git repository:
        git 'https://github.com/username/repo.git'
    }

    stage('Build') {
        // Set up the environment
        def javaHome = tool 'JDK'
        env.JAVA_HOME = javaHome
        env.PATH = "${javaHome}/bin:${env.PATH}"

        // Build the application using Maven
        sh "${mvnHome}/mvn clean package"
    }

    stage('Test') {
        // Run unit and integration tests
        sh "${mvnHome}/mvn test"
    }

    stage('Deploy') {
        // Deploy the application to a test environment
        sh "${mvnHome}/mvn deploy"
    }
}
