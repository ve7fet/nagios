# nagios
Collection of various Nagios plugins that need customization.

These scripts have been collected from various sources, but needed customization to work with my hardware.

smart-ups-x3000

This is a plugin, originally from https://gitlab.com/argaar/nagios-plugins/-/blob/master/check%20symmetra%20apc/check_apc.pl 

Unfortunately, not all the OID's are supported by my Smart-UPS X3000 with an AP9631. So, I'll just modify it to work.

This script has been modified to support additional OID's polled from the UPS (including additional commands added). Since this UPS does not support the "Nominal Battery Voltage" OID, that has been hard-coded to 134V. That is equivalent to 13.4VPC (since there 10x12VDC gel cells in the pack). Additionally, the bat_act_volt command will exit with Critical if the Actual Battery Voltage is detected to be >=6VDC above nominal (ie 140V, equivalent to 14.0VPC), which would be an "overcharge" condition, leading to thermal runaway (which APC is famous for). 

Remember to install these:
sudo apt-get install libswitch-perl libsnmp-perl
