
### How to run: 
Build the image file
```sh
cd microservice-one
sudo docker build -t sample-core-api-image .
```

Run the image
```sh
sudo docker run -d --name sample-core-api-container sample-core-api-image
```

To see inside the container
```sh
sudo docker exec -it sample-core-api-container sh
```