# nagios
Collection of various Nagios plugins that need customization.

These scripts have been collected from various sources, but needed customization to work with my hardware.

smart-ups-x3000

This is a plugin, originally from https://gitlab.com/argaar/nagios-plugins/-/blob/master/check%20symmetra%20apc/check_apc.pl 

Unfortunately, not all the OID's are supported by my Smart-UPS X3000 with an AP9651. So, I'll just modify it to work.

Remember to install these:
sudo apt-get install libswitch-perl libsnmp-perl
