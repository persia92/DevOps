
### How to run: 
Build the image file
```sh
cd microservice-one
sudo docker build -t microservice-one-image .
```

Run the pod
```sh
kubectl craete -f service-one-pod.yaml
kubectl get pods
```


Run the image
```sh
sudo docker run -d --name microservice-one-container microservice-one-image
```

To see inside the container
```sh
sudo docker exec -it microservice-one-container sh
```