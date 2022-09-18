VERSION=1.0
PREFIX=thanhbao0390/nginx-hello
TAG=$(VERSION)

all: build push

install:
	@echo "Install dependencies:"
	curl -fsSL https://get.docker.com/ | sh
	docker run hello-world
build:
	@echo "Building image:"
	docker build -t $(PREFIX):$(TAG) .
push:
	@echo "Pushing image:"
	docker push $(PREFIX):$(TAG)
test:
	@echo "Running container:"
	docker run --rm -p 8080:8080 $(PREFIX):$(TAG)
