---
title: .alter-merge callout policy command- Azure Data Explorer
description: This article describes the .alter-merge callout policy command in Azure Data Explorer.
services: data-explorer
author: orspod
ms.author: orspodek
ms.reviewer: yonil
ms.service: data-explorer
ms.topic: reference
ms.date: 11/29/2021
---
# .alter-merge callout policy

Enables or disables a cluster's [callout policy](calloutpolicy.md). Azure Data Explorer clusters can communicate with external services in many different scenarios. Cluster admins can manage the authorized domains for external calls, by updating the cluster's callout policy.

## Syntax

`.alter-merge` `cluster` `policy` `callout` *SerializedArrayOfPolicyObjects*

## Arguments

*SerializedArrayOfPolicyObjects* - A serialized array with one or more JSON policy objects.

### Examples

```kusto
.alter-merge cluster policy callout @'[{"CalloutType": "sql","CalloutUriRegex": "sqlname\\.database\\.azure\\.com/?$","CanCall": true}]'
```
