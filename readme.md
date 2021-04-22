pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "Maven 3"
    }

    stages {
        stage('SCM') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/dnilay/mongodb-relation.git'

            }

            
        }
        stage('Mvn Clean') {
            steps {
            
                 sh "mvn clean"
            }

            
        }
        stage('Mvn Package') {
            steps {
            
                 sh "mvn package"
            }

            
        }
        stage('Mvn Install') {
            steps {
            
                 sh "mvn install"
            }

            
        }
    }
}
