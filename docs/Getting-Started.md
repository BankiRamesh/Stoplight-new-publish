
# Getting Started

## Introduction to Dell EMC Cloudlink Appliance REST API


Dell EMC CloudLink’s agent-based encryption unlocks native Windows BitLocker and Linux OS encryption features by providing policy-based key management and orchestration. This includes pre-boot authorization to enable boot and data volume encryption in virtual and cloud environments. With CloudLink you define the security policy to permit a virtual machine to start, including verifying the integrity of the VM, which protects against unauthorized modifications. CloudLink ensures that only trusted and verified VMs have the ability to run and access sensitive data residing in the cloud.

### Benefits

- **Uses native OS encryption tools** for optimum performance and to avoid risks inherent in proprietary encryption
- **Protects the entire VM** without re-architecting how your applications store data
- **Supports new, existing and modified VMs **- encrypt existing volumes and additional volumes as they are added
- **Encryption key management remains under your control** - the encryption key store can reside within your enterprise data center
- **Virtual Machine geo-fencing** enables you to ensure that VMs may only be run in approved Azure and Azure Stack regions and thus prevent access to sensitive data if the VMs are migrated outside predefined trusted locations
- **Flexible key storage options** include integration with Azure Key Vault, Active Directory and third party key managers
- **Manage and monitor security** across the hybrid cloud
- **Supported on both Azure and Azure Stack**

### Basic concepts

### REST API endpoint

The Cloudlink REST API endpoint:

    https://%clc_address%/cloudlink/rest/<RESOURCE>

### Best practices

#### **Backward and forward compatibility**

As additional features are added to the product, APIs may change. Observe these common practices when dealing with API changes:

- Deprecated APIs and fields: Do not use them. Deprecated APIs and fields are removed when the infrastructure no longer supports them.
- Handling requests and responses in JSON: Exercise flexibility and tolerance with unrecognized fields and enumerations. New fields and enumerations might be added in support of new features such as a new asset type or new protection type. If you do not use them, ignore these fields and enumerations when they are not recognized.

### Contact

