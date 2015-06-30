$SCRIPT = <<SCRIPT
(
yum install -y nc
curl -sSL https://rvm.io/mpapis.asc | sudo gpg2 --import -
curl -L get.rvm.io | bash -s stable
source /etc/profile.d/rvm.sh
rvm requirements
rvm install 2.2
rvm rubygems current
gem install pmap
) > /dev/null 2>&1
SCRIPT

Vagrant.configure(2) do |config|
	config.vm.box = 'puppetlabs/centos-6.6-64-nocm'
	config.vm.provision 'shell', inline: $SCRIPT
	config.ssh.username = 'root'
	config.ssh.password = 'puppet'
	config.ssh.insert_key = 'true'
end
