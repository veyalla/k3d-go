你好！
很冒昧用这样的方式来和你沟通，如有打扰请忽略我的提交哈。我是光年实验室（gnlab.com）的HR，在招Golang开发工程师，我们是一个技术型团队，技术氛围非常好。全职和兼职都可以，不过最好是全职，工作地点杭州。
我们公司是做流量增长的，Golang负责开发SAAS平台的应用，我们做的很多应用是全新的，工作非常有挑战也很有意思，是国内很多大厂的顾问。
如果有兴趣的话加我微信：13515810775  ，也可以访问 https://gnlab.com/，联系客服转发给HR。
# k3d-go

## k3s in docker

k3s is the lightweight Kubernetes distribution by Rancher: [rancher/k3s](https://github.com/rancher/k3s)

This repository is basically [zeerorg/k3s-in-docker](https://github.com/zeerorg/k3s-in-docker) reimplemented in Golang with some different/new functionality... just because I didn't have time to learn Rust.

Thanks to @zeerorg for the original work!

## Requirements

- docker

## Install

Grab a release from the [release tab](https://github.com/iwilltry42/k3d-go/releases).

or...

## Build

1. Clone this repo, e.g. via `go get -u github.com/iwilltry42/k3d-go/releases`
2. Inside the repo run
   - `make bootstrap` to install build tools and then `make build` to build for your current system
   - `go install` to install it to your `GOPATH`
   - `make build-cross` to build for all systems

## Usage

Check out what you can do via `k3d help`

Example Workflow: Create a new cluster and use it with `kubectl`

1. `k3d create` to create a new single-node cluster (docker container)
2. `export KUBECONFIG=$(k3d get-kubeconfig)` to make `kubectl` to use the kubeconfig for that cluster
3. execute some commands like `kubectl get pods --all-namespaces`
4. `k3d delete` to delete the default cluster

## TODO

- [ ] Use the docker client library instead of commands
- [ ] Test the docker version
- [ ] Improve cluster state management
