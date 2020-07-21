.PHONY: build
REGISTRY_URL=hub.lnxsystems.com
PROJECT=jnvilo
IMAGE_NAME=django
TAG=0.0.4

.PHONY: all

all:  build tag push

build:
	docker build -t ${REGISTRY_URL}/${PROJECT}/${IMAGE_NAME}:${TAG} .

pull:   
	docker  pull ${REGISTRY_URL}/${PROJECT}/${IMAGE_NAME}:latest 

tag: 
	docker tag ${REGISTRY_URL}/${PROJECT}/${IMAGE_NAME}:${TAG} ${REGISTRY_URL}/${PROJECT}/${IMAGE_NAME}:latest
 
push:  build tag
	docker push ${REGISTRY_URL}/${PROJECT}/${IMAGE_NAME}:latest
	docker push ${REGISTRY_URL}/${PROJECT}/${IMAGE_NAME}:${TAG}

run:
	docker run --rm -it -p 8000:8000  ${REGISTRY_URL}/${PROJECT}/${IMAGE_NAME}:${TAG}
