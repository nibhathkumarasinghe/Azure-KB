**Azure Storage**

**Implement and manage storage**

 

**Azure Storage**

 

Azure Storage is a service that you can use to store files, messages,
tables, and other types of information. They are

 

\- Durable and highly available - Redundancy ensures that your data is
safe during transient hardware failures. You replicate data across
datacenters or geographical regions for protection from local
catastrophe or natural disaster

\- Secure -All data written to Azure Storage is encrypted by the service
and provides fine-grained control who have access them

\- Scalable - massively scalable to meet data storage and performance

\- Managed - Microsoft Azure handles hardware maintenance, updates, and
critical issues for you.

\- Accessible - Data in Azure Storage is accessible from anywhere in the
world over HTTP or HTTPS providing SDKs with various languages .NET,
Java, Node.js, Python, PHP, Ruby, Go, and REST API.

 

Azure Storage supports scripting in Azure PowerShell or Azure CLI. And
the Azure portal and Azure Storage Explorer offer easy visual solutions
for working with your data.

 

Azure Storage Categories

 

\- Storage for Virtual Machines- Virtual machine storage includes disks
and files. Disks are persistent block storage for Azure IaaS virtual
machines. Files are fully managed file shares in the cloud.

\- Unstructured Data- Unstructured data includes Blobs and Data Lake
Store. Blobs are highly scalable, REST-based cloud object store. Data
Lake Store is Hadoop Distributed File System (HDFS) as a service.

\- Structured Data- Structured data includes Tables, Cosmos DB, and
Azure SQL DB. Tables are a key/value, autoscaling NoSQL store. Cosmos DB
is a globally distributed database service. Azure SQL DB is a fully
managed database-as-a-service built on SQL.

 

Tiers of Storage accounts

 

\- Standard storage accounts are backed by magnetic drives (HDD) and
provide the lowest cost per GB which allows you to have any data service
(Blob, File, Queue, Table). Double-digit ms latency, 10,000 IOPS,
300-MBps bandwidth

\- Premium storage accounts are backed by solid-state drives (SSD) and
offer consistent low-latency performance. Single-digit ms latency,
100,000 IOPS, 5-GBps bandwidth, can only use file storage accounts with
ZRS storage in a limited number of regions.

 

You can't convert a Standard storage account to a Premium storage
account or vice versa. You must create a new storage account with the
desired type and copy data, if applicable, to a new storage account.

 

**Azure Storage Services**

 

Azure Containers (Blobs) : object storage solution for massive amount of
unstructured data such as text or binary data. Blob storage is ideal
for:

\- Serving images or documents directly to a browser.

\- Storing files for distributed access.

\- Streaming video and audio.

\- Storing data for backup and restore, disaster recovery, and
archiving.

\- Storing data for analysis by an on-premises or Azure-hosted service.

 

Unstructured data is data that doesn't adhere to a particular data model
or definition

 

Objects in Blob storage can be accessed from anywhere in the world via
HTTP or HTTPS. Users or client applications can access blobs via URLs,
the Azure Storage REST API, Azure PowerShell, Azure CLI, or an Azure
Storage client library.

 

Azure Files: enables you to set up highly available network file shares
that can be accessed by using the standard Server Message Block (SMB)
protocol.

 

Azure Files can be used to add to or replace a company's existing
on-premises NAS devices or file servers. One thing that distinguishes
Azure Files from files on a corporate file share is that you can access
the files from anywhere in the world using a URL that points to the file
and includes a shared access signature (SAS) token. You can generate SAS
tokens; they allow specific access to a private asset for a specific
amount of time.

 

There are two built-in methods of data access supported by Azure Files.

1\. direct access via a mounted drive in your operating system

2\. use a Windows server (either on-premises or in Azure) and install
Azure File Sync to synchronize the files between local shares and Azure
Files

 

Common scenarios that file shares can be used.

 

\- Many on-premises applications use file shares where mount file shares
to same drive that application uses

\- Apps and configuration files can be stored on a file share and
accessed from multiple VMs.

\- Diagnostic logs, metrics, and crash dumps are just three examples of
data that can be written to a file share using File REST API and
Developers can then map to the shared folder and run their local
debugging tools

\- use the integrated snapshots feature and set up automatic backups by
using Recovery Services vaults

\- All the data is encrypted in transit by using HTTPS and is stored
encrypted when at rest.

\- The shares are cross-platform, and you can connect to them from
Windows, Linux, or macOS.

\- The storage account credentials are used to provide authentication
for access to the file share.

 

Data migration tool

 

AzCopy

Command-line tool that offers the best performance, especially for a low
volume of small files.

Robocopy

Command-line tool shipped with Windows and Windows Server. AzCopy is
written to be Azure aware and performs better.

Azure Storage Explorer

Graphical file management utility that runs on Windows, Linux, and
macOS.

Azure portal

Use the portal to import files and folders.

Azure File Sync

Can be used to do the initial data transfer, and then uninstalled after
the data is transferred.

Azure Data Box

If you have up to 35 TB of data and you need it imported in less than a
week.

Data Migration Assistant

 

The Data Migration Assistant (DMA) helps you upgrade to a modern data
platform by detecting compatibility issues that can impact database
functionality in your new version of SQL Server or Azure SQL Database.
DMA recommends performance and reliability improvements for your target
environment and allows you to move your schema, data, and uncontained
objects from your source server to your target server.

 

Steps to create and connect Azure File Share

 

1\. Create storage account

2\. Create file shares

3\. Create a VM and connect with RDP protocol

4\. Map drives to Azure File shares

5\. Test the mounted drive

 

Azure Queues: To store and retrieve millions of messages to process them
asynchronously. It can be up to 64 KB

 

Azure Tables: A NoSQL store for seamless storage of structured data
which is part of of Azure Cosmos DB. Table storage is ideal for storing
structured, non-relational data.

 

Kinds of storage accounts

 

\- Standard general-purpose v2 - including Blob, File, Queue, Table, and
Data Lake Storage

\- Premium block blobs - with high trnsactions rates, or scenarios that
use smaller objects or require consistently low storage latency. Premium
BlockBlobStorage doesn’t support access tier.

\- Premium file shares - high performance enterprise file-share
applications. Premium FileStorage doesn’t support tier

\- Premium page blobs - high-performance page blob

 

Azure storage replication

 

Replication strategies

 

To ensure durability and high availability, Azure Storage replication
copies your data so that it is protected from planned and unplanned
events ranging from transient hardware failures, network or power
outages, massive natural disasters. You can choose to replicate your
data within the same data center, across zonal data centers within the
same region, and even across regions.

 

Locally Redundant Storage(LRS)

 

\- Lowest-cost replication option and least durability

\- If DC level disaster occurs, all replicas at be lost and
unrecoverable

\- Appropriate when data is constantly changing, replicating data only
within a country due to data governance requirements, easily
reconstructed if data loss occurs.

 

Zone Redundant Storage(ZRS)

 

\- synchronously replicates your data across three (3) storage clusters
in a single region. Each storage cluster is physically separated from
the others and resides in its own availability zone

