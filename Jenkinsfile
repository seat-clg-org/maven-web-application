node{
    
    
propproperties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), [$class: 'JobLocalConfiguration', changeReasonComment: ''], pipelineTriggers([pollSCM('* * * * *')])])erties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), [$class: 'JobLocalConfiguration', changeReasonComment: ''], pipelineTriggers([pollSCM('* * * * *')])])

def mavenHome  = tool name: 'maven3.9.1'

echo "The Job name is: ${JOB_NAME} " 
echo "The Node name is:  ${NODE_NAME}"
echo "The Build Number is:  ${BUILD_NUMBER}"
echo "Jenkins Home path is: ${JENKINS_HOME}" 


stage('CheckoutCode'){
git branch: 'development', credentialsId: '134510de-0c0f-41e6-93fc-993f46b87a17', url: 'https://github.com/seat-clg-org/maven-web-application.git'
}

stage('Build')
{
sh "${mavenHome}/bin/mvn clean package"
}

  /*
stage('SonarQubeReport'){
sh "${mavenHome}/bin/mvn clean sonar:sonar"
}

stage('UploadArtifactsIntoNexus'){
sh "${mavenHome}/bin/mvn clean deploy"
}

stage('DeployAppIntoTomcat'){
sshagent(['dd085870-ab36-4a86-9f5b-a915e179d45d']) {
   sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@172.31.40.86:/opt/apache-tomcat-9.0.73/webapps/"
}
}
*/

}//node closing
