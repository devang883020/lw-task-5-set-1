# lw-task-5-set-1

I'd create all the necessary Kubernetes resources for this scenario.
Kubernetes Service Account and RBAC ConfigurationClick to open code
To apply these resources, you can follow these steps:


Apply the resources:

kubectl apply -f service-account-setup.yaml

Let's go through each component:

ServiceAccount: Creates a service account named my-service-account
Role: Defines permissions to get and list secrets
RoleBinding: Binds the Role to the ServiceAccount
Secret: Creates a secret with the key "my-key" and value "Redhat" (base64 encoded)

Deployment:

Uses the service account
Mounts the secret as a volume
Runs a busybox container that reads the secret



To verify the setup:

Check if the pod is running:

kubectl get pods

View the pod logs to see if it successfully read the secret:

bashCopykubectl logs -l app=secret-reader
The output should show "Redhat" if everything is configured correctly.