\- able to access and manage your data if a zone becomes unavailable

\- provides excellent performance and low latency.

\- ZRS is not yet available in all regions.

\- requires the physical data movement from a single storage stamp to
multiple stamps within a region if changing to ZRS from another data
replication option

\- ZRS currently supports standard general-purpose v2, FileStorage and
BlockBlobStorage storage

 

 

Geo-redundant Storage(GRS)

 

\- replicates your data asynchronously to a secondary region

\- Higher cost and level of durability for you data even if there is a
regional outage( 99.99..% 16 9’s)

\- When GRS or RA- GRS is enabled, all data is first replicated with
locally redundant storage (LRS). The update is then replicated
asynchronously to the secondary region using GRS

\- Both the primary and secondary regions manage replicas across
separate fault domains and update domains within a storage scale unit.

\- GRS replicates your data to another data center in a secondary
region, but that data is available to be read only if Microsoft
initiates a failover from the primary to secondary region.

\- With RA-GRS(Read-access geo-redundant storage), you can read from the
secondary region regardless of whether Microsoft initiates a failover
from the primary to the secondary.

 

 

Geo-zone redundant storage(GZRS)

 

 

\- GZRS storage account is replicated across three Azure availability
zones in the primary region and also replicated to a secondary
geographic region for protection from regional disasters

\- can continue to read and write data if an availability zone becomes
unavailable or is unrecoverable

