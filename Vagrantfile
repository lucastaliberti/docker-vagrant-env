ENV['VAGRANT_DEFAULT_PROVIDER'] = 'docker'
DOCKER_HOST_NAME = "dockerhost-0"
DOCKER_HOST_VAGRANTFILE = "./DockerHostVagrantfile"

Vagrant.configure("2") do |config|

  config.vm.define "redis" do |a|
    a.vm.provider "docker" do |d|
      d.image = "redis"
      d.name = "redis"
      d.ports = ["6379:6379"]
      d.remains_running = true
      d.vagrant_machine = "#{DOCKER_HOST_NAME}"
      d.vagrant_vagrantfile = "#{DOCKER_HOST_VAGRANTFILE}"
    end
  end

  config.vm.define "node" do |a|
    a.vm.provider "docker" do |d|
      d.build_dir = "node/."
      d.build_args = ["-t=msanand/node"]
      d.name = "node"
      d.ports = ["8080:8080"]
      d.link("redis:redis")
      d.remains_running = true
      d.vagrant_machine = "#{DOCKER_HOST_NAME}"
      d.vagrant_vagrantfile = "#{DOCKER_HOST_VAGRANTFILE}"
    end
  end

end