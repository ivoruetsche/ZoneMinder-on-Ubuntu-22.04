# ZoneMinder-on-Ubuntu-22.04
Ubuntu 22.04 with ZoneMinder Installation

## Add repository and update it
add-apt-repository ppa:iconnor/zoneminder-1.36
apt update

## Install Zoneminder
apt install zoneminder joe

## Enable ZoneMinder at startup
systemctl enable zoneminder

## Change time zone on system and php.ini
timedatectl set-timezone Europe/Zurich
joe /etc/php/*/apache2/php.ini
	date.timezone = Europe/Zurich

## Enable SSL
a2enmod ssl

## Enable rewriting module
a2enmod cgi rewrite expires headers

## Enable ZoneMinder configuration
a2enconf zoneminder

## Update your installation and reboot
apt -y upgrade
reboot
