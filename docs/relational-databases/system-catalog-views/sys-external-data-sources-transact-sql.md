---
title: "sys.external_data_sources (Transact-SQL)"
description: sys.external_data_sources (Transact-SQL)
author: rwestMSFT
ms.author: randolphwest
ms.date: "09/02/2021"
ms.prod: sql
ms.prod_service: "database-engine, sql-database, synapse-analytics, pdw"
ms.technology: system-objects
ms.topic: "reference"
dev_langs:
  - "TSQL"
monikerRange: ">=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||>=sql-server-linux-2017||=azuresqldb-mi-current"
---
# sys.external_data_sources (Transact-SQL)

[!INCLUDE [sqlserver2016-asdb-asdbmi-asa-pdw](../../includes/applies-to-version/sqlserver2016-asdb-asdbmi-asa-pdw.md)]

  Contains a row for each external data source in the current database for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssSDS](../../includes/sssds-md.md)], and [!INCLUDE[ssSDW](../../includes/sssdw-md.md)].  
  
 Contains a row for each external data source on the server for [!INCLUDE[ssPDW](../../includes/sspdw-md.md)].  
  
|Column Name|Data Type|Description|Range|  
|-----------------|---------------|-----------------|-----------|  
|data_source_id|**int**|Object ID for the external data source.||  
|name|**sysname**|Name of the external data source.||  
|location|**nvarchar(4000)**|The connection string, which includes the protocol, IP address, and port for the external data source.||  
|type_desc|**nvarchar(255)**|Data source type displayed as a string.|HADOOP, RDBMS, SHARD_MAP_MANAGER, REMOTE_DATA_ARCHIVE, BLOB_STORAGE, NONE|  
|type|**tinyint**|Data source type displayed as a number.|0 - HADOOP<br /><br /> 1 - RDBMS<br /><br /> 2 - SHARD_MAP_MANAGER<br /><br /> 3 - REMOTE_DATA_ARCHIVE<br /><br /> 4 - *internal use only*<br /><br /> 5 - BLOB_STORAGE<br /><br /> 6 - NONE |  
|resource_manager_location|**nvarchar(4000)**|For type HADOOP, the IP and port location of the Hadoop resource manager. The `resource_manager_location` is used for submitting a job on a Hadoop data source.<br /><br /> `NULL` for other types of external data sources.||  
|credential_id|**int**|The object ID of the database scoped credential used to connect to the external data source.||  
|database_name|**sysname**|For type RDBMS, the name of the remote database. For type, SHARD_MAP_MANAGER, the name of the shard map manager database. NULL for other types of external data sources.||  
|shard_map_name|**sysname**|For type SHARD_MAP_MANAGER, the name of the shard map. NULL for other types of external data sources.||  
  
## Permissions  
 The visibility of the metadata in catalog views is limited to securables that a user either owns or on which the user has been granted some permission. For more information, see [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## See Also  
  - [sys.external_file_formats &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-external-file-formats-transact-sql.md)   
  - [sys.external_tables &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-external-tables-transact-sql.md)   
  - [CREATE EXTERNAL DATA SOURCE &#40;Transact-SQL&#41;](../../t-sql/statements/create-external-data-source-transact-sql.md)  
  
  
