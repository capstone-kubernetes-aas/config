1. apiVersion: 
    This field specifies the version of Kubernetes you are using. For deployments, this will most likely be: apps/v1

2. kind:
    This field specifies what the config file will be used for. This could be Deployment, Service, Pod, and the like. The most common are Deployment and Service. For deployments, the kind will alwayse Deployment.

3.  metadata: 
        name:
            This field is for specifying the name of the deployment so that it can be identified when the deployment is running (as there can be multiple deployments).

4. spec: (This field has several subfields: selector, replicas, and template.)
    a. selector:
        matchLabels:
            app: (This is the name you use to refere to your deployed application.)
            tier: (This is not mandatory but can be used to specify if the deployment is front-end or back-end if necessary.)
            role: (This is also not mandatory but can be used to specify if a deployment is a master or a slave if necessary.)

    b. replicas:
        This field is used to specify the number of times it should deploy the given docker image

    c. template: (This field also has a few subfields which themselves have subfields)
        i. metadata:
            labels:
                app: (should be same as above)
                tier: (should be same as above)
                role: (should be same as above)

        ii. spec: 
                containers: (The fields under here a specs for the containers)
                - name: (The name you wish to give your container)
                  image: (The name/path of the docker image used for these containers)
                  resources: (These are not mandatory but can be useful.)
                    cpu: (How much cpu to give each container e.g: 500m.)
                    memory: (How much memory to give each container e.g: 250Mi)
                  env: (This field is not mandatory. Use to specify envs for your container.)
                  - name: (The name of the env.)
                    value:  (The protocol for your env. e.g. http, tcp, dns, etc.)
                  ports: (This field is not mandatory. Use to specify container ports)
                  - containerPort: (The chosen port for your container)
                Note: you can specify more containers by copying the above format starting from "- name" and adding each needed copy underneath the first container specification.