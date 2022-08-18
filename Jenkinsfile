pipeline {
    agent any
    
    tools{
        gradle 'Gradle'
    }

    stages {
        stage('run frontend') {
            steps {
                echo 'executing yarn..'
                nodejs('Node-18.7') {
                    sh 'yarn install'
                }
            }
        }
        stage('run backend') {
            steps {
                echo 'executing gradle..'
                withGradle() {
                    sh './gradlew -v'
                }
            }
        }
    }
}
