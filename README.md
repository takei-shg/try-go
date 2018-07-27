# try-go

- ref. https://outcrawl.com/getting-started-microservices-go-grpc-kubernetes/

# commands

```
docker run --rm -v $(pwd):$(pwd) -w $(pwd) znly/protoc --go_out=plugins=grpc:. -I. gcd.proto
docker build -t local/gcd -f Dockerfile.gcd .
docker build -t local/api -f Dockerfile.api .
kubectl create -f api.yaml
kubectl create -f gcd.yaml
kubectl get services
kubectl describe service api-service
curl http://localhost:{port}/gcd/xxx/yyy
```
