# Ultimate-CI-CD-pipeline-Using-Jenkins-and-Sonar-cube
Install Jenkins, configure Docker as agent, set up cicd, deploy applications to k8s and much more.

![image](https://img.shields.io/badge/apache_maven-C71A36?style=for-the-badge&logo=apachemaven&logoColor=white)
![image](https://img.shields.io/badge/Amazon_AWS-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white)
![image](https://img.shields.io/badge/Sonarqube-5190cf?style=for-the-badge&logo=sonarqube&logoColor=white)
![image](https://img.shields.io/badge/Jenkins-D24939?style=for-the-badge&logo=Jenkins&logoColor=white)
![image](https://img.shields.io/badge/Shell_Script-121011?style=for-the-badge&logo=gnu-bash&logoColor=white)
![image](https://img.shields.io/badge/kubernetes-326ce5.svg?&style=for-the-badge&logo=kubernetes&logoColor=white)
![image](https://img.shields.io/badge/Argo%20CD-1e0b3e?style=for-the-badge&logo=argo&logoColor=#d16044)

![argo](https://github.com/saif-15/Ultimate-CI-CD-pipeline-Using-Jenkins-and-Sonar-cube/assets/46129194/ee363fdd-5dbc-420b-b6f2-e03d401287e4)

Create a EC2 instance t2.large in this case because we have to deploy both jenkins and sonarcube server

![1](https://github.com/saif-15/Ultimate-CI-CD-pipeline-Using-Jenkins-and-Sonar-cube/assets/46129194/17058cc9-cd92-4236-9db7-0c64bd48f0a2)

![2](https://github.com/saif-15/Ultimate-CI-CD-pipeline-Using-Jenkins-and-Sonar-cube/assets/46129194/ae9a2823-78fb-4148-a72e-86310550a838)

![3](https://github.com/saif-15/Ultimate-CI-CD-pipeline-Using-Jenkins-and-Sonar-cube/assets/46129194/a9e504a8-2909-48c3-b0c4-9429dca3c64e)

![4 1](https://github.com/saif-15/Ultimate-CI-CD-pipeline-Using-Jenkins-and-Sonar-cube/assets/46129194/d70cb8cc-53e9-4904-bb00-fc9844151538)

Login to instance using ssh

![4](https://github.com/saif-15/Ultimate-CI-CD-pipeline-Using-Jenkins-and-Sonar-cube/assets/46129194/ad9d0b66-caec-4d22-aa3e-f32a12796bdf)

Install Java and verify it

![5](https://github.com/saif-15/Ultimate-CI-CD-pipeline-Using-Jenkins-and-Sonar-cube/assets/46129194/70b11b60-735a-48b8-9b74-1dc62db6adee)

![6](https://github.com/saif-15/Ultimate-CI-CD-pipeline-Using-Jenkins-and-Sonar-cube/assets/46129194/ca5a2dc7-3f5b-4d80-b7ed-c04922580dbd)

Install Jenkins 

![7](https://github.com/saif-15/Ultimate-CI-CD-pipeline-Using-Jenkins-and-Sonar-cube/assets/46129194/698a8a33-3918-47cf-abac-3d0b4b7bdb62)

![8](https://github.com/saif-15/Ultimate-CI-CD-pipeline-Using-Jenkins-and-Sonar-cube/assets/46129194/c7f99854-503b-4a5e-88f0-657f55cafa53)

login in to Jenkins Dashboard Using initial password Running on 8080 port

![10 1](https://github.com/saif-15/Ultimate-CI-CD-pipeline-Using-Jenkins-and-Sonar-cube/assets/46129194/d8f519ab-0f08-4e86-a9b5-695bce306e45)

![9](https://github.com/saif-15/Ultimate-CI-CD-pipeline-Using-Jenkins-and-Sonar-cube/assets/46129194/3b83d1d7-85bf-4c70-8035-c6c14c318a71)

![10](https://github.com/saif-15/Ultimate-CI-CD-pipeline-Using-Jenkins-and-Sonar-cube/assets/46129194/01627622-91a0-4547-aa95-58e6eea199e0)

Create a Pipeline project in Jenkins 

![11](https://github.com/saif-15/Ultimate-CI-CD-pipeline-Using-Jenkins-and-Sonar-cube/assets/46129194/2c5220a1-0114-46de-8d52-883f77cde64c)

![12](https://github.com/saif-15/Ultimate-CI-CD-pipeline-Using-Jenkins-and-Sonar-cube/assets/46129194/a217742f-957b-4136-a4fe-f6facbcb3a07)

![13](https://github.com/saif-15/Ultimate-CI-CD-pipeline-Using-Jenkins-and-Sonar-cube/assets/46129194/efd90b7d-826b-4b81-8d01-e846bb123d3d)

Install Sonar Cube
``` bash
yum install unzip
adduser sonarqube
wget https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-9.4.0.54424.zip
unzip *
chmod -R 755 /home/sonarqube/sonarqube-9.4.0.54424
chown -R sonarqube:sonarqube /home/sonarqube/sonarqube-9.4.0.54424
cd sonarqube-9.4.0.54424/bin/linux-x86-64/
./sonar.sh start
```
Login to Sonar cube Server Running on port 9000

![14](https://github.com/saif-15/Ultimate-CI-CD-pipeline-Using-Jenkins-and-Sonar-cube/assets/46129194/cc4def7b-a53a-4507-a127-45c74ebf9759)

![15](https://github.com/saif-15/Ultimate-CI-CD-pipeline-Using-Jenkins-and-Sonar-cube/assets/46129194/b6454ddb-10b6-4349-b21f-7e3c5ce8a930)

Generate a Token in Sonar Cude and add in secrets in Jenkins

![16](https://github.com/saif-15/Ultimate-CI-CD-pipeline-Using-Jenkins-and-Sonar-cube/assets/46129194/5041d7c6-d3da-40e1-8ec8-8d3bdc610460)

![17](https://github.com/saif-15/Ultimate-CI-CD-pipeline-Using-Jenkins-and-Sonar-cube/assets/46129194/663d0001-ffc5-4b3f-8366-cc9b8cb1f686)

Start The build

![18](https://github.com/saif-15/Ultimate-CI-CD-pipeline-Using-Jenkins-and-Sonar-cube/assets/46129194/a8d5e46c-9070-4f00-839f-17b8b11da091)

![19](https://github.com/saif-15/Ultimate-CI-CD-pipeline-Using-Jenkins-and-Sonar-cube/assets/46129194/973824e5-1ee6-4b8f-9318-ac66c1168940)

![20](https://github.com/saif-15/Ultimate-CI-CD-pipeline-Using-Jenkins-and-Sonar-cube/assets/46129194/659f4a10-433f-45f2-bcfc-1670cf2cc0b2)

Install The Argo CD on the K8s Cluster

```bash
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

Verfiy the Pods

```bash
kubectl get pods -n argocd
```

Expose Argo CD server

```bash
kubectl port-forward svc/argocd-server -n argocd 9090:443
```

Initial Password Argo CD Dashboard

```bash
export argocd_password=$(kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d)
```

![27](https://github.com/saif-15/Ultimate-CI-CD-pipeline-Using-Jenkins-and-Sonar-cube/assets/46129194/cea0827a-894e-4d0d-8319-2f6f3c1d831b)

Create An Application in ArgoCD and configure github.com/saif-15/Microservice as repository

![28](https://github.com/saif-15/Ultimate-CI-CD-pipeline-Using-Jenkins-and-Sonar-cube/assets/46129194/8a81d4d3-cc74-4930-8879-ceece31b041b)

![29](https://github.com/saif-15/Ultimate-CI-CD-pipeline-Using-Jenkins-and-Sonar-cube/assets/46129194/7cc0590d-dfc0-45de-bdb3-1890c7433540)

![30](https://github.com/saif-15/Ultimate-CI-CD-pipeline-Using-Jenkins-and-Sonar-cube/assets/46129194/e007b7cd-b082-4a0a-99c0-eda027bdf1ef)

![31](https://github.com/saif-15/Ultimate-CI-CD-pipeline-Using-Jenkins-and-Sonar-cube/assets/46129194/46604e57-9a7a-4ced-8b69-8b3d53a8afc6)

![32](https://github.com/saif-15/Ultimate-CI-CD-pipeline-Using-Jenkins-and-Sonar-cube/assets/46129194/9c7b7d95-165f-406c-9232-4a08893fd85b)
















