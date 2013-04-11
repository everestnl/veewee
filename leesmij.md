#status
Dit is een fork van veewee met een vbox build voor Everest.
Onder windows vind de opstartende vm de shell scripts niet.
Onder gevirtualiseerde Linux kan niet een embedded 64 bit virtualbox worden gedraaid om te builden. 

#installeer
    sudo apt-get install dkms linux-headers-`uname -r` build-essential


    wget --quiet http://download.virtualbox.org/virtualbox/4.2.10/virtualbox-4.2_4.2.10-84104~Ubuntu~precise_amd64.deb 
sudo dpkg --install virt[..tab..].deb

    curl -L https://get.rvm.io | bash -s stable --rails --autolibs=enabled  --ruby=1.9.3  
    cd veewee
    rvm use 1.9.3

    gem install bundler  
    bundle install

Run het volgende commando om een vbox te builden op basis van de definitie in `definitions/everprecise64`  
    bundle exec vagrant basebox build 'everprecise64'

    bundle exec vagrant basebox export 'everprecise64'
De vbox file is nu in de . directory te vinden.

#pro memorie
De initiele versie van die definitie is gegenereerd met
    bundle exec vagrant basebox templates

    bundle exec vagrant basebox define 'everprecise64' 'ubuntu-12.04.02-server-amd64'
