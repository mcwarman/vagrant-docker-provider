# Vagrant Provider Docker Images [![Docker Build](https://img.shields.io/docker/automated/mcwarman/interlok-hello-world.svg)](https://hub.docker.com/r/mcwarman/vagrant-provider/)

## Images

| OS                                    | Image                                       |
|---------------------------------------|---------------------------------------------|
| [Alpine][alpine]                      | `mcwarman/vagrant-provider:alpine`          |
| [CentOS 6][centos6]                   | `mcwarman/vagrant-provider:centos6`         |
| [CentOS 7][centos7-ssh]               | `mcwarman/vagrant-provider:centos7`         |
| [CentOS 7 - systemd][centos7-systemd] | `mcwarman/vagrant-provider:centos7-systemd` |

## Usage

Update the `d.image` as required in sample `Vagrantfile`:

### alpine

```
ENV['VAGRANT_DEFAULT_PROVIDER'] = 'docker'

Vagrant.configure("2") do |config|
  config.vm.provider "docker" do |d|
    d.image = "mcwarman/vagrant-provider:alpine"
    d.has_ssh = true
  end
end
```

### centos6

```
ENV['VAGRANT_DEFAULT_PROVIDER'] = 'docker'

Vagrant.configure("2") do |config|
  config.vm.provider "docker" do |d|
    d.image = "mcwarman/vagrant-provider:centos6"
    d.has_ssh = true
  end
end
```

### centos7

```
ENV['VAGRANT_DEFAULT_PROVIDER'] = 'docker'

Vagrant.configure("2") do |config|
  config.vm.provider "docker" do |d|
    d.image = "mcwarman/vagrant-provider:centos7"
    d.has_ssh = true
  end
end
```

### centos7-systemd

```
ENV['VAGRANT_DEFAULT_PROVIDER'] = 'docker'

Vagrant.configure("2") do |config|
  config.vm.provider "docker" do |d|
    d.image = "mcwarman/vagrant-provider:centos7-systemd"
    d.has_ssh = true
    d.privileged = true
    d.create_args = ["-v", "/sys/fs/cgroup:/sys/fs/cgroup:ro"]
  end
end
```

[alpine]:          https://github.com/mcwarman/vagrant-docker-provider/tree/master/alpine
[centos6]:         https://github.com/mcwarman/vagrant-docker-provider/tree/master/centos6
[centos7-ssh]:     https://github.com/mcwarman/vagrant-docker-provider/tree/master/centos7/ssh
[centos7-systemd]: https://github.com/mcwarman/vagrant-docker-provider/tree/master/centos7/systemd
