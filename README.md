# Jenkins Helm Chart 

This repository contains helm chart for the jenkins controller and agent. You can scale jenkins at any scale using this helm chart on kubernetes cluster.

#### Requirements

1. Kubernetes Cluster ( >v1.18 )
2. Helm Chart (v3)
3. Kubectl 


#### Steps

1. First clone this repo.

		git clone https://github.com/himanshuchaudhary426/helm-chart-for-prod-jenkins.git

2. Open values.yaml and setup following values.

		a) adminuser and adminpassword
		b) Controller and agent memory and cpu resources to use.
		c) Your subdomain to access the jenkins on external URL. (If you don't want any external URL for jenkins then you can disable ingress)

3. Create a new namespace for jenkins to install in the kubernetes cluster. Use the below command to do so.

		kubectl create namespace jenkins

3. After adding all the required values you can now run helm command to install jenkins in the kubernetes cluster.

		helm install jenkins jenkins/ -n jenkins

4. Check and verify jenkins is running or not.

		kubectl get pods -n jenkins