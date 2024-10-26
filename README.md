# Minifinance_IAC
## Infrastructure as Code (IaC) with Vagrant and Apache Server Setup (Local Environment Context)

This DevOps project sets up an Apache web server on an Ubuntu 22.04 (Jammy Jellyfish) virtual machine using Vagrant. The server is pre-configured to serve a simple HTML and CSS finance website.

The goal of this project is to learn the basics of Infrastructure as Code (IaC) in a local environment using Vagrant and Vagrant provisioning.

## Requirements

- [Vagrant](https://www.vagrantup.com/downloads) (version 2.x)

- [VirtualBox](https://www.virtualbox.org/wiki/Downloads) (version 6.x or later)

- [Git Bash](https://gitforwindows.org/) (for Windows users): This provides a Unix-like terminal, making it easier to run commands as outlined in this guide.

- macOS users can proceed directly with the instructions without Git Bash.

Make sure to download these tools before proceeding.
## Note
### VM Characteristics

The virtual machine created by this Vagrant setup has the following characteristics:

- **Base Box**: Ubuntu 22.04 (Jammy Jellyfish)
- **Memory Allocation**: 1 GB
- **CPU Allocation**: 1 CPU
- **Storage**: 
  - Disk Size: 10 GB (default size for the base box)
- **Network Configuration**: 
  - Private Network IP: `192.168.56.28`
  - Public Network (optional)
- **Provisioning**: 
  - Apache web server installed and configured
  - Simple HTML and CSS finance website deployed

These specifications provide a lightweight environment suitable for developing and testing web applications locally.


## Getting Started

Follow these steps to set up your Vagrant environment:


1. **Clone the Repository:**

   ```bash
   git clone https://github.com/rdplus2015/minifinance_IAC.git 
   ```
   ```bash
   cd minifinance_IAC
   ```

2. **Initialize the Vagrant Environment:**

   ```bash
   vagrant up  # Run this command in the folder where your Vagrantfile is located
   ```

   This command will download the necessary box, set up the virtual machine, and run the provisioning script to install Apache and download the finance template.


   ### Choosing the Bridge Network Interface

   During the `vagrant up` command, you may be prompted to select a network interface for the bridge connection. This bridge interface allows the VM to access the same network as the host machine. You'll see a list similar to this:

   ```plaintext
   1) wlp0s20f3
   2) enp2s0
   3) vmnet1
   4) vmnet8
   ==> default: When choosing an interface, it is usually the one that is
   ==> default: being used to connect to the internet.
   ==> default: 
   default: Which interface should the network bridge to?
   ```

   To identify which interface to select:

   1. **Identify Your Active Network Interface:**  
      Run the following command in your shell to view your active network interfaces:

      ```bash
      ip a show 
      ```

      Look for the interface connected to the internet (often labeled with `inet <IP address>`).

   2. **Select the Correct Interface:**  
      When prompted, enter the number of the interface connected to the internet. For example, if `wlp0s20f3` is your active Wi-Fi connection, you would enter `1`.

   This selection allows the VM to use the same network as your host, enabling easier access to the internet and local resources.

---


3. **Access the Server:**

   - Open your web browser and navigate to [http://192.168.56.28](http://192.168.56.28) to view the deployed application.

4. **SSH into the VM (Optional):**

   If you need to access the virtual machine for debugging or development, you can use:

   ```bash
   vagrant ssh
   ```

5. **Stop the VM:**

   To stop the virtual machine, run:

   ```bash
   vagrant halt
   ```

6. **Destroy the VM:**

   To completely remove the virtual machine and its resources, run:

   ```bash
   vagrant destroy
   ```

## Provisioning Script

The provisioning script performs the following tasks:

- Updates package lists
- Installs Apache
- Starts and enables the Apache service
- Downloads a finance template and extracts it to the web directory
- Cleans up temporary files

## Customization

Feel free to modify the Vagrantfile and the provisioning script to fit your project's needs.


## Contributing

If you'd like to contribute to this project, please fork the repository and submit a pull request with your changes.

Additionally, you can check the second project of the same type, which uses WordPress instead of a simple HTML and CSS website.  [click here](https://github.com/rdplus2015/wordpress_IAC) 


## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
