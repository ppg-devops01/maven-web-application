timestamps {
node('slave1-Redhat') {
    def mavenHome = tool name:"maven3.6.3"
    
    properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), [$class: 'JobLocalConfiguration', changeReasonComment: '']])
    

    stage ('CodecheckOut') {
        git branch: 'development', credentialsId: 'e668a2c0-17f6-46e5-91c9-92febc884bdf', url: 'https://github.com/ppg-devops01/maven-web-application.git'
    }
    
    stage ('build') {
        
        sh "${mavenHome}/bin/mvn clean package"
    }
    
    /*
    stage ('SonarQubeReport') {
        
        sh "${mavenHome}/bin/mvn sonar:sonar"
    }
    
     stage ('ArtifactUploadIntoNexus') {
        
        sh "${mavenHome}/bin/mvn deploy"
    }
    
    stage ('DeployApplicationIntoTomcatServer') {
        sshagent(['1457494c-512d-4e50-866f-5f20d77da04b']) {
            sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@65.0.110.90:/opt/apache-tomcat-9.0.41/webapps"
            }
    }
    
    stage ('SendNotifications') {
        mail bcc: '', body: 'the corresponding build status is shared.', cc: '', from: '', replyTo: '', subject: 'This is a Build Notification', to: 'ppgdevops@gmail.com'
    }
    */
}
}
