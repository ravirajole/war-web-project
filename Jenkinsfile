pipeline
{
 agent any
 stages
 {
  stage('scm checkout')
  { steps { git 'https://github.com/ravirajole/war-web-project.git'}  }


  stage('build the code')    //build the job clean workspace skip test scripts
  { steps { withMaven(globalMavenSettingsConfig: '', jdk: 'JDK_Home', maven: 'MVN_home', mavenSettingsConfig: '', traceability: true) 
	    { sh 'mvn clean -B -DskipTests package'} }  
  }
//   stage('deploy to tomcat dev')
//   { steps{sshagent(['DEVCICD']) {
// 	   sh 'scp -o StrictHostKeyChecking=no target/SpringBootStaticWeb-0.0.1-SNAPSHOT.jar ec2-user@172.31.16.242:/usr/share/tomcat/webapps'}}     
//   }
   }
}
