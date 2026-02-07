# OpenShift

# ArgoCD

This is the "Real World" transition. To do this, you need to follow a specific structure so ArgoCD knows what to do with your files.

Step 1: Prepare your Git Repository
File 1: deployment.yaml
File 2: service.yaml

Step 2: The "OpenShift Touch" (The Route)
Since you are on OpenShift, a Service isn't enough to see the website in your browser. You need a Route.
Add this file to your Git repo
File: route.yaml

Step 3: Verify and Access
Go to the ArgoCD UI. You will see private-nginx-app.
Click Refresh. You will see it suddenly find the route.yaml you just pushed.
Once it is "Synced" (Green), get your URL:

# oc get route my-nginx-route -n my-nginx-project
Paste that URL into your browser. You should see the Bitnami NGINX welcome page.
