# Vagrant Provider Docker Image [![Docker Build](https://img.shields.io/docker/automated/mcwarman/interlok-hello-world.svg)](https://hub.docker.com/r/mcwarman/vagrant-provider/)

## Images

| OS                  | Image                               |
|---------------------|-------------------------------------|
| [CentOS 6](centos6) | `mcwarman/vagrant-provider:centos6` |
| [CentOS 7](centos7) | `mcwarman/vagrant-provider:centos7` |

## Usage

Update the `d.image` as required in sample `Vagrantfile`:
```
ENV['VAGRANT_DEFAULT_PROVIDER'] = 'docker'

Vagrant.configure("2") do |config|
  config.vm.provider "docker" do |d|
    d.image = "mcwarman/vagrant-provider:centos7"
    d.has_ssh = true
  end
end
