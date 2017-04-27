all: help

help:
	@echo ""
	@echo "-- Help Menu"
	@echo ""
	@echo "   1. make build            - build image"
	@echo "   2. make pull             - pull image"
	@echo "   3. make clean            - remove image"
	@echo "   4. make run              - run image"
	@echo "   4. make rm               - rm container"
	@echo ""

build:
	@docker build --tag=minaki/chainer .

pull:
	@docker pull chainer:chainer

clean:
	@docker rmi -f minaki/chainer

run:
	@docker run -it -v `pwd`/root:/root/ --name mychainer -p 5000:5000 minaki/chainer /bin/bash

rm:
	@docker stop chainer && docker rm chainer


