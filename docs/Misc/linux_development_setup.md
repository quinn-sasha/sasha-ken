- Using UTM
- Cannot set up ssh, why?
- Log in with "ssh 'kenta@192.168.64.2'" from next time
- Need to use our VM for testing and not for development (i.e. compile the kernel in the host machine then install it in the VM)
- Problem when setting up sharing folder using UTM:
	- My mode (VirtFS) needs the guest operating system (ubuntu) to have driver support for 9pfs and VirtIO 
	- I solved this by changing the name of folder to "share" from "virtual"
	- 