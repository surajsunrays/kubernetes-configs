## Step by Step instructions to create and use dynamic volume in kubernetes
##### 1. Step 1. <br>
Create Strorage class for storage type that we are using, like <br>
<| Strorage type | StorageClass |<br>
| :------------- | :------------- |<br>
| SSD            | fast           |<br>
| HDD            | slow           |<br>
| ------         | distributed    |<br>
| :------------- | :------------- |<br>
<br>
example filename: sc.yaml<br>
###### Apply the configuration .....
```
kubectl create -f sc.yaml
```
<br>


```
kubectl get storageclass
```

<br>

```
kubectl describe storageclass fast
```

<br>

##### 2. Step 2. <br>
Create PersistentVolumeClaim <br>
example filename: pvc-dv.yaml<br>
###### Apply the configuration

```
kubectl create -f pvc-dv.yaml
```

<br>

```
kubectl get pvc
```

<br>

##### 5. Step 3. <br>
Create Reference claim in pod <br>
example filename: nginx-pv.yaml <br>
###### Apply the configuration

```
kubectl create -f nginx-pv.yaml
```

<br>

```
kubectl get pods -o wide
```

<br>
