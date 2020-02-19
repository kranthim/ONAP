# ONAP
VF-C, SDN-C deployment ;  Rancher and Customized code

#######################################
Installation Guide
#######################################
Vitual Function Controller: VF-C
https://wiki.onap.org/pages/viewpage.action?pageId=3246989

VF-C ; Swager
https://onap.readthedocs.io/en/beijing/submodules/vfc/nfvo/lcm.git/docs/platform/installation.html

Getting Started With ONAP:
https://onap.readthedocs.io/en/beijing/release/index.html#id5

ONAP on Kubernetes with Rancher:
https://onap.readthedocs.io/en/beijing/submodules/oom.git/docs/oom_setup_kubernetes_rancher.html#onap-on-kubernetes-with-rancher

SETUP:
Blade servers: 4
RAM: 192 GB
CPU: 32 cores
Kubernetes	1.13.5
Helm	2.12.3
kubectl	1.13.5
Docker	18.09.5

Rancher:
http://10.xx.xx.xx:8080/env/1a7/infra/hosts

VIM:
https://10.xx.xx.xx/project/

Retrive Tables from:
kubectl get svc -n onap -o go-template='{{range .items}}{{range.spec.ports}}{{if .nodePort}}{{.nodePort}}{{.}}{{"\n"}}{{end}}{{end}}{{end}}'



Lab Setup
---------------------------------------------------------------------
sb4-k8s-1   192.xx.xx.xx   10.xx.xx.xx
sb4-k8s-2   192.xx.xx.xx   10.xx.xx.xx
sb4-k8s-3   192.xx.xx.xx   10.xx.xx.xx

sb4-rancher 192.xx.xx.xx   10.xx.xx.xx

VM        Flavor                     Role
------------------------------------------------------------------------------
12	 16 GB RAM - 8 vCPUs  	Running the K8S worker role
3	   16 GB RAM - 8 vCPUs 	Running the K8S controller role
1	   16 GB RAM - 8 vCPUs	  Running the shared NFS server for /dockerdata-nfs/
