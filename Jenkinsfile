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
		
	}	
	}
