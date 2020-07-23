pipeline {
	agent any
	stages {

		stage('Create Kubernetes Cluster') {
			steps {
				withAWS(region:'us-west-2', credentials:'aws_credentials') {
					sh '''
						eksctl create cluster \
						--name CapstoneCluster \
						--version 1.17 \
						--region us-west-2 \
						--nodegroup-name standard-workers \
						--node-type t3.medium \
						--nodes 2 \
						--nodes-min 1 \
						--nodes-max 3 \
					'''
				}
			}
		}

		stage('Configure kubectl') {
			steps {
				withAWS(region:'us-west-2', credentials:'aws_credentials') {
					sh '''
						aws --region us-west-2 eks update-kubeconfig --name CapstoneCluster
					'''
				}
			}
		}

	}
}
