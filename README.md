## Kubernetes Metallb
- install using Native Metallb installation from documentation: [https://metallb.universe.tf/installation/](https://metallb.universe.tf/installation/)
- edit kube-proxy configmap from namespace kube-system with 'ipvs > strictARPS' set to true instead of the default false value
- create an or some ipaddresspool/s 
- create an L2advertisement referencing those ipaddresspools (can also use BGP but I have Calico working and don't want to have issues with it)
- create a deployment of an app with the service type LoadBalancer and it will automatically be given an externalIP by Metallb
- use that address to access your app from outside

# extras:
Different annotations exists to have your service set with a fix designated ip
You can also have an ip range or CIDR so can have services in subnets configuration
You can also have several services sharing same LoadBalancer IP address as soon as they have OR different protocols OR have different ports to be accessed from

see the examples of the nginx1 and nginx2 yaml files which are set to share same ip address. 
Some commented lines exists for other configurations or explanations

HOPE THAT YOU ENJOY! 
