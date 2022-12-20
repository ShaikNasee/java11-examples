node('mvn-3.8.6') {
    stage("git"){
        git 'https://github.com/ShaikNasee/java11-examples.git'
    }
    stage("build"){
        sh '/usr/local/apache-maven-3.8.6/bin/mvn clean package'
    }
    stage("archive artifacts"){
        archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
    }
    stage("junit reports"){
        junit '**/TEST-*.xml'
    }
}