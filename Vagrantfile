# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

ENV['VAGRANT_DEFAULT_PROVIDER'] ||= 'docker'

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.define "web" do |web|
    web.vm.provider 'docker' do |d|
      d.cmd     = ["/sbin/my_init", "--enable-insecure-key"]
      d.image   = "phusion/baseimage"
      d.has_ssh = true
    end
    
    web.vm.synced_folder "/srv/microservice", "/srv/www", owner: 'root', group: 'root'

    web.ssh.username = "root"
    web.ssh.private_key_path = "phusion.key"

  end
end




  # config.ssh.private_key_path = ['./vagrant.pem', File.join(ENV['HOME'], '.ssh', 'id_rsa')]
  # config.ssh.forward_agent = true



      # d.image           = 'ubuntu'
      # d.name            = 'cloudspace_webapp2'
      # d.create_args     = ['-i', '-t']
      # d.cmd             = ['/etc/tail -f /var/log']
      # d.remains_running = true
      # d.ports           = ['2222:22']
      # d.has_ssh         = true

      # d.link('gun_crawler_web_postgres:postgres')
      # d.link('gun_crawler_web_elasticsearch:elasticsearch')
      # d.link('gun_crawler_web_redis:redis')


