NAME := firefox
CONTAINER := bitschupser/$(NAME)
DATA := ~/.docker/data/$(NAME)

build: Dockerfile
	docker build -t $(CONTAINER) .

run: build
	./docker-firefox.sh $(CONTAINER) $(DATA)
