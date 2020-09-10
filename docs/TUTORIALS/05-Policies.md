# Policies

### CloudLink key release policies
This topic provides information about the key release policies available in CloudLink.

Before CloudLink Center automatically releases keys, a machine must:

-  Fulfill the requirements of a key release policies.
-  Use an IP address that belongs to an approved network.
-  Belong to an approved location.
-  Not have been previously removed.

Key release policies may be required to enable:
-  A machine to start as part of the prestartup authorization process
-  Access to encrypted data volumes

If a machine does not meet the policies, CloudLink Center puts the machine in the pending state. To enable a key release policy, you must manually select a key release policy. 

### Types of CloudLink key release policies 

**IP Change :**
Applied when the IP address of the machine , that is booted different from the IP stored by Cloudlink Center.

**Moved Machine volume:**
Applied when the volume of a machine is moved to different machine then the volume store by Cloudlink Center.

**Machine Clone:**
Determines wether Cloudlink Center allows a cloned machine to boot automatically.

**Platform Change: **
Determines wether Cloudlink Center allows a machine to boot automatically when it starts up with different platform than the platform recorded in the Cloudlink Center database.

**Integrity change: **
Determines wether Cloudlink Center allows a machine to boot automatically when it starts up with an
integrity value that is different than the integrity value recorded in the Cloudlink Center database. 

### CloudLink pending machine policy

This topic provides information about the CloudLink pending machine policy.

The pending machine policy determines whether or not a machine is placed in the pending state when it connects to CloudLink Center forthe first time. Or, when it connects from a network or location not previously associated with the machine. You can select to allow the machine to automatically register with CloudLink Center, or remain in the pending state and require manual approval.

The following pending machine policy is applicable only to Enterprise and Microsoft Azure and Azure Stack:

**New Machine**—If a new machine that has an approved IP address is added to CloudLink Center, you can choose to allow it to automatically (default) connect to CloudLink Center or require manual approval to connect to CloudLink Center.

This policy applies to VMs.

Change the pending machine policy the same way you change a key release policy. 

### CloudLink Center volume encryption policy

This topic provides information about the volume encryption policy in CloudLink Center.

Volume encryption policy determines which volumes must be encrypted for virtual or physical machines. For example, the All Data volume encryption policy requires that all existing data volumes on a machine be encrypted.

Volume encryption policy applies to boot or data volumes for VMs.

Volume encryption policy is set for a machine group and can be changed at any time. 

For an individual machine in a machine group, you can enable a particular volume to be exempt from the group policy.

### Types of volume encryption policies in CloudLink Center

This topic provides information about the different types of volume encryption policies available in CloudLink Center.
- ** Boot and Manual Data**—The boot volume must be encrypted. Data volumes are not required to be encrypted.
-  **All Data**—Data volumes must be encrypted. The boot volume is not required to be encrypted.
  ○ On Windows machines, data volumes added are automatically encrypted.
  ○ On Linux machines, data volumes (mounted devices) must be manually encrypted.
- ** Boot and All Data**—The boot and all data volumes must be encrypted.
  ○ On Windows machines, data volumes added to the machine are automatically encrypted.
  ○ On Linux machines, data volumes (mounted devices) must be manually encrypted.
-  **Manual**—The boot and data volumes are not required to be encrypted.

NOTE: Key release requires that the boot volume is encrypted. 

