pipeline
{
	agent any
		stages{
			stage('Pull'){
				steps{
					script{
						checkout([$class: 'GitSCM', branches: [[name: '*/master']],
						userRemoteConfigs: [[
							url: 'https://github.com/ridha-bouazizi/LivraisonContinue.git']]]
						)
					}
				}
			}
			stage('docker'){
				steps{
					script{
						sh "ansible-playbook ansible/docker.yml -i ansible/inventory/host.yml"
					}
				}
			}
		}
}
