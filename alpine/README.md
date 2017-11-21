# Alpine - Vagrant Provider Docker Image

## Docker Image
```
docker pull mcwarman/vagrant-provider:alpine
```

## Vagrant File
```
ENV['VAGRANT_DEFAULT_PROVIDER'] = 'docker'

Vagrant.configure("2") do |config|
  config.ssh.shell = "ash"
  config.vm.provider "docker" do |d|
    d.image = "mcwarman/vagrant-provider:alpine"
    d.has_ssh = true
  end
end
```
