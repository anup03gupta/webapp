
node {
   stage('Checkout') {
   git 'https://github.com/anup03gupta/webapp.git'
    
}
stage('Build') {
   def mvn_version = 'Maven'	
 	withEnv( ["PATH+MAVEN=${tool mvn_version}/bin"] ) {	
 	sh "mvn clean package"	 

   }
}
stage('Package') {
   sshagent(['tomcat-dev']) {
    sh 'scp -o StrictHostKeyChecking=no target/*.war anup@172.31.41.209:/var/lib/tomcat8/webapps/'
}

}


}


