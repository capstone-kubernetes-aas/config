# **Deployment**

#### Prefilled fields
```yaml
# This field specifies the version of Kubernetes you are using. 
#For deployments, this will most likely be: apps/v1
apiVersion: apps/v1

# This field specifies what the config file will be used for. 
# This could be Deployment, Service, Pod, and the like. 
# The most common are Deployment and Service. 
# For deployments, the kind will alwayse Deployment.
kind: Deployment

## User specified fields

metadata:
    # This field is specifies the name of the deployment so 
    # that it can be identified when the deployment is running 
    # (as there can be multiple deployments).
    name:

    # This field can be configured with the name of the namespace 
    # for the deployment to be in a certain namespace 
    # (OPTIONAL, does not have to specified and will be deployed 
    # in 'default' if not specified).
    namespace:

spec: 
    selector:
        matchLabels:
            app: (This is the name you use to refere to your deployed application.)
            tier: (This is not mandatory but can be used to specify the deployment is front-end or back-end.)
            role: (This is also not mandatory but can be used to specify a deployment is a master or a slave.)
        
    # This field is used to specify the number of times it should deploy the given docker image 
    replicas:

    template: 
        metadata:
            labels:
                app: (same as above)
                tier: (same as above)
                role: (same as above)
            
        spec: 
            containers: 
            - name: (The name you wish to give your container)
              imagePullPolicy: (Must be configured to IfNotPresent since we are using local docker registry)
              image: (The name/path of the docker image used for these containers)
              ports: (This field is used to specify container ports)
              - containerPort: (The chosen port for your container)
```