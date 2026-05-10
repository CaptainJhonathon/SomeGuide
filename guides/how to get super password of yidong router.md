# 1. check your CMCC router MAC
	MAC = 3C1060CBB330
# 2. using http address to turn on telnet function in the router
	http:/192.168.1.1/cgi-bin/telnetenable.cgi?telnetenable=1&key=
	(the address above need to add mac to the end!)
# 3. using telnet login
	name: admin
	password: Fh@{last 6 of MAC}
	password(exmaple) Fh@CBB330
# 4. catch root user info
	load_cli factory
	show admin_name
	show admin_pwd

