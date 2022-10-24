# k8s-deployment-with-ingress-spring-boot-api-mysql-

Install Minikube on Linux environment

1. deploy db.yaml file

kubectl apply -f db.yaml

2. deploy deployment.yaml file

kubectl apply -f deployment.yaml 

3. deploy mysql-configMap.yaml mysql-secrets.yaml service.yaml

Kubectl apply -f mysql-configMap.yaml mysql-secrets.yaml service.yaml

3. check whether is successfully deployed or not

kubectl get pods

![image](https://user-images.githubusercontent.com/32263261/197510759-ea883d10-fce6-4430-a322-ad07d8f2fed5.png)

4. Now check spring boot is working or not

 minikube service springboot-k8s-svc --url
 
 curl http://192.168.49.2:32107/orders
 
 ![image](https://user-images.githubusercontent.com/32263261/197511795-1a248057-99bb-43ae-b14b-21b850750488.png)

it's working fine

now add some order data on db use postman to add order details

Post order details.

![image](https://user-images.githubusercontent.com/32263261/197513010-15c6b8e6-f919-46f1-b774-7d72dfeb2a2b.png)

Get order details from Postman App

![image](https://user-images.githubusercontent.com/32263261/197513212-e80c3825-9c4d-47af-a1f5-230d5e69eb38.png)

Previusly it's showing blank after adding some order details now it' showing order details as well

![image](https://user-images.githubusercontent.com/32263261/197513421-82e07ea0-43ca-403a-9ff7-bd51a417dfbe.png)


Now we are going to implement ingress controller show we can expose on external network.

Kubectl apply -f ingress.yaml

kubectl get ing

  ![image](https://user-images.githubusercontent.com/32263261/197514495-cfad1850-b8d9-4ac7-9e2d-de97d92dc9bc.png)






