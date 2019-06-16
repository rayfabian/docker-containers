
# build the image and tag
# docker build -t  muledevregistry.azurecr.io/mule-ee-openjdk-alpine:4.2.0 .

# run the image
# docker run -it -d --name <container-name> <image-name> 
# docker run -it c3417eb48a94 sh # interactive
# docker run -d  -p 8081:8081 --name mule-ee-4.2.0  muledevregistry.azurecr.io/mule-ee-openjdk-alpine:4.2.0 

# push the image
# az acr login --name muledevregistry.azurecr.io or docker login muledevregistry.azurecr.io
# docker push muledevregistry.azurecr.io/mule-ee-openjdk-alpine:4.2.0
