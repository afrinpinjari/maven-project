pipeline
{
	agent any
	stages
	{
		stage ('git clone')
		{
			steps
			{
				git 'https://github.com/afrinpinjari/maven-project.git'
			}
		}
		stage ('compile')
		{
			steps
			{
				withMaven(jdk: 'localJDK', maven: 'localMaven') {
				sh 'mvn compile'}
    
			}
		}
		stage ('test my project')
		{
			steps
			{
				withMaven(jdk: 'localJDK', maven: 'localMaven') {
				sh 'mvn test'}
    
			}
		}
		stage ('build my project')
		{
			steps
			{
				withMaven(jdk: 'localJDK', maven: 'localMaven') {
				sh 'mvn package'}
    
			}
		}
		stage ('deploy my project')
		{
			steps
			{
				sshagent(['tomcat1']) 
				{
				sh 'ssh -o StrictHostKeyChecking=no */target/*.war ec2-user@172.31.20.132:/usr/share/tomcat1/webapps
				}
			}
		}
}
}		
