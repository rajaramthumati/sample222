node('linux') {
    def mvnHome
    stage('Preparation') { // for display purposes
        // Get some code from a GitHub repository
        node('linux') {
        git 'https://github.com/jglick/simple-maven-project-with-tests.git'
        }
        // Get the Maven tool.
        // ** NOTE: This 'M3' Maven tool must be configured
        // **       in the global configuration.
        mvnHome = tool 'maven382'
        xyx()
    }
    stage('Build') {
        // Run the maven build
        withEnv(["MVN_HOME=$mvnHome"]) {
            if (isUnix()) {
                sh '"$MVN_HOME/bin/mvn" -Dmaven.test.failure.ignore clean package'
            } else {
                bat(/"%MVN_HOME%\bin\mvn" -Dmaven.test.failure.ignore clean package/)
            }
        }
    }
}


def xyx() {
    print 'hi'
}
