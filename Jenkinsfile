pipeline{
    agent{label 'mvn-3.8.6'}
    triggers { upstream(upstreamProjects: 'starterproject1', threshold: hudson.model.Result.SUCCESS) }
    stages{
        stage('source code from git'){
            steps{
               git branch: 'declarative', url: 'https://github.com/ShaikNasee/java11-examples.git' 
            }
        }
        stage('maven build'){
            steps{
                sh '/usr/local/apache-maven-3.8.6/bin/mvn clean package '
            }
        }
    }
}