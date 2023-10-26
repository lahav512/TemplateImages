.PHONY: build run push

dir_name := $(shell basename $(CURDIR) | tr 'A-Z' 'a-z')

all:
	@echo ${dir_name}

build:
	docker buildx build --pull=false --load --platform linux/amd64 -t ${dir_name} .
	# docker buildx create --use
	# docker buildx build --platform linux/amd64,linux/arm64 -t cuda-sandbox:latest .

run:
	docker run -it ${dir_name}

push:
	docker save "${dir_name}:latest" | gzip > "${dir_name}-image.tar.gz"
	scp ${dir_name}-image.tar.gz gpu-sandbox-git:~
