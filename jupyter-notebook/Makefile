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
	@docker build --tag=minaki/jupyter:plotly .

pull:
	@docker pull jupyter/datascience-notebook 

clean:
	@docker rmi -f minaki/jupyter:plotly

run:
	@docker run -d -p 8888:8888 -v `pwd`/notebooks:/home/jovyan/work -e GRANT_SUDO=yes -e PASSWORD="myjupyter" --user root --name myjupyter minaki/jupyter:plotly start-notebook.sh --NotebookApp.token=''
#	@docker run -d -p 8888:8888 -v `pwd`/notebooks:/home/jovyan/work -e GRANT_SUDO=yes -e PASSWORD="myjupyter" --user root --name myjupyter minaki/jupyter:plotly start-notebook.sh

rm:
	@docker stop myjupyter && docker rm myjupyter


