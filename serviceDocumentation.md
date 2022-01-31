1. apiVersion: 
    This field specifies the version of Kubernetes you are using. For deployments, this will most likely be: v1

2. kind:
    This field specifies what the config file will be used for. This could be Deployment, Service, Pod, and the like. The most common are Deployment and Service. For services, the kind will alwayse Service.

3. metadata: (This field has several subfields.)
    a. name: (The name of your service. Name will be used to identify this service from the others that may be also running.)
    b. labels:
        app: (This is the name you use to refere to your service / which application it is applied to.)
        tier: (This is not mandatory but can be used to specify if the service is front-end or back-end if necessary.)
        role: (This is also not mandatory but can be used to specify if a service is a master or a slave if necessary.)

4. spec: (This field also has a few subfields and is used to specify informatio about the service such as exposed ports.)
    a. ports: (Copy all of the fields below and add them to the end to specify multiple prots)
        i. - port: (The port to expose e.g: 8080)
             targetPort: (Usually the same as this "- port" but doesn't have to be.)           
        ii. selector:
                app: (Should be same as above)
                tier: (Should be same as above)
                role: (Should be same as above)

5. section 4.a.i can also be written as the following:
    - protocol: (Name the protocol you intend to use.)
      port: (The port to expose)              
      targetPort: (The port to target)

6. subsets: (This field is used to connect a port to an address without using the selector field to specify information about the service.)
    a. - addresses:
            - ip: (The target ip address of the service)
         ports:
            - port: (The target port for the service)