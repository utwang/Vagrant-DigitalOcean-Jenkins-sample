Vagrant.configure('2') do |config|

  config.vm.define "jenkins" do |jenkins|
    config.vm.provider :digital_ocean do |provider, override|
      override.ssh.private_key_path = '~/.ssh/digital_ocean/id_rsa.vagrant'
      override.vm.box = 'digital_ocean'
      override.vm.box_url = "https://github.com/smdahlen/vagrant-digitalocean/raw/master/box/digital_ocean.box"

      provider.hostname = 'mr.jenkins'
      provider.token = '@@@@@'
      provider.image = 'ubuntu-14-04-x64'
      provider.region = 'sgp1'
      provider.size = '1gb'
      provider.ssh_key_name = 'Vagrant'
    end
    config.vm.provision :shell, :path => "jenkins-installer.sh"
  end
end
