pipeline{

	agent any
	stages{
		stage('Git-Checkout'){
			steps{
				echo "git checkout completed successfully!";		
				git 'https://github.com/mohanraopandi/scriptedpipeline.git'
			
			}
		}
		stage('Build'){
			steps{
				echo "Build completed successfully!";		
				sh label: '', script: 'Build.sh'
			
			}
		}
		stage('Deploy'){
			steps{
				echo "deployed successfully!";
				sh label: '', script: 'Deploy.sh'				
			
			}
		}
		stage('Quality'){
			steps{
				echo "Quality passed successfully!";		
				sh label: '', script: 'Quality.sh'
			
			}
		}
		stage('Unit'){
			steps{
				echo "Deployment in dev server completed successfully!";	
				sh label: '', script: 'Unit.sh'				
			
			}
		}

}
	post{
		always{
			echo "This will run always!"
		}
		success{
			echo "This will run only if successful!"
		}
		failure{
			echo "This will run only if failure!"
		}
		unstable{
			echo "This will run only if the run was marked as unstable!"
		}
		changed{
			echo "This will run only if the state of the pipe line has changed"
			echo "For example, if the pipe line was previuosly failing but is now sucessful"
		}



}

}

