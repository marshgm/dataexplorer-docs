---
title: Storage connection strings - Azure Data Explorer
description: This article describes storage connection strings in Azure Data Explorer.
services: data-explorer
author: orspod
ms.author: orspodek
ms.reviewer: shanisolomon
ms.service: data-explorer
ms.topic: reference
ms.date: 01/20/2022
---
# Storage connection strings

Azure Data Explorer can interact with external storage services. For example, you can [create an Azure Storage external tables](../../management/external-tables-azurestorage-azuredatalake.md).

The following types of external storage are supported:

* Azure Blob Storage
* Azure Data Lake Storage Gen2
* Azure Data Lake Storage Gen1

Each type of a storage has corresponding connection string formats used to describe the storage resources and how to access them.
Azure Data Explorer uses a URI format to describe these storage resources and the properties necessary to access them, such as security credentials.

## Storage connection string templates

Each storage type has a different connection string format. See the following table for connection string templates for each storage type.

|Storage Type                  |Scheme    |URI template                          |
|------------------------------|----------|--------------------------------------|
|Azure Blob Storage            |`https://`|`https://`*StorageAccountName*`.blob.core.windows.net/`*Container*[`/`*BlobName*][*CallerCredentials*]|
|Azure Data Lake Storage Gen2  |`https://`|`https://`*StorageAccountName*`.dfs.core.windows.net/`*Filesystem*[`/`*PathToDirectoryOrFile*][*CallerCredentials*]|
|Azure Data Lake Storage Gen2  |`abfss://`|`abfss://`*Filesystem*`@`*StorageAccountName*`.dfs.core.windows.net/`[*PathToDirectoryOrFile*][*CallerCredentials*]|
|Azure Data Lake Storage Gen1  |`adl://`  |`adl://`*StorageAccountName*.azuredatalakestore.net/*PathToDirectoryOrFile*[*CallerCredentials*]|

## Storage authentication

For Azure Data Explorer to interact with and authenticate to external storage, you must specify the storage's `connection string`. This `connection string` defines the resource being accessed and its authentication information. For more information, see [storage authentication methods](/storage-authentication-methods.md).
