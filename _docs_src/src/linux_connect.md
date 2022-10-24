# Connecting to BioStore from Windows

You will be using a file sharing protocol called SMB (Server Message Block) to connect to BioSore from your Windows machine.  Before you try to connect, make sure that you have completed the steps on the ["Getting Started"](./getting_started.md) page and are connected to UD's network.  If you are not on campus, this means that you must connect using the [VPN](https://udeploy.udel.edu/software/anyconnect-vpn/).

If you are a Linux user, you probably already know that there are several flavors of Linux.  These instructions are for Ubuntu 20.04, but should be similar across Linux types.

1\. Open up your file manager.

2\. Navigate to 'Other Locations' on the left navigation pane.

3\. Once in 'Other Locations', enter `smb://biostore.dbi.udel.edu` in the box at the bottom labeled "Connect to Server."  Then, hit connect.

<img src="https://udel-cbcb.github.io/biostore_docs/img/linux_connect_to_server.png" alt="Connect to server" width="600" />

4\. A dialogue box will appear and tell you, "Password required for biostore.dbi.udel.edu".  Your username will be the beginning of your udel email (the part before @udel.edu).  The domain will be `[username]@biostore.isilon`, where `[username]` is the same username you entered in the previous box.  Your password should have been set up in previous steps.  After entering the username, domain, and password, hit "Connect."

<img src="https://udel-cbcb.github.io/biostore_docs/img/linux_username_password.png" alt="Linux username and password" width="400" />

5\. You should now be connected to BioStore!  The file manager window will now display some of the directories on BioStore.  You will only be able to access directories where you have permissions and others will appear empty.  Your view mode should look something like this:

<img src="https://udel-cbcb.github.io/biostore_docs/img/linux_biostore_connection.png" alt="BioStore in Linux file manager" width="600" />

6\. Open the directory for your lab/group by double-clicking on the folder.  This will "mount" the directory and it will now appear on the sidebar just above "Other Locations"

<img src="https://udel-cbcb.github.io/biostore_docs/img/linux_mounted_connection.png" alt="BioStore mounted in other locations" width="600" />

Alternatively, you can compress steps 4-6 into a single step by including the name of the volume in the server entry box, as below:

<img src="https://udel-cbcb.github.io/biostore_docs/img/linux_connect_to_server_corefs.png" alt="Connect to server without selecting volume" width="600" />

If you choose to login this way, there will be an additional option in the username and password dialogue box.  Make sure the option "Registered User" is selected.

7\. You will now be able to use BioStore from either your file manager window or the command line.  To access BioStore from the command line, you will need to find the smb mount.  On our test device (Ubuntu 20.04), the location is `ls /run/user/1000/gvfs/smb-share\:server\=biostore.dbi.udel.edu\,share\=your_directory/`, where `your_directory` is the name of the directory for your lab or group's storage (e.g., corefs).  The easiest way to find this path is to drag and drop and folder or file from your BioStore allocation directly into the terminal.

When you are done using BioStore, you can disconnect from the server using the "Disconnect" button.