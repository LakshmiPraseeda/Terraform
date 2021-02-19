pipeline
{
    agent any
    stages
	{
	stage('test')
	    {
		steps
		    {
    			withCredentials([string(credentialsId: 'aws-credentials', variable: 'aws-credentials')]) { //set SECRET with the credential content
        		//echo "My secret text is '${access}'"
				//withCredentials([string(credentialsId: 'secretkey', variable: 'secretkey')]) { //set SECRET with the credential content
        			//echo "My secret text is '${secr}'"
					withCredentials([file(credentialsId: 'jenkins', variable: 'jenkins')]) {
						withCredentials([file(credentialsId: 'jenkins_pem', variable: 'jenkins_pem')]) {
				sh 'terraform init -no-color'
				sh 'terraform apply -auto-approve -no-color -var "Accesskey=$Aaccesskey" -var "secretkey=$secretkey" -var "jenkins=$jenkins" -var "jenkins_pem=$jenkins_pem"'
			}
    		}
				}
			}
		}
	    }
	}
}
