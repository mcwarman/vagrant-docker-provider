# CentOS 6 - Vagrant Provider Docker Image

## Docker Image
```
docker pull mcwarman/vagrant-provider:centos6
```

## Vagrant File
```
ENV['VAGRANT_DEFAULT_PROVIDER'] = 'docker'

Vagrant.configure("2") do |config|
  config.vm.provider "docker" do |d|
    d.image = "mcwarman/vagrant-provider:centos6"
    d.has_ssh = true
  end
end
```
