# Licenses and Upgrade

CloudLink license files determine the volume of machine instances, Key Management Interoperability Protocol (KMIP) clients, CPU
sockets, encrypted storage capacity, or physical machines with SEDs that your organization can manage using the CloudLink Center.
License files also define the CloudLink Center usage duration. For example, your license might enable you to run 25 machines in CloudLink
Center for 365 days, or encrypt 5 TB of data space in CloudLink Center for perpetuity.<br>
Licensing involves uploading a license file to make it available to CloudLink Center.

    POST https://%clc_address%/cloudlink/rest/license 

##### View CloudLink licenses

    GET https://%clc_address%/cloudlink/rest/license

Response Body:

    [
      {
        "id": "e4e5870872c1d90c017469efb99d0593",
        "licensing_type": "socket",
        "type": "subscription",
        "start_date": "2019-09-20T00:00:00.000Z",
        "end_date": "2020-10-31T00:00:00.000Z",
        "duration": 407,
        "limit": 20,
        "assigned": true,
        "expired": false,
        "deletable": true,
        "status": "active",
        "target_id": "e4e5870872c1d90c017469efb99d0593",
        "platform": "vmware",
        "customer_domain": "Bangalore",
        "serial_number": "9c8f0b0"
      }
    ]

The CloudLink licenses are displayed. View the following information for each installed license:

**Licensing**
- Instance license—Licensed per machine for volume encryption. This license defines the number of machines, virtual, or bare–metal, that can be protected using the CloudLink Center.
- Capacity license—Encrypted capacity for VxFlex OS 
  This license defines the total storage that can be encrypted using the CloudLink Center.
- Container license—Enables data encryption for containers. A single Container license supports any number of Kubernetes clusters.
- Socket license—Enables encryption licenses to be applied to all machines on a VMware ESXi host. For example, if an ESXi host has two sockets, adding that host to the Licensed Hosts allocates part of the socket license and allows an unlimited number of machines to be encrypted when they are deployed on that host.
- Key Management over KMIP license—Licensed KMIP clients<br>
 This license defines the number of KMIP clients that can be managed using the CloudLink Center.
- Key Management for SED license—Number of physical machines with SEDs

- A single Key Management for SEDs license is used per physical machine regardless of the number of SEDs connected to that machine.

**Type**-Following are the license types:
 - Subscription—The license expires on a predefined date and time.
 - Perpetual—The license never expires.<br>
 
**Limit**—The maximum number of licensed machine instances, physical machines with SEDs, amount of encrypted capacity, or KMIP clients.
For Socket licenses, this is the maximum number of sockets across all VMware ESXi hosts that can be licensed.<br>
**Duration**—The number of days that the license is valid.<br>             
**Start Date**—The date that the license takes effect.<br>                                   
**End Date**—The date that the license expires<br>                         

**Delete CloudLink licenses**

Delete a license and replace it with a new license.

    DELETE  https://%clc_address%/cloudlink/rest/license/{license_id}

### Upgrade CloudLink

Use this procedure to upgrade CloudLink.

**Prerequisites**
- Ensure that your account has the Update System permission, which is required to upgrade CloudLink.
- Set CloudLink Vault to Auto Unlock mode before the upgrade begins. This setting allows CloudLink Center to unlock immediately after the upgrade so that all CloudLink Agents can be upgraded. If CloudLink Vault is set to Manual Unlock mode before the upgrade, it remains in Manual Unlock mode after the upgrade and the vault is locked. You can change the vault back to Manual Unlock mode after the upgrade.

**Steps:**
1. Ensure that the CloudLink Vault is set to Auto Unlock mode.
2. Log in to CloudLink Center.
3. Click System > Upgrade.
4. Click Upload.
5. In the Upload ISO dialog box, click to go to the upgrade ISO file, and then click Upload.
If you are upgrading a CloudLink Center cluster, it can take several seconds for the ISO file to upload to all nodes in a cluster. Do not
attempt to upload the ISO file again during this time.
  NOTE: If for any reason the ISO file is not automatically uploaded to all cluster nodes, manually               upload the ISO file to each cluster node.
6. Click Upgrade to start the upgrade process.
7. In the Confirm Host Upgrade dialog box, click Upgrade.

8. Your connection to CloudLink Center is lost during the upgrade process. You are returned to the login screen when the upgrade is complete.

Unlock Coludlink:

    PUT  https://%clc_address%/cloudlink/rest/lockbox/unlock

Get UUDI:

    GET https://%clc_address%/cloudlink/rest/securevm

Upgrade:


    PUT https://%clc_address%/cloudlink/rest/securevm/{uuid}/upgrade




