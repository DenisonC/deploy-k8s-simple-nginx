Nginx Server Deployment

This repository contains the definition of a Deployment for Nginx with Prometheus support, which includes the Nginx Prometheus Exporter for monitoring.

Content
deployment.yaml: YAML file that defines Nginx Deployment and Nginx Prometheus Exporter.

Explanation of Sections
apiVersion and kind
Defines the API version and resource type. In this case, we are creating a Deployment using the apps/v1 version.

metadata
Contains the Deployment metadata, including the resource name, nginx-server.

spec
Specifies the Deployment details:

selector: Defines the selector to identify the pods managed by Deployment, with the label app: nginx.
replicas: Defines the number of Deployment replicas, in this case, 1.
template: Defines the template for pods managed by Deployment, including containers, volumes and additional metadata.
containers
Defines the containers that will run in the pod:

nginx: Main container that runs Nginx, exposing port 80.
nginx-exporter: Container that runs the Nginx Prometheus Exporter, exposing port 9113 for monitoring.
volumes
Defines the volumes that will be mounted in containers, in this case, a configMap called nginx-config.

How to apply
To apply this Deployment to your Kubernetes cluster, use the command:

kubectl apply -f deployment.yaml

Comments
The deployment.yaml file must be adjusted according to the specific needs of your environment.
Make sure Prometheus is configured to monitor the endpoint exposed by the Nginx Prometheus Exporter.
