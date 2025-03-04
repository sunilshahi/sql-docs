---
title: Release notes for SQL Server 2022 Preview on Linux
description: This article contains the release notes and supported features for SQL Server 2022 Preview running on Linux. Release notes are included for the most recent release and several previous releases.
author: rwestMSFT
ms.author: randolphwest
ms.date: 07/25/2022
ms.topic: conceptual
ms.prod: sql
ms.technology: linux
ms.reviewer: amitkh, vanto
---
# Release notes for [!INCLUDE[sssql22](../includes/sssql22-md.md)] on Linux

[!INCLUDE[tsql-appliesto-ssver16-xxxx-xxxx-xxx-linuxonly.md](../includes/tsql-appliesto-ssver16-xxxx-xxxx-xxx-linuxonly.md)]

The following release notes apply to the public community technology preview (CTP) of [!INCLUDE[sssql22](../includes/sssql22-md.md)] running on Linux.

> [!TIP]  
> To learn about new Linux features in [!INCLUDE[sssql22](../includes/sssql22-md.md)], see [What's new in SQL Server 2022 Preview](../sql-server/what-s-new-in-sql-server-2022.md).

## Supported platforms

| Platform | File System | Installation Guide | Get |
| --- | --- | --- | --- |
| Red Hat Enterprise Linux 8.0 - 8.5 Server | XFS or EXT4 | [Installation guide](../linux/quickstart-install-connect-red-hat.md) | [Get RHEL 8.0](https://access.redhat.com/products/red-hat-enterprise-linux/evaluation) |
| Ubuntu 20.04 LTS | XFS or EXT4 | [Installation guide](../linux/quickstart-install-connect-ubuntu.md) | [Get Ubuntu 20.04](https://releases.ubuntu.com/20.04/) |
| Docker Engine 1.8+ on Linux | N/A | [Installation guide](../linux/quickstart-install-connect-docker.md) | [Get Docker](https://www.docker.com/get-started) |

SUSE Linux Enterprise Server (SLES) **is not supported** for CTP 2.1, and will follow in a later release.

> [!TIP]  
> For more information, review the [system requirements](../linux/sql-server-linux-setup.md#system) for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on Linux. For the latest support policy for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see the [Technical support policy for Microsoft SQL Server](/troubleshoot/sql/general/support-policy-sql-server).

## Tools

Most existing client tools that target SQL Server can seamlessly target SQL Server running on Linux. Some tools might have a specific version requirement to work well with Linux. For a full list of SQL Server tools, see [SQL Tools and Utilities for SQL Server](../tools/overview-sql-tools.md).

## How to install updates

If you've configured the preview repository (`mssql-server-preview`), then you'll get the latest public CTP of SQL Server packages when you perform new installations. If you require Docker container images, see official images for [Microsoft SQL Server on Linux for Docker Engine](https://hub.docker.com/r/microsoft/mssql-server/).

If you're updating existing SQL Server packages, run the appropriate update command for each package to get the latest public CTP. For specific update instructions for each package, see the following installation guides:

- [Install SQL Server package](sql-server-linux-setup.md#upgrade)
- [Install Full-Text Search package](sql-server-linux-setup-full-text-search.md)
- [Install SQL Server Integration Services](sql-server-linux-setup-ssis.md)
- [Install SQL Server Machine Learning Services R and Python support on Linux](sql-server-linux-setup-machine-learning.md)
- [Install PolyBase package](../relational-databases/polybase/polybase-linux-setup.md)
- [Enable SQL Server Agent](sql-server-linux-setup-sql-agent.md)

## <a id="ctp21"></a> CTP 2.1 (July 2022)

SQL Server 2022 CTP 2.1 (16.0.700.4) Linux packages and containers, as well as Azure Images, will be available soon at their current release locations.

## <a id="ctp20"></a> CTP 2.0 (May 2022)

The following section provides package locations and known issues for the first public community technology preview (CTP). To learn more about new features [!INCLUDE[sssql22](../includes/sssql22-md.md)] running on Linux, see the [What's new in SQL Server 2022 Preview](../sql-server/what-s-new-in-sql-server-2022.md).

### Package details

For manual or offline package installations, you can download the RPM and Debian packages for the latest supported distributions, with the information in the following table.

> [!IMPORTANT]  
> SUSE Linux Enterprise Server (SLES) **is not supported** for [!INCLUDE[sssql22](../includes/sssql22-md.md)] on Linux CTP 2.0.

| Package | Package version | Downloads |
|-----|-----|-----|
| **RHEL 8.x RPM packages** | 16.0.600.9-2 | [Database Engine RPM package](https://packages.microsoft.com/rhel/8/mssql-server-preview/mssql-server-16.0.600.9-2.x86_64.rpm)</br>[High Availability RPM package](https://packages.microsoft.com/rhel/8/mssql-server-preview/mssql-server-ha-16.0.600.9-2.x86_64.rpm)</br>[Full-Text Search RPM package](https://packages.microsoft.com/rhel/8/mssql-server-preview/mssql-server-fts-16.0.600.9-2.x86_64.rpm)</br>[Extensibility RPM package](https://packages.microsoft.com/rhel/8/mssql-server-preview/mssql-server-extensibility-16.0.600.9-2.x86_64.rpm)</br>[Java Extensibility RPM package](https://packages.microsoft.com/rhel/8/mssql-server-preview/mssql-server-extensibility-java-16.0.600.9-2.x86_64.rpm)</br>[PolyBase RPM package](https://packages.microsoft.com/rhel/8/mssql-server-preview/mssql-server-polybase-16.0.600.9-2.x86_64.rpm)|
| **Ubuntu 20.04 Debian packages** | 16.0.600.9-2 | [Database Engine Debian package](https://packages.microsoft.com/ubuntu/20.04/mssql-server-preview/pool/main/m/mssql-server/mssql-server_16.0.600.9-2_amd64.deb)</br>[High Availability Debian package](https://packages.microsoft.com/ubuntu/20.04/mssql-server-preview/pool/main/m/mssql-server-ha/mssql-server-ha_16.0.600.9-2_amd64.deb)</br>[Full-Text Search Debian package](https://packages.microsoft.com/ubuntu/20.04/mssql-server-preview/pool/main/m/mssql-server-fts/mssql-server-fts_16.0.600.9-2_amd64.deb)</br>[Extensibility Debian package](https://packages.microsoft.com/ubuntu/20.04/mssql-server-preview/pool/main/m/mssql-server-extensibility/mssql-server-extensibility_16.0.600.9-2_amd64.deb)</br>[Java Extensibility Debian package](https://packages.microsoft.com/ubuntu/20.04/mssql-server-preview/pool/main/m/mssql-server-extensibility-java/mssql-server-extensibility-java_16.0.600.9-2_amd64.deb)</br>[PolyBase Debian Package](https://packages.microsoft.com/ubuntu/20.04/mssql-server-preview/pool/main/m/mssql-server-polybase/mssql-server-polybase_16.0.600.9-2_amd64.deb)|

## Known issues

The following sections describe known issues with the CTP 2.1 release of [!INCLUDE[sssql22](../includes/sssql22-md.md)] on Linux.

### General

- The length of the hostname where [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] is installed needs to be 15 characters or less.

  - **Resolution**: Change the name in `/etc/hostname` to something 15 characters long or less.

- Manually setting the system time backwards in time will cause [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to stop updating the internal system time within [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].

  - **Resolution**: Restart [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].

- Only single instance installations are supported.

  - **Resolution**: If you want to have more than one instance on a given host, consider using VMs or Docker containers.

- [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager can't connect to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on Linux.

- The default language of the **sa** login is English.

  - **Resolution**: Change the language of the **sa** login with the `ALTER LOGIN` statement.

- OLEDB provider logs the following warning: `Failed to verify the Authenticode signature of 'C:\binn\msoledbsql.dll'. Signature verification of SQL Server DLLs will be skipped. Genuine copies of SQL Server are signed. Failure to verify the Authenticode signature might indicate that this is not an authentic release of SQL Server. Install a genuine copy of SQL Server or contact customer support.`

  - **Resolution**: No action is required. The OLEDB provider is signed using SHA256. SQL Server Database engine doesn't validate the signed .dll correctly.

### Databases

- The `master` database can't be moved with the **mssql-conf** utility. Other system databases can be moved with **mssql-conf**.

- When restoring a database that was backed up on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on Windows, you must use the `WITH MOVE` clause in the Transact-SQL statement.

- Certain algorithms (cipher suites) for Transport Layer Security (TLS) don't work properly with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on Linux. This results in connection failures when attempting to connect to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], and problems establishing connections between replicas in high availability groups.

  - **Resolution**: Modify the `mssql.conf` configuration script for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on Linux to disable problematic cipher suites, by doing the following:

   1. Add the following to `/var/opt/mssql/mssql.conf`.

      ```ini
      [network]
      tlsciphers=AES256-GCM-SHA384:AES128-GCM-SHA256:AES256-SHA256:AES128-SHA256:AES256-SHA:AES128-SHA:!ECDHE-RSA-AES128-GCM-SHA256:!ECDHE-RSA-AES256-GCM-SHA384:!ECDHE-ECDSA-AES256-GCM-SHA384:!ECDHE-ECDSA-AES128-GCM-SHA256:!ECDHE-ECDSA-AES256-SHA384:!ECDHE-ECDSA-AES128-SHA256:!ECDHE-ECDSA-AES256-SHA:!ECDHE-ECDSA-AES128-SHA:!ECDHE-RSA-AES256-SHA384:!ECDHE-RSA-AES128-SHA256:!ECDHE-RSA-AES256-SHA:!ECDHE-RSA-AES128-SHA:!DHE-RSA-AES256-GCM-SHA384:!DHE-RSA-AES128-GCM-SHA256:!DHE-RSA-AES256-SHA:!DHE-RSA-AES128-SHA:!DHE-DSS-AES256-SHA256:!DHE-DSS-AES128-SHA256:!DHE-DSS-AES256-SHA:!DHE-DSS-AES128-SHA:!DHE-DSS-DES-CBC3-SHA:!NULL-SHA256:!NULL-SHA
      ```

      > [!NOTE]  
      > In the preceding code, `!` negates the expression. This tells OpenSSL to not use the following cipher suite.

   1. Restart [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] with the following command.

      ```bash
      sudo systemctl restart mssql-server
      ```

- [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] databases on Windows that use In-memory OLTP can't be restored on [!INCLUDE[sssql22](../includes/sssql22-md.md)] on Linux. To restore a [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] database that uses in-memory OLTP, first upgrade the databases to [!INCLUDE[sssql16-md](../includes/sssql16-md.md)], [!INCLUDE[sssql17-md](../includes/sssql17-md.md)], [!INCLUDE[sssql19-md](../includes/sssql19-md.md)], or [!INCLUDE[sssql22-md](../includes/sssql22-md.md)] on Windows before moving them to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on Linux, via backup/restore or detach/attach.

- User permission `ADMINISTER BULK OPERATIONS` is not supported on Linux at this time.

### Networking

Features that involve outbound TCP connections from the `sqlservr` process, such as linked servers, PolyBase, or availability groups, might not work if both the following conditions are met:

1. The target server is specified as a hostname and not an IP address.

1. The source instance has IPv6 disabled in the kernel. To verify if your system has IPv6 enabled in the kernel, all the following tests must pass:

   - `cat /proc/cmdline` will print the boot cmdline of the current kernel. The output must not contain `ipv6.disable=1`.
   - The `/proc/sys/net/ipv6/` directory must exist.
   - A C program that calls `socket(AF_INET6, SOCK_STREAM, IPPROTO_IP)` should succeed - the syscall must return an `fd != -1` and not fail with `EAFNOSUPPORT`.

The exact error depends on the feature. For linked servers, this manifests as a login timeout error. For availability groups, the `ALTER AVAILABILITY GROUP JOIN` DDL on the secondary will fail after 5 minutes with a `download configuration timeout` error.

To work around this issue, do one of the following:

1. Use IPs instead of host names to specify the target of the TCP connection.

1. Enable IPv6 in the kernel by removing `ipv6.disable=1` from the boot command line. The way to do this depends on the Linux distribution and the bootloader, such as **grub**. If you want IPv6 to be disabled, you can still disable it by setting `net.ipv6.conf.all.disable_ipv6 = 1` in the `sysctl` configuration (for example, `/etc/sysctl.conf`). This will still prevent the system's network adapter from getting an IPv6 address, but allow the `sqlservr` features to work.

#### Network File System (NFS)

If you use **Network File System (NFS)** remote shares in production, note the following support requirements:

- Use NFS version **4.2 or higher**. Older versions of NFS don't support required features, such as `fallocate` and sparse file creation, common to modern file systems.

- Locate only the `/var/opt/mssql` directories on the NFS mount. Other files, such as the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] system binaries, aren't supported.

- Ensure that NFS clients use the `nolock` option when mounting the remote share.

### Localization

- If your locale isn't English (`en_us`) during setup, you must use UTF-8 encoding in your bash session/terminal. If you use ASCII encoding, you might see an error similar to the following:

   ```output
   UnicodeEncodeError: 'ascii' codec can't encode character u'\xf1' in position 8: ordinal not in range(128)
   ```

   If you can't use UTF-8 encoding, run setup using the `MSSQL_LCID` environment variable to specify your language choice.

   ```bash
   sudo MSSQL_LCID=<LcidValue> /opt/mssql/bin/mssql-conf setup
   ```

- When running `mssql-conf setup`, and performing a non-English installation of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], incorrect extended characters are displayed after the localized text, "Configuring SQL Server...". Or, for non-Latin based installations, the sentence might be missing completely. The missing sentence should display the following localized string:

  `The licensing PID was successfully processed. The new edition is [<Name> edition]`.

  This string is output for information purposes only, and the next [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Cumulative Update will address this for all languages. This doesn't affect the successful installation of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] in any way.

#### Full-Text Search

Not all filters are available with this release, including filters for Microsoft Office documents. For a list of supported filters, see [Install SQL Server Full-Text Search on Linux](sql-server-linux-setup-full-text-search.md#filters).

#### SQL Server Integration Services (SSIS)

The **mssql-server-is** package isn't supported on SUSE in this release. It's currently supported on Ubuntu and on Red Hat Enterprise Linux (RHEL).

[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages can use ODBC connections on Linux. This functionality has been tested with the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] and the MySQL ODBC drivers, but is also expected to work with any Unicode ODBC driver that observes the ODBC specification. At design time, you can provide either a DSN or a connection string to connect to the ODBC data; you can also use Windows authentication. For more info, see the [blog post announcing ODBC support on Linux](https://blogs.msdn.microsoft.com/ssis/2017/06/16/odbc-is-supported-in-ssis-on-linux-ssis-helsinki-ctp2-1-refresh/).

The following features aren't supported in this release when you run SSIS packages on Linux:

- [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Catalog database
- Scheduled package execution by SQL Agent
- Windows Authentication
- Third-party components
- Change Data Capture (CDC)
- [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Scale Out
- Azure Feature Pack for SSIS
- Hadoop and HDFS support
- Microsoft Connector for SAP BW

For a list of built-in SSIS components that aren't currently supported, or that are supported with limitations, see [Limitations and known issues for SSIS on Linux](sql-server-linux-ssis-known-issues.md#components).

For more info about SSIS on Linux, see the following articles:

- [Blog post announcing SSIS support for Linux](https://blogs.msdn.microsoft.com/ssis/2017/05/17/ssis-helsinki-is-available-in-sql-server-vnext-ctp2-1/).
- [Install SQL Server Integration Services (SSIS) on Linux](sql-server-linux-setup-ssis.md)
- [Extract, transform, and load data on Linux with SSIS](sql-server-linux-migrate-ssis.md)

#### SQL Server Management Studio (SSMS)

The following limitations apply to [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] on Windows connected to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on Linux.

- Maintenance plans aren't supported.

- Management Data Warehouse (MDW) and the data collector in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] aren't supported.

- [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] UI components that have Windows Authentication or Windows event log options don't work with Linux. You can still use these features with other options, such as SQL logins.

- Number of log files to retain can't be modified.

## Next steps

To get started, see the following quickstarts:

- [Install on Red Hat Enterprise Linux](quickstart-install-connect-red-hat.md)
- [Install on Ubuntu](quickstart-install-connect-ubuntu.md)
- [Run on Docker](quickstart-install-connect-ubuntu.md)
- [Provision a SQL VM in Azure](/azure/azure-sql/virtual-machines/linux/sql-vm-create-portal-quickstart?toc=/sql/toc/toc.json)
- [Run SQL Server in the cloud](quickstart-install-connect-clouds.md)

For answers to frequently asked questions, see the [SQL Server on Linux FAQ](sql-server-linux-faq.yml).
