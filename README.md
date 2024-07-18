# YOURLS plugin YourlsBlacklistIPs

YourlsBlacklistIPs is a plugin for [YOURLS](https://yourls.org). It blacklist spammer IPs.
You can define IPs in the format:
- individual IP like 1.2.3.4
- IP ranges like 1.2.3.4-1.2.3.255
- IP ranges in subnet notation like 1.2.3.4/255.255.255.0
- IP ranges in CIDR notation like 1.2.3.4/24

It has been tested on all YOURLS up to v1.7.9 (probably working with newer version too)

## State of this project
This project was taken over to maintain it. It was very stable over 12 years without any modification. But time came where new changes where required.

## INSTALLATION

- go to your yourls installation folder
- here you will find the sub-folder `user/plugins`, `cd` (dive) into it with `cd user/plugins`
- create a new folder named BlackListIP
- In this new directory, copy the `plugin.php` and `ludo_blacklist_ip_Check_IP_Module.php` files from this repository
- Go to the Plugins administration page
- go to *Manage Plugins*
- activate the plugin with hovering over *BlackListIP* row in the column *Action*
- go back to admin home

## Usage / Blocking IPs

You will see in the admin section a new admin page *BlackListIP*. In this section you can now add IP addresses you want to blacklist.

Please enter one IP address per line. 
Other syntax should provide unexpected behaviours!

# Planned features / Roadmap
- support IPv6
- support comments beside of IPs to be able to maintain in a team with info why a IP was blocked
- some code cleanup

# Changelog
- v1.3 : Add several possibilities to provide IP ranges :
   - A.B.C.D-X.Y.Z.T range : all IPs from A.B.C.D to X.Y.Z.T are blacklisted
   - A.B.C.0 range : all IPs from A.B.C.0 to A.B.C.255 are blacklisted
   - A.B.0.0 range : all IPs from A.B.0.0 to A.B.255.255 are blacklisted
   - A.0.0.0 range : all IPs from A.0.0.0 to A.255.255.255 are blacklisted
   - A.B.C.D/X.Y.Z.T : A.B.C.D is an IP address, X.Y.Z.T is a subnet mask, all IPs addresses corresponding to that IP and mask are blacklisted
   - A.B.C.D/T, T between 0 TO 32 : CIDR notation.
- v1.2 : Add some checks on IP format and some warnings for use
- v1.1 : Add admin page
- v1.0 : initialization
