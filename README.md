### Requirements
| Tool | Link |
| ------ | ------ |
| Vagrant | [https://www.vagrantup.com/downloads.html](https://www.vagrantup.com/downloads.html) |
| Packer | [https://packer.io/downloads.html](https://packer.io/downloads.html) |
| Virtualbox | [https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads) |
| VMWare Fusion (coming soon) | - |

Clone the github repository via the GitHub website or via the Git client (if installed)
Download and install Vagrant
Download Packer and move the binary into your Packer folder
Download and install Virtualbox

Move into our working directory.
```sh
$ cd AnalysisBuild/Packer
```
Now we build and configure the VM. This will download the Win10 ISO from Microsoft, boot it, and install the necessary tools to configure it. This will take a couple hours so do not feel the need to watch it. Red text may display showing errors but it will handle those by itself. If the are fatal errors the operation will stop and display the reason
```sh 
$ packer build --only=virtualbox-iso windows_10.json
```
Move the .box file into our new working directory
```sh 
$ mv windows_10.box ../Boxes
```
Change to our Vagrant directory, import the virtual machine into Virtualbox, boot it, and run it with our Vagrant configuration
```sh 
cd ../Vagrant
``` 
```sh
Vagrant up
```

At this point you have a Windows 10 virtual machine with the following tools installed:  
`FireEye Flare`  
`Sysinternal Suite`

The license assigned to this VM is a 90 trial provided by Microsoft. Feel free to change the license to your own.
Credit:
[https://www.vagrantup.com/downloads.html](https://www.vagrantup.com/downloads.html)