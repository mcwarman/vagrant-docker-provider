# CentOS 7 - Vagrant Provider Docker Image

## Docker Image
```
docker pull mcwarman/vagrant-provider:centos7
```

## Vagrant File
```
ENV['VAGRANT_DEFAULT_PROVIDER'] = 'docker'

Vagrant.configure("2") do |config|
  config.vm.provider "docker" do |d|
    d.image = "mcwarman/vagrant-provider:centos7"
    d.has_ssh = true
  end
end
```
