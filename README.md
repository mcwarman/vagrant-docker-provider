# Vagrant Provider

## Images

| OS                                             | Image                                            |
|------------------------------------------------|--------------------------------------------------|
| [Alpine][alpine]                               | `mcwarman/vagrant-provider:alpine`               |
| [CentOS 6][centos6]                            | `mcwarman/vagrant-provider:centos6`              |
| [CentOS 7][centos7-ssh]                        | `mcwarman/vagrant-provider:centos7`              |
| [CentOS 7 - systemd][centos7-systemd]          | `mcwarman/vagrant-provider:centos7-systemd`      |
| [Ubuntu Focal - systemd][ubuntu-focal-systemd] | `mcwarman/vagrant-provider:ubuntu-focal-systemd` |

## Usage

Update the `d.image` as required in sample `Vagrantfile`:

### alpine

```vagrant
ENV['VAGRANT_DEFAULT_PROVIDER'] = 'docker'

Vagrant.configure("2") do |config|
  config.vm.provider "docker" do |d|
    d.image = "mcwarman/vagrant-provider:alpine"
    d.has_ssh = true
  end
end
```

### centos6

```vagrant
ENV['VAGRANT_DEFAULT_PROVIDER'] = 'docker'

Vagrant.configure("2") do |config|
  config.vm.provider "docker" do |d|
    d.image = "mcwarman/vagrant-provider:centos6"
    d.has_ssh = true
  end
end
```

### centos7

```vagrant
ENV['VAGRANT_DEFAULT_PROVIDER'] = 'docker'

Vagrant.configure("2") do |config|
  config.vm.provider "docker" do |d|
    d.image = "mcwarman/vagrant-provider:centos7"
    d.has_ssh = true
  end
end
```

### centos7-systemd

```vagrant
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

### centos7-systemd

```vagrant
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

### ubuntu-focal-systemd

```vagrant
ENV['VAGRANT_DEFAULT_PROVIDER'] = 'docker'

Vagrant.configure("2") do |config|
  config.vm.provider "docker" do |d|
    d.image = "mcwarman/vagrant-provider:ubuntu-focal-systemd"
    d.has_ssh = true
    d.privileged = true
    d.create_args = ["-v", "/sys/fs/cgroup:/sys/fs/cgroup:ro"]
  end
end
```

[alpine]:               https://github.com/mcwarman/vagrant-docker-provider/tree/master/alpine
[centos6]:              https://github.com/mcwarman/vagrant-docker-provider/tree/master/centos6
[centos7-ssh]:          https://github.com/mcwarman/vagrant-docker-provider/tree/master/centos7/ssh
[centos7-systemd]:      https://github.com/mcwarman/vagrant-docker-provider/tree/master/centos7/systemd
[ubuntu-focal-systemd]: https://github.com/mcwarman/vagrant-docker-provider/tree/master/ubuntu-focal/systemd
