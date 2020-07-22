pipeline {
	agent any
	stages {

		stage('Create Kubernetes Cluster') {
			steps {
				withAWS(region:'us-west-2', credentials:'aws_credentials') {
					sh '''
						eksctl create cluster \
						--name MOUCapstoneUdaCluster \
						--version 1.14 \
						--nodegroup-name standard-workers \
						--node-type t3.medium \
						--nodes 2 \
						--nodes 2 \
						--nodes-min 1 \
						--nodes-max 3 \
						--node-ami auto \
						--region us-west-2 \
					'''
				}
			}
		}

		stage('Configure kubectl') {
			steps {
				withAWS(region:'us-west-2', credentials:'aws_credentials') {
					sh '''
						aws eks --region us-west-2 update-kubeconfig --name MOUCapstoneUdaCluster
					'''
				}
			}
		}

	}
}
