# CloudLink Agent Download and Installation

### Download and Install CloudLink Agent on Windows and Linux using Custom mode

This topic describes the procedure to download and install CloudLink Agent on Windows and Linux using Custom mode of installation.

### Download and run CloudLink Agent using Custom mode on Windows
Use this procedure to download and run CloudLink Agent using the Custom mode on Windows.
Steps
1. Download the CloudLink Agent installer package. See, Download CloudLink Agent installer package for Windows in Custom mode.
2. Run the installer from the CLI to complete installation and configuration.

### Download CloudLink Agent installer package for Windows in Custom mode
Use this procedure to download the CloudLink Agent installer package for Windows in Custom mode.
Steps
1. Log in to CloudLink Center.
2. From Agents, select Agent Download.
3. From the Downloads page, select the 64-bit Windows Installer package (securevm-windows-x64.msi), and then click
Download Selected.
4. Click Save File.<br>

**Results**
The installer package is downloaded to your Downloads directory.

### Run the CloudLink Agent installer package in Custom mode on Windows
Use this procedure to run the CloudLink Agent installer package on Windows using Custom mode.<br>
**About this task**
After downloading the CloudLink Agent installer package (the securevm-windows-x64.msi file) from CloudLink Center, you can run it from the CLI or by using Windows Installer tools.

**Steps**
1. Go to the folder where the CloudLink Agent installer package is located.
2. From the command line, type the following: 
<br>

    msiexec /i securevm-windows-x64.msi [CLOUDLINKCENTER=clc_address]
    [GROUPCODE=group_code]

where, 
-  CLOUDLINKCENTER=clc_address specifies the CloudLink Center server address. For more information, see CloudLink Center server address. If you do not specify the CloudLink Center server address, the machine is not registered with CloudLink Center. No automatic encryption occurs after deployment. For information about specifying this address following deployment, see Add the CloudLink Center server address or group registration code after deployment.
-  GROUPCODE=group_code specifies the registration code for the machine group to which you want to assign the machine. If you do not specify a registration code, CloudLink Center assigns the machine to the Default machine group. For more information, see Manage CloudLink machines by grouping.

3. When the CloudLink Agent Setup Wizard is displayed, click Install.
4. Click Finish.
5. Wait for the installation to complete.

**Results**
The machine automatically restarts one or more times.

#### Add the CloudLink Center server address or group registration code after deployment

**About this task** <br>
As a deployment option, you might want to omit the CloudLink Center server address when running the MSI file from the CLI. Similarly, you might not have access to the group registration code required to assign a machine to a machine group other than Default. See, Run the CloudLink Agent installer package in Custom mode on Windows.<br>

**Steps** 
Run the following command to add the CloudLink Center server address or group registration code:

    svm /S clc_address [/g group_code]

where, /S clc_address specifies the CloudLink Center server address. For more information, see CloudLink Center server address./g group_code specifies the registration code for the machine group to which you want to assign this machine.

### Verify successful deployment of CloudLink Agent on Windows machines in Custom mode
Verify successful deployment of CloudLink Agent on Windows machines by using one of the following.

• Log in to CloudLink Center, and view the machine status. For information about managing machines, including viewing their status, see the Dell EMC CloudLink Administration Guide.

• In the Windows taskbar, ensure that the icon is displayed. The tooltip displays a message indicating that the machine is connected to CloudLink Center.

### Download, install and configure CloudLink Agent using Custom mode on Linux machines
Use this procedure to download, install, and configure CloudLink Agent using custom mode on Linux machines. 

**Steps**

1. Download the CloudLink Agent deployment package.
2. Install the CloudLink Agent deployment package.
3. Configure CloudLink Agent.

### Download the CloudLink Agent deployment package for Linux in Custom mode

Use this procedure to download CloudLink Agent deployment package for Linux machines in Custom mode.

**Prerequisites**
Update to the latest curl version before downloading the installation script.

**About this task**

CloudLink Agent deployment packages are available as RPM, TGZ, or DEB files which you download from CloudLink Center.

**Steps**

1. Log in to CloudLink Center.
2. Click Agents > Agent Download.
3. On the Downloads page, select the 64-bit Linux package that you want to use. The package URL is displayed below the selected package.
For example,

    securevm.centos.x86_64.rpm

4. In the Linux machine, open a command-line client and enter one of the following commands:
<br>

    wget http://clc_address/cloudlink/agent/url_of_package


    curl –O http://clc_address/cloudlink/agent/url_of_package

where, clc_address is the CloudLink Center server address, and url_of_package is the package URL. The clc_address must be in either the FQDN, IPv4, or IPv6 format.
For example,

    wget http://192.168.112.157/cloudlink/agent/securevm.centos.x86_64.rpm

**Results**
The deployment package is downloaded to the Linux machine to be encrypted.

### Install the CloudLink Agent deployment package for Linux in Custom mode

**About this task**

After downloading the deployment package for your operating system from CloudLink Center, do the following.

**Steps**

Install the package using the package manager for your platform.
NOTE: After CloudLink Agent is installed on a Linux machine and the boot partition is encrypted, kernel upgrades and any upgrades that involve rebuilding the kernel or initrd are not supported.

### Configure CloudLink Agent on Linux machines
Use this procedure to configure CloudLink Agent on Linux machines using Custom mode.

**About this task**
The deployment package installation installs the CloudLink Agent, which provides the svm subcommand for configuring CloudLink Agent.During configuration, the machine is registered with CloudLink Center.

**Steps**
1. Enter the following command to configure CloudLink Agent.

    svm [-v ] [-G group_code]-S clc_address

where,
-  -v uses verbose mode.
-  -G group_code specifies the registration code for the machine group that you want to assign this machine to.
-  -S clc_address specifies the CloudLink Center server address. The clc_address must be in either the FQDN, IPv4, or IPv6 format. For more information, see CloudLink Center server address .
2. Restart the machine.

### Verify successful deployment of CloudLink Agent on Linux machines in Custom mode

**About this task**

Verify CloudLink Agent deployment from the machine CLI and encryption status of volumes or devices by entering the following command:

    svm status

### Refresh data after deployment of CloudLink Agent on Linux machines in Custom mode

**About this task**

For Linux machines, if the networking configuration is changed on the client after CloudLink Agent deployment, refresh the CloudLink Agent service.

**Steps**
Refresh  the CloudLink Agent service from the machine CLI by entering the following command:

    svm refresh
