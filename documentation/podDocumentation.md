1. apiVersion: 
    This field specifies the version of Kubernetes you are using. For pods, this will most likely be: v1

2. kind: 
    This field specifies what the config file will be used for. This could be Deployment, Service, Pod, and the like. For pods, the kind will alwayse Pod.

3. metadata: (The data you wish to specify to identify this pod.)
    a. name: (The name you wish to give your pod.)

4. spec: (Specifications for the pod including container / image information)
    a. containers: (Container information.)
       - name: (The name of the container, porbably the same as pod name in metadata.)
         image: (The image to build the container from.)
         ports: (The port needed for the container in this section.)
         - containerPort: (The actual port e.g. 8080)
