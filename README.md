# modern.ie-vagrant

Modern.ie for Vagrant 

To create a new Modern.IE box:
   * Clone this repository
   ```bash
   $ git clone https://github.com/hugsy/modern.ie-vagrant.git win7
   ```  
   * Edit `Vagrantfile` to change the line `VM = VMS[<id>]` where `id` is the index of the box you want to have (default: `Windows 7 / IE11`)
   * For the directory, launch Vagrant the first time with the environment `FIRSTBOOT` set to `1`
   ```bash
   $ cd win7 && FIRSTBOOT=1 vagrant up 
   ```
   _NOTE_: the `FIRSTBOOT` will force Vagrant to show a GUI for the VM, which is required to run the initial scripts and enable WinRM
   * When Windows prompts for the type of network for the new interface, choose either `Home` or `Work` (`public` will make the firewall block 
   all WinRM communications)
   * Once the interface is in `Home` or `Work` environment, execute as Administrator `scripts\RunFirstBoot.bat` (can be found under 
   `\\vboxsrv\vagrant\scripts\RunFirstBoot.bat`)
   
The next boot can be done without the `FIRSTBOOT` environment variable, WinRM and RDP will work properly. 
   
That's it!!
