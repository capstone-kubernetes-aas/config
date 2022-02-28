# **Service**

## *Prefilled fields*

### apiVersion: 
```
This field specifies the version of Kubernetes you are using. For deployments, this will most likely be: v1
```

### kind:
```
This field specifies what the config file will be used for. This could be Deployment, Service, Pod, and the like. The most common are Deployment and Service. For services, the kind will alwayse Service.
```

## *User specified fields*

### metadata: 
* #### name: 
    ```
    The name of your service. Name will be used to identify this service from the others that may be also running.)
    ```
* #### labels:
    ```
    app: (This is the name you use to refere to your service / which application it is applied to.)
    tier: (This is not mandatory but can be used to specify the service is front-end or back-end.)
    role: (This is also not mandatory but can be used to specify a service is a master or a slave.)
    ```

### spec: 
* #### ports: 
    ```
    - port: (The port to expose e.g: 8080)
    targetPort: (Usually the same as this "- port" but doesn't have to be.)   
    ```        
* #### selector:
    ```
    app: (Should be same as above)
    tier: (Should be same as above)
    role: (Should be same as above)
    ```