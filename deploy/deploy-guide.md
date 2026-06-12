# Deploy Guide of Torchspec on Kubernetes Cluster

## Build the Torchspec docker image

Build Docker image and register. The `deploy/Dockerfile` is a docker script that patches docker/sglang/v0.5.10.post1/Dockerfile with the mooncake package built from source to make it work properlly. The image build and registry has been done within the di cluster:

```
cd Torchspec/
docker build -f deploy/Dockerfile -t torchspec:0.1.0-deploy
docker tag torchspec:0.1.0-deploy localhost:30500/torchspec:0.1.0-deploy
docker push localhost:30500/torchspec:0.1.0-deploy
```
