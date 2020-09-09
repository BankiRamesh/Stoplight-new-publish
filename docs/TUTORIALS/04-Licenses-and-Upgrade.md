# Licenses and Upgrade

CloudLink license files determine the volume of machine instances, Key Management Interoperability Protocol (KMIP) clients, CPU
sockets, encrypted storage capacity, or physical machines with SEDs that your organization can manage using the CloudLink Center.
License files also define the CloudLink Center usage duration. For example, your license might enable you to run 25 machines in CloudLink
Center for 365 days, or encrypt 5 TB of data space in CloudLink Center for perpetuity.<br>
Licensing involves uploading a license file to make it available to CloudLink Center.

    POST https://%clc_address%/cloudlink/rest/license 

### View CloudLink licenses
Use this procedure to view the licenses uploaded in CloudLink Center.<br>
Steps
1. Log in to CloudLink Center.
2. Click System > License.
<br>

    GET https://%clc_address%/rest/license

The CloudLink licenses are displayed. View the following information for each installed license:

• Licensing
- Instance license—Licensed per machine for volume encryption. This license defines the number of machines, virtual, or bare–metal, that can be protected using the CloudLink Center.
- Capacity license—Encrypted capacity for VxFlex OS
- This license defines the total storage that can be encrypted using the CloudLink Center.
- Container license—Enables data encryption for containers. A single Container license supports any number of Kubernetes
- clusters.
- Socket license—Enables encryption licenses to be applied to all machines on a VMware ESXi host. For example, if an ESXi host
- has two sockets, adding that host to the Licensed Hosts allocates part of the socket license and allows an unlimited number of machines to be encrypted when they are deployed on that host.
- Key Management over KMIP license—Licensed KMIP clients
- This license defines the number of KMIP clients that can be managed using the CloudLink Center.
- Key Management for SED license—Number of physical machines with SEDs

- A single Key Management for SEDs license is used per physical machine regardless of the number of SEDs connected to that machine.<br>
• Type—Following are the license types:
○ Subscription—The license expires on a predefined date and time.
○ Perpetual—The license never expires.
• Limit—The maximum number of licensed machine instances, physical machines with SEDs, amount of encrypted capacity, or
KMIP clients.
For Socket licenses, this is the maximum number of sockets across all VMware ESXi hosts that can be licensed.
• Duration—The number of days that the license is valid.
• Start Date—The date that the license takes effect.
• End Date—The date that the license expires
