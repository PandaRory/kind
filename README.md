```sh
cd kind/
kind create cluster --name playground --config kind-config.yaml

docker build . -f build/Dockerfile -t demo
kind load docker-image demo-entrypoint:latest --name playground
kind load docker-image demo-command:latest --name playground

k apply -f demo-application.yml
```