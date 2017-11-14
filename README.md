# About this Repo

This is the Git repo of the Docker image for [distribution](https://hub.docker.com/r/titanzhang/rpi-docker-registry/).
See the Hub page for the full readme on how to use the Docker image and for information
regarding contributing and issues.

## Build registry binary (Debian:stretch container on Raspbian)
```
sudo apt-get update
sudo apt-get install -y curl git mercurial make  binutils bison gcc build-essential

# Install Go (Debian running on Raspbian)
sudo apt-get install go-land
export GOPATH=$HOME/go

# Install Go (Native Raspbian)
#bash < <(curl -s -S -L https://raw.githubusercontent.com/moovweb/gvm/master/binscripts/gvm-installer)
#source /home/pi/.gvm/scripts/gvm
#gvm install go1.4
#gvm use go1.4 [--default]
#gvm install go1.8
#gvm use go1.8 [--default]

git clone https://github.com/docker/distribution.git
cd distribution
go get ./...

export GOOS=linux
export GOARCH=arm
make binaries
```
