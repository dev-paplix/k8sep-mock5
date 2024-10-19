Name:Anis Adleena bt kamarulzaman

Q1: <done>

A developer needs access to view Pods and Services within the `dev` namespace but should not have permissions to modify or delete any resources. How would you create an RBAC policy to meet this requirement?

Task:

Create a Role named `view-pods-services` in the `dev` namespace with the necessary permissions.
Bind this Role to a user named `dev-user`.


Q2: <kiv>

Your cluster’s DNS resolution is not working correctly for services. You suspect the issue might be related to the CoreDNS configuration. How would you verify and troubleshoot the CoreDNS configuration?

Task:

Verify if CoreDNS is deployed and running correctly in the cluster.
Check the CoreDNS ConfigMap and ensure that the kubernetes plugin is correctly configured to handle service DNS requests.


Q3: <done>

A specific node in your cluster is dedicated to running a critical application and should not accept any other workloads. This node has a taint with `key=dedicated`, `value=critical`, and e`ffect=NoSchedule`. Ensure that only the pods from a deployment named `critical-app` are allowed to run on this node.

Task:

Add the necessary tolerations to the `critical-app` deployment to ensure that its pods can run on the tainted node.


Q4: <done>

You need to label a set of nodes to be used by the backend services only. The label should be `role=backend`. After labeling, ensure that a deployment named `backend-app` only schedules pods on nodes with this label.

Task:

Label the nodes with `role=backend`.
Modify the `backend-app `deployment to ensure that its pods are scheduled only on nodes with the `role=backend` label.


Q5: <done>

Execute the following requirements in the prod namespace. Create a new Deployment named app01 using the nginx:latest container image and have it listen on port 80. The deployment should consist of 2 replicas. Create a new Service named app01-svc and expose the newly created deployment using a NodePort. Confirm that you can access the nginx home (index) page using the NodePort service.



Q6: <kiv>

You are responsible for deploying and managing a Kubernetes cluster. One of the services running on your cluster is experiencing DNS resolution issues. You suspect that the issue may be related to the configuration of CoreDNS, the default DNS provider in Kubernetes. Using kubectl, please perform the following diagnostic tasks:

Identify the version of CoreDNS currently running on the cluster and save the version into the file /home/ubuntu/coredns/version.txt. The value should be stored in v1.2.3 format.
Examine the configuration of CoreDNS and record it's custom TTL value into the file /home/ubuntu/coredns/ttl.txt
Determine whether there are any pods running on the cluster that are not using CoreDNS for DNS resolution and save the resulting pod names into the file /home/ubuntu/coredns/pods.txt


Q7: <done>

A team needs a persistent storage solution for their database application running in Kubernetes. They require a 1Gi volume that should persist even if the pod is deleted or rescheduled. The storage class used should be fast-storage.

Task:

Create a PersistentVolume (PV) with a size of 1Gi and a fast-storage storage class.
Create a PersistentVolumeClaim (PVC) that binds to this PV and ensure that a pod named database-app uses this PVC for its storage.


Q8: <done>

You have a Kubernetes namespace `finance` with a deployment named `billing-app`. The `billing-app` deployment should only allow inbound traffic from pods in the `web` namespace. All other traffic should be denied.

Task:

Create a NetworkPolicy in the `finance` namespace to enforce this rule.


Q9:

You need to expose a web application running in your cluster to the internet. The application is accessible via a service named `web-service` in the `default` namespace on port 80. The domain name for the application is `example.com`.

Task:

Create an Ingress resource that routes traffic from `example.com` to the `web-service` on port 80.



Q10:

You have a deployment named frontend-app that experiences fluctuating traffic. You want to ensure that the number of pods automatically scales based on CPU utilization. The desired CPU utilization target is 60%, with a minimum of 2 pods and a maximum of 10 pods.

Task:

Configure Horizontal Pod Autoscaling (HPA) for the frontend-app deployment to meet these requirements.


Q11:

Your Kubernetes cluster uses ETCD as the key-value store for all cluster data. You need to create a backup of the ETCD data and then simulate a failure by restoring the backup.

Task:

Create a snapshot of the ETCD data and save it to /var/backups/etcd-snapshot.db.
Simulate an ETCD failure by restoring the cluster from the backup you created.


Q12:

You have a deployment named data-processing that requires all its pods to be scheduled on the same node for data locality reasons. However, it should not be scheduled on the same node as another deployment named web-server.

Task:

Configure the data-processing deployment with a Pod Affinity rule to ensure all its pods are scheduled on the same node.
Add a Pod Anti-Affinity rule to prevent data-processing pods from being scheduled on the same node as web-server.


Q13:

You need to upgrade your Kubernetes cluster from version the current version to version 1.30.4. Ensure that the control plane components are upgraded first, followed by the worker nodes.

Task:

Upgrade the Kubernetes control plane to version 1.23.
Upgrade the worker nodes to version 1.23 while minimizing downtime.

Q14:

The `development` namespace is being used by multiple teams, and you want to ensure that no single team can exhaust the cluster’s resources. Specifically, you want to limit the total CPU usage to 4 cores and memory usage to 8Gi for all pods in this namespace.

Task:

Create a ResourceQuota named `dev-quota` in the `development` namespace to enforce these limits.


Q15:

You need to ensure that a logging agent runs on every node in your Kubernetes cluster. This logging agent should collect logs from all the containers running on each node. The agent should be deployed using a DaemonSet so that it automatically runs on every node, including any new nodes added to the cluster.

Task:

Create a DaemonSet named `log-agent` that runs an appropriate logging container on every node.
Ensure that the DaemonSet is configured to run only on nodes labeled with `env=production`.



Q16:

You have deployed a new version of an application using a Deployment named `myapp` in the `production` namespace. The Deployment creates pods that listen on port 8080. You need to expose this application to external traffic so that it can be accessed via a `LoadBalancer` on port 80.

Task:

Create a Service of type `LoadBalancer` named `myapp-service` that exposes the `myapp` Deployment on port 80 and routes traffic to port 8080 on the pods.
Ensure that the service is accessible from outside the cluster.


Q17:

You have a Deployment named `web-app` in the `staging` namespace that is currently running version 1.0 of your application. You need to roll out an update to version 2.0 of the application. Ensure that the rollout is monitored, and if there are any issues, you should be able to roll back to version 1.0.

Task:

Update the `web-app` Deployment to use the new image version `web-app:2.0`.
Monitor the rollout status to ensure that the new version is deployed successfully.
If the deployment encounters issues, perform a rollback to the previous version (1.0).



