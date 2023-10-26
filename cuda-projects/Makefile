.PHONY: build run push


build:
	export dir_name=${PWD##*/}
	docker buildx build --load --platform linux/amd64 -t ${dir_name} .
	# docker buildx create --use
	# docker buildx build --platform linux/amd64,linux/arm64 -t cuda-sandbox:latest .

run:
	export dir_name=${PWD##*/}
	docker run -it ${dir_name}

push:
	export dir_name=${PWD##*/}
	docker save "${dir_name}:latest" | gzip > "${dir_name}-image.tar.gz"
	scp ${dir_name}-image.tar.gz gpu-sandbox-git:~
