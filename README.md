# Mircrofinance_IAC
## Infrastructure as Code (IaC) with Vagrant and Apache Server Setup (Local Environment Context)

This DevOps project sets up an Apache web server on an Ubuntu 22.04 (Jammy Jellyfish) virtual machine using Vagrant. The server is pre-configured to serve a simple HTML and CSS finance website.

The goal of this project is to learn the basics of Infrastructure as Code (IaC) in a local environment using Vagrant and Vagrant provisioning.

## Requirements

- [Vagrant](https://www.vagrantup.com/downloads) (version 2.x)
- [VirtualBox](https://www.virtualbox.org/wiki/Downloads) (version 6.x or later)

Make sure to download these tools before proceeding.

## Getting Started

Follow these steps to set up your Vagrant environment:

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/rdplus2015/mircrofinance_IAC.git 
   ```
   ```bash
   cd mircrofinance_IAC
   ```

2. **Initialize the Vagrant Environment:**

   ```bash
   vagrant up  # Run this command in the folder where your Vagrantfile is located
   ```

   This command will download the necessary box, set up the virtual machine, and run the provisioning script to install Apache and download the finance template.

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

Additionally, you can check the second project of the same type, which uses WordPress instead of a simple HTML and CSS website.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.