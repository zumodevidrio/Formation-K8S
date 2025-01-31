# Programme de la formation

<img src="images/olivier.jpg" width="100">

Votre formateur : Olivier Beyler (Certifié CKA, CKS)

## Docker
- [Docker file](Chapitres/DockerFile.md)
- [Principales commandes](Chapitres/DockerCommand.md)
- [Docker registry](Chapitres/DockerRegistry.md) 
- [Docker forces et faiblesses](Chapitres/DockerForceFaiblesse.md)

## Kubernetes
- [Principaux composants K8S](Chapitres/PrincipauxComposants.md)
- [Différentes Topologies de serveur K8S](Chapitres/TopologieK8S.md)
- [Géneralité](Chapitres/Generalite.md)
- [KubeConfig](Chapitres/KubeConfig.md)
- [Principales commandes](Chapitres/Commandes.md)

## Principaux objects / concepts K8S
### Etape 1 mon premier pod
- [Namespace](Chapitres/Namespace.md)
- [Pod](Chapitres/Pod.md)
- [Label Annotation](Chapitres/LabelAnnotation.md) 
- [ConfigMap](Chapitres/ConfigMap.md) 
- [Secret](Chapitres/Secret.md)

### Etape 2 - les autres moyens d'instancier des pods
- [Tour d'horizon](Chapitres/Workload.md)
- [Deployment](Chapitres/Deployment.md)
- [HorizontalPodAutoscaling](Chapitres/HorizontalPodAutoScaling.md)
- [DaemonSet](Chapitres/Daemonset.md)
- [StatefulSet](Chapitres/StatefulSet.md)
- [Job et CronJob](Chapitres/JobCronJob.md)

### Etape 3 - L'exposition
- [Service](Chapitres/Service.md)
- [Ingress / ingress Controller](Chapitres/Ingress.md)

### Etape 4 - la persistence
- [Tour d'horizon de la persistance](Chapitres/Persistence.md)
- [StorageClass](Chapitres/StorageClass.md)
- [PersistentVolume](Chapitres/PersistentVolume.md)
- [PersistentVolumeClaim](Chapitres/PersistentVolumeClaim.md)
 
### Etape 5 - le placement des pods
- [NodeSelector,Resource,Affinity](Chapitres/PodPlacement.md)
- [Taint et Tolération](Chapitres/Taint.md)

### Etape 6 - La sécurité
- [Généralités](Chapitres/Securite.md)
- [RBAC](Chapitres/RBAC.md)
- [SecurityContext](Chapitres/SecurityContext.md)
- [NetworkPolicy](Chapitres/NetworkPolicy.md)
- [Mise à jour](Chapitres/Maj.md) 
- [AdmissionController](Chapitres/AdmissionController.md)

### Etape 7 - Packaging
- [Helm](Tools/Helm)
- [Kustomize](Tools/Kustomize.md)
- [Opérateur](Tools/Operateur.md)

### Etape 8 - Pour aller plus loin
- [PodDisruptionBudget](Chapitres/PodDisruptionBudget.md)
- [ResourceQuota et LimitRange](Chapitres/ResourceQuota.md)
- [ETCD](Chapitres/ETCD.md)

## Mise en pratique
- [Lab 1](Exercices/Lab-001.md) (deploiement pod configmap service secret )  
- [Lab 2](Exercices/Lab-002.md) (le placement)
- [Lab 3](Exercices/Lab-003.md) (RBAC)
- [Lab 4](Exercices/Lab-004.md) (Helm)
- [Lab 5](Exercices/Lab-005.md) ()

## Ecosysteme & outils


- [Metric-server](Tools/MetricServer)
- [Cert-manager](Tools/CertManager.md)
- [Prometheus](Tools/Prometheus.md)
- [Grafana](Tools/Grafana.md)
- [Loki](Tools/Loki.md)
- [Longhorn](Tools/Longhorn.md)
- [Harbor](Tools/Harbor.md)
- [Falco](Tools/Falco.md)
- [Artifactory/Jcr](Tools/Artifactory.md)
- [Rancher](Tools/Rancher.md)
- [Artifacthub.io](https://artifacthub.io)
- [Trivy](Tools/Trivy.md)
### Force / Faiblesse

