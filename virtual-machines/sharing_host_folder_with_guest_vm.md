# Sharing host folder with guest VM

To access Java source from your IDE, and build the same source code from Ubuntu VBOX-VM 

As tested on *Mac OSX 10.10* running *VirtualBox 4.3.20* with the Ubuntu_12.04_OpenJDK_dev_1 VM.

Create a folder on host machine such as ```~/Public/Java```

Make sure that the Ubuntu VM has guest additions installed:
 - From the menu choose: Device  then  Insert guest CD
 - This should then auto-run.

Add a shared folder to the VM. For "Folder path" browse to the shared folder you created above (eg ```~/Public/Java```)
If this displays a blank window, you might need to press ENTER (the blank window is a confirmation dialogue)

In the VM, cd into the shared folder shown above (eg ```cd /media/sf_Java```), then fetch and build the Java source as described above [ Can we link to another chapter instead of the following (..stuff..)](eg ```hg clone... ; cd jdk9 ; ./get_sources.sh ; bash configure ; make clean images``` )
 - This might require root to allow this, if the  cd  command fails with "Permission denied" then try:  ```sudo -i```
 - TODO Ideally remove this limitation, would be good to run as non-root. An alternative could be to  share the guest's home folder using SMB and map to it from host, some research and configuring is required here, and it has the disadvantage that the VM would need to be running in order to access the jdk source files.