node("mvn-3.8.6") {
    properties([pipelineTriggers([cron('* 3 * * 1-5')])])
    stage("git"){
        git branch: 'scripted', url: 'https://github.com/ShaikNasee/java11-examples.git'
    }
    stage("build"){
        sh '/usr/local/apache-maven-3.8.6/bin/mvn clean package'
    }
    stage("archive artifacts"){
        archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
    }
    stage("Publish rest reports"){
        junit '**/TEST-*.xml'
    }
}