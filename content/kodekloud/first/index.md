---
title: How to Deploy Applications to Kubernetes
date: 2024-01-14
draft: false
resources:
  - src: "/assets/img/k8s-resources/*"
    name: "k8s-resources"
    title: "k8s-resources"
weight: 5
---


Kubernetes simplifies the running of containerized application by automating many things like scaling, self-healing, high-availability, service discovery, load balancing, updates and rollbacks. This is enabled by a unified API which includes the Controller Manager, Scheduler, etcd, Kubelet and  Kube-proxy that allows for applications to be defined declaratively in yaml and do things like configuration management, handle persistent storage and Role Based Access Control.

 When the API is extended, with CRDs (Custom Resource Definitions), Admissions Controllers and with Controllers/Operators, Kubernetes then goes beyond its original purpose as an 'orchestrator of containers':

- to provision cloud infrastructure or custom applications through Crossplane created CRDs,
- to enforce security policies through a Kyverno Admission Controller,
- to synchronize the cluster manifests with the source of truth on Github through ArgoCD's CRDs,
- to provision an Istio service mesh or other side car patterns like Knative or Dapr,
- to enable an environment of application-specific-controllers, or operators, to  manage applications:

    - with the Operator Framework or Red Hat's Openshift.
    - with Charmed Operators on Ubuntu.
    - with VMware's Tanzu.  



With all the automation features (staying with just vanilla Kubernetes) that have made things easy comes complexity. That’s because the underlying is complex. However, once again, the new goal, it seems,  is to abstract away this complexity and try and make things ‘simpler’. It is possible, with one CRD wrapper layer (from acorn.io) to create and deploy an application to Kubernetes without having to know the Kubernetes resources (objects), shown below. Yet it’s probably worth knowing, especially if you want to appreciate what ever layer that does get put on top of the <span style="color: green">**underlying kubernetes resources :**</span> 
#### <span style="color:green;"> (1) namespace, deployment, pod, replicaset ,service, ingress, horizontal autoscaler, network policy, limits, quotas 

![k8s Exposed Pod](images/k8s-diagram.png)

#### <span style="color:green;"> (2) persistent volume, persistent volume claim, config map, secret, endpoint, service account, role, cluster role, cluster role binding and pod security policy </span>

<div style="display: flex; 40px;">
{{< figure src="k8s-resources-40/pv-128.png" alt="pv" >}}
{{< figure src="k8s-resources-40/pvc-128.png" alt="pvc" >}}
{{< figure src="k8s-resources-40/cm-128.png" alt="cm" >}}
{{< figure src="k8s-resources-40/secret-128.png" alt="secret" >}}
{{< figure src="k8s-resources-40/ep-128.png" alt="ep" >}}
{{< figure src="k8s-resources-40/sa-128.png" alt="sa" >}}
{{< figure src="k8s-resources-40/role-128.png" alt="role" >}}
{{< figure src="k8s-resources-40/c-role-128.png" alt="c-role" >}}
{{< figure src="k8s-resources-40/crb-128.png" alt="crb" >}}
{{< figure src="k8s-resources-40/psp-128.png" alt="psp" >}}
</div>


 
There are many ways to deploy applications to Kubernetes.  What is the optimal way? In the following posts I am going to explore the following methods:
1. **Kubectl**
    - [Kubectl](/posts/kubectl/kubectl/): Content related to Kubectl.

2. **Operator Framework**
    - [Operator Framework](/posts/operator-framework/operator-framework/): Content related to the Operator Framework.

3. **Helm**
    - [Helm](/posts/helm/helm/): Content related to Helm.

4. **Kustomize**
    - [Kustomize](/posts/kustomize/kustomize/): Content related to Kustomize.

5. **Acorn**
    - [Acorn](/posts/acorn/acorn/): Content related to Acorn.

6. **Cue**
    - [Cue](/posts/cue/cue/): Content related to Cue.

7. **Kubefirst**
    - [Kubefirst](/posts/kubefirst/kubefirst/): Content related to Kubefirst.
