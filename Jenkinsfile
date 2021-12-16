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
			stage('install'){
				steps{
					script{
						sh "npm install"
					}
				}
			}
			stage('build'){
				steps{
					script{
						sh "ansible-playbook ansible/build.yml -i ansible/inventory/host.yml"
					}
				}
			}
		}
}
