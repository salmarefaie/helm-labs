### 1- Add bitnami helm chart repository in the controlplane node.
``` bash 
   helm repo add bitnami https://charts.bitnami.com/bitnami
   helm repo list
```
![Screenshot from 2023-02-12 12-51-02](https://user-images.githubusercontent.com/76884936/218314536-dc654294-768f-4995-b351-dbe08c1105fa.png)

![Screenshot from 2023-02-12 12-52-52](https://user-images.githubusercontent.com/76884936/218314548-6e096ea1-2f39-4e86-86be-4d4bd8748a8d.png)

### 2- Deploy the Apache application on the cluster using the apache from the bitnami repository.
Set the release Name to: amaze-surf
``` bash 
   helm install amaze-surf bitnami/apache
   kubectl get all
```
![Screenshot from 2023-02-12 13-00-33](https://user-images.githubusercontent.com/76884936/218314825-6030d9b6-b7e4-485c-b24a-3faad32c0322.png)

### 3- Uninstall the apache chart release  from the cluster.
``` bash 
   helm delete amaze-surf
   kubectl get all
```
![Screenshot from 2023-02-12 13-02-37](https://user-images.githubusercontent.com/76884936/218314876-a9fbca9c-c33c-49fa-bda8-ddb268534ce9.png)

### 4- install specfic version of nginx 1.22.0, then update it to specfic 1.23.1 ,then rollback
``` bash 
   helm search repo bitnami/nginx --versions
   helm install my-release bitnami/nginx --version 12.0.1
   helm ls -a
   helm upgrade  my-release bitnami/nginx --version 13.1.3
   helm ls -a
   helm rollback my-release 
   helm ls -a
```
![Screenshot from 2023-02-12 16-10-11](https://user-images.githubusercontent.com/76884936/218316166-2132af9c-e39f-4248-a864-289d4c467601.png)

![Screenshot from 2023-02-12 16-12-09](https://user-images.githubusercontent.com/76884936/218316137-c6fb1153-c9f4-47e1-a7ee-e4957fbe8d8d.png)
