pipeline {
	agent any
	stages {

		stage('Create Kubernetes Cluster') {
			steps {
				withAWS(region:'us-west-2', credentials:'aws_credentials') {
					sh '''
						eksctl create cluster \
						--name MOUCapstoneUdaCluster \
						--version 1.17 \
						--region us-west-2 \
						--nodegroup-name standard-workers \
						--node-type t3.medium \
						--nodes 3 \
						--nodes-min 1 \
						--nodes-max 4 \
						--ssh-access \
						--ssh-public-key /home/ubuntu/.ssh/id_rsa.pub \
						--managed
					'''
				}
			}
		}

		stage('Configure kubectl') {
			steps {
				withAWS(region:'us-west-2', credentials:'aws_credentials') {
					sh '''
						aws --region us-west-2 eks update-kubeconfig --name MOUCapstoneUdaCluster --role-arn arn:aws:iam::486251485842:user/capstone
					'''
				}
			}
		}

	}
}
