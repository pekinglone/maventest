pipeline {
    agent any
    tools {
        maven "Maven3.6.0"
        jdk "jdk1.8.0_202"
    }
    stages {
        stage('Build') {
            steps {
                pre {
                    cleanWs()
                }
                sh 'printenv'
                sh 'which java &&which mvn'
                sh 'java -version'
                sh 'mvn -version'
                //sh 'rm -rf ./* &&  rm -rf ../../.m2/*'
                // Get some code from a GitHub repository
                //git 'https://github.com/jglick/simple-maven-project-with-tests.git'
                
                //sh 'git clone https://github.com/jglick/simple-maven-project-with-tests.git'

                // Run Maven on a Unix agent.
                sh 'mvn -Dmaven.test.failure.ignore=true clean package'

                // To run Maven on a Windows agent, use
                // bat "mvn -Dmaven.test.failure.ignore=true clean package"
            }

        }
    }
}