\- provide at least 99.99999999999999% (16 9's) durability

\- can optionally enable read access to data in the secondary region
with read-access geo-zone-redundant storage (RA-GZRS).

 

Changing replication settings has two options

 

1\. Manual migration

2\. Live migration

 

If you are migrating from LRS in the primary region to ZRS in the
primary region or vice versa, then you must perform either a manual
migration or a live migration.

 

Manual migration

 

\- provides more flexibility than a live migration

\- Can control the timing of a manual migration if you need the
migration to complete by a certain date

\- manual migration can result in application downtime

\- When storage account is replicated in the primary region, by moving
from LRS to ZRS or vice versa

\- can migrate an LRS account to a GZRS or RA-GZRS account in one step

\- Premium storage accounts must be migrated manually

\- To perform a manual migration, you can use one of the following
options:

 

1\. Copy data by using an existing tool such as AzCopy, one of the Azure
Storage client libraries, or a reliable third-party tool.

2\. If you're familiar with Hadoop or HDInsight, you can attach both the
source storage account and destination storage account to your cluster.

 

Live migration

 

\- migrate your storage account from LRS to ZRS in the primary region
with no application downtime

\- During a live migration, you can access data in your storage account
with no loss of durability or availability where Azure Storage SLA is
maintained

\- In the standard performance tier, LRS supports general-purpose v2
accounts only for a live migration to ZRS

\- there's no guarantee as to when a live migration will complete

\- Live migration is supported only for storage accounts that use LRS or
GRS replication

\- Standard storage account types support live migration.

 

 

Scenarios;

 

1\. To migrate from LRS to GZRS or RA-GZRS, first switch to GRS or
RA-GRS and then request a live migration. Similarly, you can request a
live migration from GRS or RA-GRS to GZRS or RA-GZRS.

2\. To migrate from GRS or RA-GRS to ZRS, first switch to LRS, then
request a live migration.

3\. If your account uses RA-GRS, then you need to first change your
account's replication type to either LRS or GRS before proceeding with a
live migration

 

Access storage

 

Azure Storage has a unique URL address that forms the subdomain of that
address. For example, if your storage account is named mystorageaccount,
then the default endpoints for your storage account are:

\- For blob Container service: //mystorageaccount.blob.core.windows.net

 

\<storage-account-name\>.blob.core.windows.net

 

Configure custom domain

 

\- Direct CNAME mapping for example, to enable a custom domain for the
blobs.contoso.com sub domain to an Azure storage account, create a CNAME
record that points from blobs.contoso.com to the Azure storage account
\[storage account\].blob.core.windows.net.

\- Intermediary mapping with asverify Mapping a domain that is already
in use within Azure may result in minor downtime as the domain is
updated. To avoid downtime, you can use the asverify subdomain to
validate the domain.

 

Secure storage endpoints

 

\- By default, storage accounts accept connection from clients on any
network. To deny access by default, choose allow access from “selected
network”

\- Firewalls and Virtual Networks service endpoint restrict access to
the Storage Account from specific Subnets on Virtual Networks or public
IPs. This includes network-based access control protections as well as
authentication and authorization-based protections.

\- Service endpoints also provide optimal routing for Azure traffic over
the Azure backbone in scenarios where Internet traffic is routed through
virtual appliances or on-premises. Service endpoints are available for
the Azure services and regions. The Microsoft.\* resource is in
parenthesis.

\- There is no additional billing for virtual network access through
service endpoints

\- Subnets and Virtual Networks must exist in the same Azure Region or
Region Pair as the Storage Account.

 

Storage accounts

 

A storage account is a container that groups a set of Azure Storage
services together. Only data services from Azure Storage can be included
in a storage account (Azure Blobs, Azure Files, Azure Queues, and Azure
Tables). The settings and changes are applied to everything in the
account. Deleting storage account deletes all the data stores in it.

 

A storage account is an Azure resource and is included in a resource
group. Other Azure data services like Azure SQL and Azure Cosmos DB are
managed as independent Azure resources and cannot be included in a
storage account.

 

Storage account settings

 

A storage account defines a policy that applies to all the storage
services in the account based on following settings. The settings that
are defined by a storage account are:

 

Subscription: The Azure subscription that will be billed for the
services in the account.

 

Location: The datacenter that will store the services in the account.

 

Performance: Determines the data services you can have in your storage
account and the type of hardware disks used to store the data.

 

Replication: Determines the strategy used to make copies of your data to
protect against transient hardware failure, network or power outages or
massive natural disaster. At a minimum, Azure will automatically
maintain three copies of your data within the data center associated
with the storage account. This is called locally-redundant storage
(LRS), and guards against hardware failure but does not protect you from
an event that incapacitates the entire datacenter. You can upgrade to
one of the other options such as geo-redundant storage (GRS) to get
replication at different data centers across the world.

 

Access tier: Controls how quickly you will be able to access the blobs
in this storage account. Hot gives quicker access than Cool, but at
increased cost.

 

Secure transfer required: A security feature that determines the
supported protocols for access. Enabled requires HTTPs, while disabled
allows HTTP.

 

Virtual networks: A security feature that allows inbound access requests
only from the virtual network(s) you specify.

 

The number of storage accounts you need is typically determined by your
data diversity, cost sensitivity, and tolerance for management overhead.

 

Data diversity: Organizations often generate data that differs in where
it is consumed(location), how sensitive it (public or private data) is,
which group pays the bills(subscription etc. In general, increased
diversity means an increased number of storage accounts.

 

Cost sensitivity: A storage account by itself has no financial cost;
however, the settings you choose for the account do influence the cost
of services in the account. For an instance, critical data with GRS and
non-critical data with LRS.

 

Tolerance for management overhead: Administrators are responsible to
reduce complexity of storage account by analyzing of your data and
create partitions that share characteristics like location, billing, and
replication strategy, and then create one storage account for each
partition.

 

Account settings

 

We will discuss the three settings that apply to the account itself,
rather than to the data stored in the account:

 

Name : globally unique name for storage account within Azure, use only
lowercase letters and digits and be between 3 and 24 letters and
numbers. The name will be used to generate the public URL used to access
the data in the account.

 

Deployment model: the system Azure uses to organize your resources. The
model defines the API that you use to create, configure, and manage
those resources.

 

\- Resource Manager: the current model that uses the Azure Resource
Manager API

\- Classic: a legacy offering that uses the Azure Service Management API

 

The key feature difference between the two models is their support for
grouping where only Resource Manager supports. Storage accounts, virtual
machines, and virtual networks support both models.

 

Account kind: Storage account kind is a set of policies that determine
which data services you can include in the account and the pricing of
those services. There are three kinds of storage accounts:

 

StorageV2 (general purpose v2)

 

\- the current offering that support all of the latest features for
blobs, files, queues, and tables

\- It delivers lowest per-gigabyte capacity prices for azure storage and
industry competitive transaction prices.

\- supports access tier for Blob service and for Azure file.

 

Storage (general purpose v1)

 

\- a legacy kind that supports all storage types but may not support all
latest features or the lowest per gigabyte pricing.

\- Doesn’t support access tier

 

Blob storage

 

\- a legacy kind that allows only block blobs and append blobs

\- support all the same block blob features as GPv2, but are limited to
supporting only block blobs.

\- Object storage data tiering between hot, cool, and archive is
supported

 

 

The archive tier supports only LRS, GRS, and RA-GRS.

 

The core advice here is to choose the Resource Manager deployment model
and the StorageV2 (general purpose v2) account kind for all your storage
accounts.

 

Upgrading to a general-purpose v2 storage account from your
general-purpose v1 or Blob storage accounts is straightforward. You can
upgrade using the Azure portal, PowerShell, or Azure CLI. There is no
downtime or risk of data loss associated with upgrading to a
general-purpose v2 storage account.

 

Tools to create storage account

 

Available tools based on if you want a GUI and whether you need
automation.

\- Azure Portal

\- Azure CLI (Command-line interface)

\- Azure PowerShell

\- Management client libraries

 

The Azure CLI and Azure PowerShell let you write scripts for automation,
while the management libraries allow you to incorporate the creation
into a client app where scripting is a better option.

 

When you create storage account in Azure portal: subscription, resource
group, storage account name, region, performance, redundancy as basic.

 

As advanced settings, use following.

 

Security :

\- Require secure transfer for REST API operations- controls whether
HTTP can be used for the REST APIs that access data in the storage
account. Setting this option to enable forces all clients to use SSL
(HTTPS).

\- Enable blob public access- allow clients to read data in that
container without authorizing the request.

\- Minimum TLS version - TLS 1.2 is the most secure version of TLS and
is used by Azure Storage on public HTTPS endpoints.

 

Data Lake Storage Gen 2 : Enable hierarchical namespace for big-data
application

 

Blob storage :

\- Access tier- Hot access tier is ideal for frequently accessed data,
Cool access tier is better for infrequently accessed data

 

Azure Files:

\- Enable large file shares- Large file shares provide support up to a
100 TiB

 

Networking

\- Connectivity method - We want to allow public Internet access as our
content are public facing

\- Network routing - use of the Microsoft global network that is
optimized for low-latency path selection.

 

Data Protection

\- Enable soft delete for blobs - Soft delete lets you recover your blob
data in many cases

\- Enable soft delete for file shares- soft delete lets you recover your
blob data more easily at the folder level.

 

After selecting these settings, it may take up to two minutes to deploy
storage account.

 

Create storage account with Azure CLI;

 

az storage account create \\

--name \<unique account name\> \\

--resource-group \<resource group name\> \\

--sku Standard_GRS

 

 

Type of disk storage for VM workload

 

Disk roles

 

OS Disk : One disk in each virtual machine contains the operating system
files and virtual machine image. The OS disk has a maximum capacity of 4
TB. Maximum OS disk size for generation VM is 2TB.

 

Data disk : You can add one or more data virtual disks to each virtual
machine to store data. For example, database files, website static
content, or custom application code. The number of data disks you can
add depends on the virtual machine size. Maximum data disk size 4 TB.

 

Temporary disk: a single temporary disk, which is used for short-term
storage applications such as page files and swap files. The contents of
temporary disks are lost during maintenance events, so don't use these
disks for critical data.

 

These disks are local to the server and aren't stored in a storage
account.

 

Ephemeral OS Disks

 

\- virtual disk that saves data on the local virtual machine storage.

\- faster read-and-write latency than a managed disk.

\- individual virtual machine failure might destroy all the data on an
ephemeral disk and leave the virtual machine unable to boot as ephemeral
disk resides locally

\- can reset the failed virtual machine to its original boot state
rapidly and get it back up and running faster than if it used managed
disks.

\- host a stateless workload, such as the business logic for a multitier
website or a microservice.

 

Managed Disks

 

\- virtual hard disk for which Azure manages all the required physical
infrastructure for virtual machines in Azure

\- Easy to provision them and attach them to virtual machines.

\- Virtual hard disks in Azure are stored as page blobs in an Azure
Storage account, but you don't have to create storage accounts, blob
containers, and page blobs or maintain this infrastructure.

 

Benefits of managed disks

 

\- Simple scalability- can create up to 50,000 managed disks of each
type in each region in your subscription.

\- High availability- Managed disks support 99.999% availability by
storing data three times.

\- Integration with availability sets and zones- If you place your
virtual machines into an availability set, Azure automatically
distributes the managed disks for those machines into different fault
domains and use availability zones, which distribute data across
multiple data centers

\- Support for Azure Backup- Azure Backup natively supports with
encrypted disks.

\- Granular access control- use Azure role-based access control (RBAC)
to grant access to specific user accounts for specific operations

\- Support for encryption - To protect sensitive data on a managed disk
from unauthorized access by using Azure Storage Service Encryption (SSE)
and Azure Disk Encryption (ADE), which uses BitLocker for Windows
virtual machines, and DM-Crypt for Linux virtual machines

 

Unmanaged Disks

 

\- you create and maintain this storage account manually in which you
have to keep track of IOPS( number of read and write operation per
second) limits within a storage account and ensures that you don't
overprovision throughput of your storage account.

\- like a managed disk, is stored as a page blob in an Azure Storage
account.

\- must also manage the security and RBAC access at the storage account
level

\- don't support all of the scalability and management features that
you've seen for managed disks

\- Originally, all virtual hard disks in Azure were unmanaged. If you're
running an old virtual machine. You can convert those unmanaged disks to
managed disks by using the PowerShell cmdlet.

 

ConvertTo-AzureRmVmManagedDisk

 

To use unmanaged disks, expand the Advanced section on the Disks page of
the Create a virtual machine wizard

 

Disk Types for VM

 

Disk performance measures

 

\- Input/output operations per second (IOPS)- IOPS measure the rate at
which the disk can complete a mix of read and write operations. Higher
performance disks have higher IOPS values.

\- Throughput - It measures the rate at which data can be moved onto the
disk from the host computer and off the disk to the host computer.
Throughput is also called data transfer rate and is measured in
megabytes per second (MBps). Higher performance disks have higher
throughput.

 

Disk Types

 

Ultra SSD

 

\- highest disk performance available in Azure which includes high
throughput, high IOPS, and low latency.

\- The performance of an Ultra Disks depends on the size you select
which have capacities from 4 GB up to 64 TB

\- A unique feature of Ultra Disks is that you can adjust the IOPS and
throughput values while they're running and without detaching them from
the host virtual machine

\- Performance adjustments can take up to an hour to take effect.

\- Can use for some workloads place intensive loads on disk storage such
as top-tier databases and SAP HANA

\- Supports for all disk types

 

Limitation of Ultra disk

 

1\. They can only be attached to virtual machines that are in
availability zones.

2\. They can only be used as data disks and can only be created as empty
disks.

3\. They don't support disk snapshots, virtual machine images, Azure
Disk Encryption, Azure Backup, or Azure Site Recovery.

 

Premium SSD

 

\- next tier down from Ultra Disks in terms of performance

\- Premium disks don't have the current limitations of Ultra Disks For
example, they're available in all regions and can be used with virtual
machines that are outside of availability zones.

\- can't adjust performance without detaching these disks from their
virtual machine.

\- You can migrate a disk to a premium at any time if you found
performance is good enough

 

Standard SSD

 

\- Cost effective storage option and next tier down from Ultra Disks and
Premium SSD

\- Use Standard SSDs when you have budgetary constraints and a workload
that isn't disk intensive. For example, web servers, lightly used
enterprise applications

 

Standard HDD

 

\- data is stored on conventional magnetic disk drives with moving
spindles

\- slower and speeds are more variable than for SSDs

\- latencies are under 10 ms for write operations and 20 ms for reads

 

 

Manage Storage

 

Azure Storage Explorer

 

Azure Storage Explorer is a standalone app that makes it easy to work
with Azure Storage data on Windows, macOS, and Linux. With Storage
Explorer, you can access multiple accounts and subscriptions and manage
all your storage content. Storage Explorer can use to upload and
download data from blob storage.

 

Storage Explorer requires both management (Azure Resource Manager) and
data layer permissions(Azure AD).

 

Connecting to storage

 

Storage explorer is used to connect;

\- storage accounts associated with your Azure subscriptions

\- storage accounts and services that are shared from other Azure
subscriptions

\- manage local storage by using the Azure Storage Emulator.

\- storage resources and specific storage service (blob container,
queue, or table) that belong to another Azure subscription by using a
shared access signature (SAS)

\- Cosmos DB account by using a connection string.

 

 

Accessing external storage accounts use the account name, account key,
storage endpoints domain drop-down to select Other and then enter the
custom storage endpoint domain.

 

Access keys

 

\- Provide access to the entire storage account

\- Store your access keys securely

\- recommend regenerating your access keys regularly

\- You are provided two access keys so that you can maintain connections
using one key while regenerating the other

\- When you regenerate your access keys, you must update any Azure
resources and applications that access this storage account to use the
new keys. This action will not interrupt access to disks from your
virtual machines.

 

 

Azure Import/Export service

 

\- use to securely import large amounts of data to Azure Blob storage
and Azure Files by shipping disk drives to an Azure datacenter

\- can also be used to transfer data from Azure Blob storage to disk
drives and ship to your on-premises sites

\- Can use your own disk drives or disk drives supplied by Microsoft,
you can use Azure Data Box Disk where You can quickly configure disk
drives, copy data to disk drives over a USB 3.0 connection, and ship the
disk drives back to Azure

\- Use Azure portal or Azure Resource Manager REST API to create jobs.

\- Each job is associated with a single storage account.

\- It requires the use of internal SATA II/III HDDs or SSDs

 

Azure Import/Export service supports the following of storage accounts:

 

✑ Standard General Purpose v2 storage accounts (recommended for most
scenarios)

✑ Blob Storage accounts

✑ General Purpose v1 storage accounts (both Classic or Azure Resource
Manager deployments)

 

Azure Import/Export service supports the following storage types:

 

✑ Import supports Azure Blob storage and Azure File storage

✑ Export supports Azure Blob storage. Azure Files not supported.

 

Use cases Azure Import/Export

 

1\. Data migration to the cloud quickly and cost effectively

2\. Quickly send data to your customer sites

3\. Take backups of your on-premises data to store in Azure Storage

4\. Recover large amount In storage and deliver to your on-premise

 

Import/Export components

 

Import/Export service: This service available in Azure portal helps the
user create and track data import (upload) and export (download) jobs

 

WAImportExport tool: This is a command-line, drive preparation and
repair tool that does the following

\- Facilitates copying your data to disk drive that are shipped for
import

\- Encrypts the data on the drive with AES 256-bit BitLocker. You can
use an external key protector to protect your BitLocker key.

\- Generates the drive journal files used during import creation.
Journal files are necessary to create an import/export job and help
ensure the integrity of the data transfer.

\- Helps identify numbers of drives needed for export jobs.

\- After an import job or export job has completed, you can use this
tool to repair any blobs that were corrupted, were missing, or
conflicted with other blobs.

 

Disk Drives: You can ship Solid-state drives (SSDs) or Hard disk drives
(HDDs) to the Azure datacenter.

 

Import into Azure Job

 

Import job allows you to import data into Azure Blobs or Azure files.
You ship drives containing your data for import job

 

Steps inside import job

 

1\. Create an Azure Storage account

2\. Determine data to be imported, number of drives you need,
destination blob location for your data in Azure storage.

3\. Identify a computer that you will use to perform the data copy,
attach physical disks that you will ship to the target Azure datacenter,
and install the WAImportExport tool.

4\. Run the WAImportExport tool to copy data to disk drives. Encrypt the
disk drives with BitLocker.

5\. Create an import job in your target storage account in Azure portal.
Upload the drive journal files.

6\. Provide the return address and carrier account number for shipping
the drives back to you.

7\. Ship the disk drives to the shipping address provided during job
creation.

8\. Update the delivery tracking number in the import job details and
submit the import job.

9\. The drives are received and processed at the Azure data center by
their staff

10\. The drives are shipped using your carrier account to the return
address provided in the import job.

 

Export from Azure Job

 

Export job allows you to export data from Azure Blobs or Azure files.
When you create an export job, you ship empty drives to an Azure
datacenter. In each case, you can ship up to 10 disk drives per job.

 

Steps inside export job

 

1\. Determine the data to be exported, number of drives you need, source
blobs or container paths of your data in Blob storage.

2\. Create an export job in your source storage account in Azure portal.

3\. Specify source blobs or container paths for the data to be exported.

4\. Provide the return address and carrier account number for shipping
the drives back to you.

5\. Ship the disk drives to the shipping address provided during job
creation.

6\. Update the delivery tracking number in the export job details and
submit the export job.

7\. Once the disks arrive at the destination, Azure datacenter staff
will carry out data copy from the storage account to the disks that you
provide, drives are encrypted with BitLocker and the keys are available
via the Azure portal.

8\. The drives are shipped using your carrier account to the return
address provided in the import job.

9\. The BitLocker keys will be available in the Azure portal, allowing
you to decrypt the content of the disks and copy them to your
on-premises storage.

 

Copy data using AZCopy

 

AzCopy v10 is the next-generation command-line utility for copying data
to/from Microsoft Azure Blob and File storage, which offers a redesigned
command-line interface and new architecture for high-performance
reliable data transfers.

 

Using AzCopy, you can copy data between a file system and a storage
account, or between storage accounts. Synchronize a file system to Azure
Blob or vice versa. Ideal for incremental copy scenarios. AzCopy is
available on Windows, Linux, and macOS.

 

New features

 

\- Supports Azure Data Lake Storage Gen2 APIs.

\- Supports copying an entire account (Blob service only) to another
account.

\- Account to account copy is now using the new Put from URL APIs. No
data transfer to the client is needed which makes the transfer faster.

\- Supports wildcard patterns in a path, --include flags, and --exclude
flags.

\- Improved resiliency: every AzCopy instance will create a job order
and a related log file. You can view and restart previous jobs and
resume failed jobs. AzCopy will also automatically retry a transfer
after a failure.

 

Authentication options

 

\- Azure Active Directory (Supported for Blob and ADLS Gen2 services).
Use .\azcopy login to sign in using Azure Active Directory. The user
should have Storage Blob Data Contributor role assigned

\- SAS tokens (supported for Blob and File services). Append the SAS
token to the blob path on the command line to use it.

 

 

azcopy sync command replicates the source location to the destination
location. However, the file is skipped if the last modified time in the
destination is more recent.

 

azcopy copy command copies a directory (and all the files in that
directory) to a blob container. The result is a directory in the
container by the same name.

 

azcopy copy \[source\] \[destination\] \[flags\]

 

az storage blob copy start-batch command copies multiple blobs to a blob
container.

 

azcopy make \[resourceURL\] \[flags\] command Create a container or file
share represented by the given resource URL.

 

azcopy make '<https://mystorageaccount.blob.core.windows.net/vmimages> ;
create the container using planned on-premises virtual machine image

 

 

Azure Files and Azure Blob Storage

 

Azure Files Share

 

File storage offers shared storage for applications in Azure virtual
machines and cloud services using the industry standard SMB protocol.
Any number of Azure virtual machines or roles can mount and access the
File storage share simultaneously. File storage uses for following
common use.

 

\- Replace and supplement- To completely replace or supplement
traditional on-premises file servers or NAS devices.

\- Access anywhere- Windows, macOS, and Linux can directly mount Azure
File shares wherever they are in the world.

\- Lift and shift- easy to "lift and shift" applications to the cloud
that expect a file share to store file application or user data

\- Azure File Sync- Azure File shares can also be replicated with Azure
File Sync to Windows Servers, either on-premises or in the cloud

\- Shared applications- Storing shared application settings such as in
configuration files

\- Diagnostic data - Storing diagnostic data such as logs, metrics, and
crash dumps in a shared location.

\- Tools and utilities- Storing tools and utilities needed for
developing or debugging or administering Azure virtual machines or cloud
services.

 

Deployment options

 

Direct mount of an Azure file share: Since Azure Files provides SMB
access, you can mount Azure file shares on-premises or in the cloud
using the standard SMB client available in Windows, macOS, and Linux.
Azure file shares are serverless. This means you don't have to apply
software patches or swap out physical disks

 

Cache Azure file share on-premises with Azure File Sync: Azure File Sync
enables you to centralize your organization's file shares in Azure
Files. Azure File Sync transforms an on-premises (or cloud) Windows
Server into a quick cache of your Azure file share

 

Other distinguishing features, when selecting Azure files.

\- Azure files are true directory objects. Azure blobs are a flat
namespace.

\- Azure files are accessed through file shares. Azure blobs are
accessed through a container.

\- Azure files provide shared access across multiple virtual machines.
Azure disks are exclusive to a single virtual machine

 

Manage file shares

 

To access your files, you will need a storage account to be created,
provide the file share Name and the Quota which refers to total size of
files on the share.

 

Azure Files uses SMB protocol. SMB communicates over TCP port 445. Your
ISP or organization may block SMB port, however you may use Azure
Site-to-Site(S2S) VPN, Point-to-Site(P2S) VPN or ExpressRoute tunnel SMB
traffics to Azure File share over different port.

 

\- Mapping file shares Windows - To connect from your file share page
from Windows or Windows server by running PowerShell command on elevated
terminal

\- Mounting file share Linux - To connect from your file share page from
Linux server by running mount command using the CIFS kernel client

 

In order to mount Azure file share outside of Azure region it is hosted
in such as on-premise or different region, OS must support encryption
functionality of SMB 3.0.

 

Secure transfer option enhances the security of your storage account
such as when calling REST APIs to access your storage accounts, you must
connect using HTTPs.

 

File share snapshot

 

\- Azure Files provides the capability to take share snapshots that
capture a point-in-time, read-only copy of your data

\- Retrieval is provided at the individual file level

\- You cannot delete a share that has share snapshots unless you delete
all the share snapshots first

\- Only the data that has changed after your most recent share snapshot
is saved as incremental snapshot where it takes most recent share
snapshot in order to restore the share

 

Use cases of file share snapshot

 

\- Protection against application error and data corruption - To protect
against an application is misconfigured or an unintentional bug is
introduced during the operation, you can take a share snapshot before
you deploy new application code

\- Protection against accidental deletions or unintended changes - After
the text file is closed while you're working on a text file in a file
share, you lose the ability to undo your changes. You can use share
snapshots to recover previous versions of the file if it's accidentally
renamed or deleted.

\- General backup purposes - Taking file share snapshot periodically
helps maintain previous versions of data that can be used for future
audit requirements or disaster recovery.

 

**Azure File Sync service**

 

\- Use to centralize your organization's file shares in Azure Files,
while keeping the flexibility, performance, and compatibility of an
on-premises file server

\- Azure File Sync transforms Windows Server into a quick cache of your
Azure file share which supports any protocol such as SMB, NFS, and FTPS

 

**Advantages of file sync**

 

\- Lift and shift - Providing write access to the same data across
Windows Servers and Azure Files, multiple offices can share files with
all offices

\- Branch Offices- Branch offices can backup files by setting up a new
server that will connect to Azure storage

\- Backup and Disaster Recovery - can restore file metadata immediately
and recall data once file sync is implemented

\- File Archiving- Only recently accessed data is located on local
servers. Non-used data moves to Azure in what is called Cloud Tiering.

 

**Cloud Tiering** - When a file is tiered, the Azure File Sync file
system replaces the file locally with a pointer, or reparse point. The
reparse point represents a URL to the file in Azure Files. When a user
opens a tiered file, Azure File Sync seamlessly recalls the file data
from Azure Files without the user needing to know that the file is
actually stored in Azure.

 

Cloud tiering transforms your server endpoint into a cache for your
files in the Azure file share, decreasing the amount of local storage
required while keeping the performance of an on-premises file server.

 

General Purpose v1 (GPv1) accounts don't support tiering

 

When cloud tiering enabled, cloud tiering will tier files to your Azure
file shares. This converts on-premises file shares into a cache, rather
than a complete copy of the dataset, to help you manage space efficiency
on your server. With cloud tiering, infrequently used or accessed files
can be tiered to Azure Files.

 

1\. Prepare Windows Server to use with Azure File Sync

2\. Deploy the Storage Sync Service

3\. Install the Azure File Sync agent

4\. Register Windows Server with Storage Sync Service

5\. Create a sync group and a cloud endpoint

6\. Create a server endpoint with registered server and specify path for
synchronization

7\. Configure firewall and virtual network settings, enable
cloud-tiering

 

<https://www.youtube.com/watch?v=vsSr8V2TjPA>

 

**File sync components**

 

***Storage Sync Service***

 

\- top-level Azure resource for Azure File Sync

\- peer of the storage account resource, and can similarly be deployed
to Azure resource groups

\- A Storage Sync Service can create sync groups that contain Azure file
shares across multiple storage accounts and multiple registered Windows
Servers

\- Before you can create a sync group in a Storage Sync Service, you
must first register a Windows Server with the Storage Sync Service

\- A subscription can have multiple Storage Sync Service resources

\- The storage account for the Azure file share must be located in the
same region as the Storage Sync Service

\- A Storage Sync Service can host as many sync groups

 

***Sync group***

 

\- sync topology for a set of files

\- A sync group must contain one cloud endpoint, which represents an
Azure file share and one or more server endpoints.

\- Endpoints within a sync group are kept in sync with each other. you
have two distinct sets of files that you want to manage with Azure File
Sync, you would create two sync groups and add different endpoints to
each sync group.

\- does not support more than one server endpoint from the same server
in the same Sync Group.

 

 

***Registered server***

 

\- represents a trust relationship between your server (or cluster) and
the Storage Sync Service

\- can register as many servers to a Storage Sync Service instances

\- An individual server or cluster can be registered with only one
Storage Sync Service at a time.

 

***Azure File Sync agent***

 

\- downloadable package that enables Windows Server to be synced with an
Azure file share

\- The Azure File Sync agent has three main components:

 

FileSyncSvc.exe: The background Windows service that is responsible for
monitoring changes on server endpoints, and for initiating sync sessions
to Azure

 

StorageSync.sys: The Azure File Sync file system filter, which is
responsible for tiering files to Azure Files

 

PowerShell management cmdlets: PowerShell cmdlets that you use to
interact with the Microsoft.StorageSync Azure resource provider

 

***Server endpoint***

 

\- The path on the Windows Server that is being synced to an Azure file
share, such as a folder on a server volume e. g C:\Folder1. Network
Attached Storage(NAS) is not supported.

\- Multiple server endpoints can exist on the same volume if their
namespaces are not overlapping (for example, F:\sync1 and F:\sync2) and
each endpoint is syncing to a unique sync group

\- The server endpoint object contains the settings that configure the
cloud tiering capability, which provides the caching capability of Azure
File Sync

\- With the on-premises servers the file(server endpoint) is scanned and
synced automatically after it's being added.

\- Changing the path or drive letter after you established a server
endpoint on a volume is not supported

\- A registered server can support multiple server endpoints, however, a
sync group can only have one server endpoint per registered server at
any given time. Other server endpoints within the sync group must be on
different registered servers.

 

***Cloud endpoint***

 

\- an Azure file share that is part of a sync group

\- entire Azure file share syncs, and an Azure file share can be a
member of only one cloud endpoint

\- Therefore, an Azure file share can be a member of only one sync
group. If you add an Azure file share into sync group, file share is
merged with existing set of files.

\- If you make a change to the cloud endpoint (Azure file share)
directly, changes first need to be discovered by an Azure File Sync
change detection job. A change detection job is initiated for a cloud
endpoint only once every 24 hours

 

 

***Deploy Azure File Sync***

 

 

1\. Deploy the Storage Sync Service- You will need to provide Name,
Subscription, Resource Group, and Location from the Azure portal

2\. Prepare Windows Server to use with Azure File Sync- configure the
server including temporarily disabling Internet Explorer Enhanced
Security and ensuring you have latest PowerShell version as preparation
steps

3\. Install the Azure File Sync Agent- downloadable package that enables
Windows Server to be synced with an Azure file share where you enable
Microsoft Update to keep Azure File Sync up to date.

4\. Register Windows Server with Storage Sync Service - When the Azure
File Sync agent installation is finished, Windows Server(or cluster)
establishes a trust relationship with the Storage Sync Service.
Registration requires your Subscription ID, Resource Group, and Storage
Sync Service.

 

Azure File Sync uses a simple conflict-resolution strategy: we keep both
changes to files that are changed in two endpoints at the same time. The
most recently written change keeps the original file name. The older
file (determined by LastWriteTime) has the endpoint name and the
conflict number appended to the filename. For server endpoints, the
endpoint name is the name of the server. For cloud endpoints, the
endpoint name is Cloud. The name follows this taxonomy:

 

\<FileNameWithoutExtension\>-\<endpointName\>\[-#\].\<ext\>

 

For example, the first conflict of CompanyReport.docx would become
CompanyReport-CentralServer.docx if CentralServer is where the older
write occurred. The second conflict would be named
CompanyReport-CentralServer-1.docx. Azure File Sync supports 100
conflict files per file. Once the maximum number of conflict files has
been reached, the file will fail to sync until the number of conflict
files is less than 100.

 

net use command is used to connect to file shares using SAS.

 

 

 

 

Azure Blob Storage

 

Azure Blob storage is a service for storing large amounts of
unstructured object data in the cloud. Blob storage can store any type
of text or binary data, such as a document, media file, or application
installer. Common uses of Blob storage include:

\- Serving images or documents directly to a browser.

\- Storing files for distributed access, such as installation.

\- Streaming video and audio.

\- Storing data for backup and restore, disaster recovery, and
archiving.

\- Storing data for analysis by an on-premises or Azure-hosted service.

\- Blob cannot be backup to service vault

 

Blob Storage uses for

 

\- access tiers to reduce cost and improve performance

\- lifecycle management plan for the older data

\- object replication for failover

 

Blob service resources

 

\- The storage account

\- Containers in the storage account

\- Blobs in a container

 

Blob containers

 

\- A container provides a grouping of a set of blobs which must be in
container

\- An account can contain an unlimited number of containers

\- A container can store an unlimited number of blobs.

\- Name of blob container may only contain lowercase letters, numbers,
and hyphens, and must begin with a letter or a number

\- name must also be between 3 and 63 characters long.

 

Public access level specifies whether data in the container may be
accessed publicly, by default container data is private to account owner

 

\- Private - no anonymous access

\- Blob - anonymous public read access for blobs only

\- Container- anonymous public read access for blobs and containers

 

New-AzStorageContainer ; create the Blob container with PowerShell

 

Blob access Tiers

 

Azure Storage provides different options for accessing block blob data
based on usage patterns. By selecting the correct access tier for your
needs, you can store your block blob data in the most cost-effective
manner.

 

 

\- Hot - for frequent access of objects in the storage account. New
storage accounts are created in the Hot tier by default

\- Cool- for storing large amounts of data that is infrequently accessed
and stored for at least 30 days.

\- Archive - for data that can tolerate several hours of retrieval
latency and will remain in the Archive tier for at least 180 days. While
a blob is in the Archive tier, it can't be read or modified. To read or
download a blob in the Archive tier, you must first rehydrate it to an
online tier, either Hot or Cool. Data in the Archive tier can take up to
15 hours to rehydrate, depending on the priority you specify for the
rehydration operation.

 

Storage cost : Hot \> Cool\> Archive

 

Cost based on demand of accessing data : Archive \> Cool \> Hot

 

Blob lifecycle management

 

Some data expires days or months after creation, while other data sets
are actively read and modified throughout their lifetimes.

 

Azure Blob storage lifecycle management offers a rich, rule-based policy
for GPv2 and Blob storage accounts. Use the policy to transition your
data to the appropriate access tiers or expire at the end of the data's
lifecycle. The lifecycle management policy lets you:

 

\- Transition blobs to a cooler storage tier (hot to cool, hot to
archive, or cool to archive)

\- Delete blobs at the end of their lifecycles

\- Define rules to be run once per day at the storage account level.

\- Apply rules to containers or a subset of blobs.

 

Blob object replication

 

Object replication asynchronously copies block blobs in a container
according to rules that you configure. Followings copies from the source
container to the destination container.

 

\- contents of the blob

\- any versions associated with the blob

\- blob's metadata and properties

 

With blob object replication,

 

1\. Minimizing latency - to consume data from a region that is in closer
physical proximity

2\. Increase efficiency for compute workloads- compute workloads can
process the same sets of block blobs in different regions

3\. Optimizing data distribution- can process or analyze data in a
single location

4\. Optimizing costs- can reduce costs by moving it to the archive tier

 

Consideration in object replication

 

\- Requires that blob versioning is enabled on both the source and
destination accounts.

\- Any snapshots on a blob in the source account are not replicated to
the destination account

\- Supports when the source and destination accounts are in the hot or
cool tier where source and destination accounts may be in different
tiers

\- Create a replication policy that specifies the source storage account
and the destination account. A replication policy includes one or more
rules that specify a source container and a destination container and
indicate which block blobs in the source container will be replicated.

 

Azure Storage offers three types of blobs.

 

Block blobs (default) - consist of blocks of data assembled to make a
blob. Block blobs are ideal for storing text and binary data in the
cloud, like files, images, and videos.

 

Append blobs - like block blobs in that they are made up of blocks, they
are useful for logging scenarios.

 

Page blobs - can be up to 8 TB in size and are more efficient for
frequent read/write operations. Azure virtual machines use page blobs as
OS and data disks.

 

Blob upload tools

 

AzCopy easy-to-use command-line tool for Windows and Linux that copies
data to and from Blob storage, across containers, or across storage
accounts.

 

Azure Storage Data Movement library - .NET library for moving data
between Azure Storage services. The AzCopy utility is built with the
Data Movement library.

 

Azure Data Factory - copying data to and from Blob storage by using the
account key, shared access signature, service principal, or managed
identities for Azure resources authentications

 

Blobfuse - virtual file system driver for Azure Blob storage. You can
use blobfuse to access your existing block blob data in your Storage
account through the Linux file system.

 

Azure Data Box Disk - service for transferring on-premises data to Blob
storage when large datasets or network constraints make uploading data
over the wire unrealistic. You can use Azure Data Box Disk to request
solid-state disks (SSDs) from Microsoft, then copy your data to those
disks and ship them back to Microsoft to be uploaded into Blob storage.

 

Azure Import/Export- service provides a way to export large amounts of
data from your storage account to hard drives that you provide and that
Microsoft then ships back to you with your data.

 

Azure Import/Export service supports the following of storage accounts:

\- Standard General Purpose v2 storage accounts (recommended for most
scenarios)

\- Blob Storage accounts

\- General Purpose v1 storage accounts (both Classic or Azure Resource
Manager deployments)

 

Azure Import/Export service supports the following storage types:

\- Import supports Azure Blob storage and Azure File storage

\- Export supports Azure Blob storage. Azure Files not supported.

 

Azure Storage Explorer also can use as blob upload tool

 

 

Determine storage pricing

 

All storage accounts use a pricing model for blob storage based on the
tier of each blob. Following billing considerations apply to storage
account.

 

\- Performance tiers: As the performance tier gets cooler, the
per-gigabyte cost decreases.

\- Data access costs: Data access charges increase as the tier gets
cooler.

\- Transaction costs: The charge increases as the tier gets cooler.

\- Geo-Replication data transfer costs: This charge only applies to
accounts with geo-replication configured, including GRS and RA-GRS.
Geo-replication data transfer incurs a per-gigabyte charge.

\- Outbound data transfer costs: data that is transferred out of an
Azure region incur billing for bandwidth usage on a per-gigabyte basis.

\- Changing the storage tier: Changing the account storage tier from
cool to hot incurs a charge equal to reading all the data existing in
the storage account.

 

Secure Storage

 

Storage security strategies

 

Encryption - All data written to Azure Storage is automatically
encrypted using Storage Service Encryption (SSE) and it keeps at rest in
encrypted way.

 

SSE automatically encrypts your data before persisting it to
Azure-managed Disks, Azure Blob, Queue, Table storage, or Azure Files,
and decrypts the data before retrieval. All data written to the Azure
storage platform is encrypted through 256-bit AES encryption.

 

Two type of encryption type

\- Microsoft managed keys - a native form

\- Customer managed keys - Azure Key Vault can manage your encryption
keys. You can create your own encryption keys and store them in a key
vault, or you can use Azure Key Vault's APIs to generate encryption
keys. You can create, disable, audit, rotate, and define access
controls. Further Azure Key Vault provides to store secrets such as
storage account keys, digital certificates, user credentials, REST API
to rotate or retrieve secrets of source code.

 

SSE is enabled for all new and existing storage accounts and cannot be
disabled.

 

The storage account and the key vault must be in the same region, but
they can be in different subscriptions.

 

Authentication

 

\- RBAC role- scope to the storage account to security principals

\- Azure AD - to authorize resource management operations such as key
management. Azure AD integration is supported for data operations on the
Blob and Queue services.

 

Data in transit -Data can be secured in transit between an application
and Azure by using Client-Side Encryption, HTTPS, or SMB 3.0.

 

Disk encryption - OS and data disks in Azure VM can be encrypted using
Azure Disk Encryption(ADE)

 

Shared Access Signatures(SAS) - Delegated access to the data objects in
Azure Storage can be granted using Shared Access Signatures.

 

Authorization options

 

Blob storage: Public access, Azure AD, Shared key, SAS

File storage: SAS only

 

Public access

 

\- grants anyone read access to files stored in blob storage via URL to
file.

\- When you grant access for blobs only, they're individually accessible
but you can't browse other blobs in the container

\- you don't need to share keys with clients or manage a SAS

\- Anonymous access is controlled at the container level, not individual
blobs. If you want to secure some files and not others, you need to
segregate them into different blob containers.

 

Azure Active Directory (Azure AD)

 

\- assign fine-grained access to users, groups, or applications via RBAC

\- to securely access Azure Storage without storing any credentials in
your code.

\- supports Azure Blobs, Azure Queues, Azure Tables, Azure Files(SMB)-
Supported, only with AAD Domain Services

\- Authorization takes a two-step approach.

1\. you authenticate a security principal that returns an OAuth 2.0
token if successful.

2\. This token is then passed to Azure Storage to enable authorization
to the requested resource.

 

 

Shared Key

 

\- Azure Storage creates two 512-bit access keys for every storage
account that's created

\- A client using Shared Key passes a header with every request that is
signed using the storage account access key

\- relies on your account access keys and other parameters to produce an
encrypted signature string

\- supports Azure Blobs, Azure Queues, Azure Tables, Azure Files(SMB),
Azure Files(REST)

\- It recommends that you manage your storage keys with Azure Key Vault.
It's then easy to rotate keys on a regular schedule to keep your storage
account secure.

 

Shared access signatures (SAS)

 

\- delegate access to a particular resource in your account with
specified permissions and over a specified time interval

\- control includes the level of access like read only or read and write

\- supports Azure Blobs, Azure Queues, Azure Tables, Azure Files(SMB),
Azure Files(REST)

 

There are three types of shared access signatures:

\- User delegation SAS: Secured with Azure AD credentials and can be
used only on Azure Blob storage.

\- Service SAS: Secured with a storage account key. A service SAS is
used on only one service at a time, like Blob storage, Azure Queue
storage, Azure Table storage, or Azure Files.

\- Account SAS: Secured with a storage account key.

 

Generate Share Access Signature(SAS) tokens

 

A shared access signature (SAS) is a URI that grants restricted access
rights to Azure Storage resources. With SAS URI, you grant them access
to a resource in secure way for a specified period of time.

 

A SAS gives you granular control over the type of access.

 

\- An account-level SAS can delegate access to multiple storage
services. For example, blob, file, queue, and table.

\- A service-level SAS delegates access to a resource in just one of the
storage services

\- An interval over SAS is valid, including the start time to expiry
time

\- Permission granted by SAS, read and write but not delete

\- IP address or range of IP addresses from which Azure Storage will
accept the SAS, default network rule. To allow all connections from all
networks.

\- The protocol over which Azure Storage will accept the SAS, HTTP or
HTTPS

 

URI and SAS parameters

 

The URI consists of your Storage Resource URI and the SAS token.

 

<https://myaccount.blob.core.windows.net/?restype=service&amp;comp=properties&amp;sv=2015-04-05&amp;ss=bf&amp;srt=s&amp;st=2015-04-29T22%3A18%3A26Z&amp;se=2015-04-30T02%3A23%3A26Z&amp;sr=b&amp;sp=rw&amp;sip=168.1.5.60-168.1.5.70&amp;spr=https>
&amp;sig=F%6GRVAZ5Cdj2Pw4txxxxx

 

Resource URI ;
<https://myaccount.blob.core.windows.net/?restype=service&comp=properties>

 

Storage services version; indicates the version to use

sv=2015-04-05

 

Services; SAS applies to the Blob and File services

ss=bf

 

Resource types; SAS applies to service-level operations

srt=s

 

Start time; Specified in UTC time. If you want the SAS to be valid
immediately, omit the start time.

st=2015-04-29T22%3A18%3A26Z

 

Expiry time; se=2015-04-30T02%3A23%3A26Z

 

Resource; sr=b

 

Permissions; sp=rw

 

IP Range; sip=168.1.5.60-168.1.5.70

 

Protocol; spr=https

 

Signature; Used to authenticate access to the blob. The signature is an
HMAC computed over a string-to-sign and key using the SHA256 algorithm,
and then encoded using Base64 encoding.

 

sig=F%6GRVAZ5Cdj2Pw4tgU7IlSTkWgn7bUkkAg8P6HESXwmf%4B

 

Potential Risks of SAS

 

\- If a SAS is compromised, it can be used by anyone who obtains it.

\- If a SAS provided to a client application expires and the application
is unable to retrieve a new SAS from your service, then the
application's functionality may be hindered.

 

Risks mitigation

 

\- Always use HTTPS to create or distribute a SAS- If a SAS is passed
over HTTP, man-in-the-middle attacks can compromise sensitive data

\- Reference stored access policies where possible - stored access
policies allows revoke permissions to regenerate the storage account
keys

\- Use near-term expiration times on an unplanned SAS - Even if a SAS is
compromised, it's valid only for a short time and limit the amount of
data that can be uploaded to a blob

\- Have clients automatically renew the SAS if necessary - Clients
should renew the SAS well before the expiration date

\- Be specific with the resource to be accessed- to provide a user with
the minimum required privileges

\- Account will be billed for any usage, including that done with SAS-
If you provide write access to a blob, a user may choose to upload. If
you've given them read access as well, they may choose to download.

\- Validate data written using SAS - application requires that data be
validated or authorized before it is ready to use which helps to protect
against corrupt or malicious data being written to your account

\- Don't assume SAS is always the correct choice - if you want to make
all blobs in a container publicly readable, you can make the container
Public, rather than providing a SAS to every client for access

\- Use Storage Analytics to monitor your application- use logging and
metrics to observe any spike in authentication failures due to an outage
in your SAS provide

 

Stored access policy

 

You can create a stored access policy on four kinds of storage resources
such as blob containers, file shares, queues, tables. It affects all
blobs contain in containers.

 

The stored access policy is created with the following properties:

\- Identifier: The name you use to reference the stored access policy.

\- Start time: A DateTimeOffset value for the date and time when the
policy might start to be used. This value can be null.

\- Expiry time: A DateTimeOffset value for the date and time when the
policy expires. After this time, requests to the storage will fail with
a 403 error-code message.

\- Permissions: The list of permissions as a string that can be one or
all of acdlrw.

 

You can create stored access policy using C# .NET code, Azure portal and
Azure CLI.

 

Manage access keys

 

Azure AD authentication for storage account

 

Access to Azure Files

 

 

 
