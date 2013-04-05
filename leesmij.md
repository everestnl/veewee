#installeer
sudo apt-get install dkms linux-headers-`uname -r`


wget --quiet http://download.virtualbox.org/virtualbox/4.2.10/virtualbox-4.2_4.2.10-84104~Ubuntu~precise_amd64.deb 
sudo dpkg --install virt[..tab..].deb

curl -L https://get.rvm.io | bash -s stable --rails --autolibs=enabled  --ruby=1.9.3
rvm use 1.9.3

gem install bundler
bundle install

bundle exec vagrant basebox templates

bundle exec basebox define 'everprecise64' 'ubuntu-12.04.02-server-amd64'

bundle exec basebox build 'everprecise64'
