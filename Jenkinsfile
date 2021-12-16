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
			stage('build'){
				steps{
					script{
						sh "sudo ansible-playbook ansible/build.yml -i ansible/inventory/host.yml"
					}
				}
			}
		}
}
