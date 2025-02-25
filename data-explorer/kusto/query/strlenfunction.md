---
title: strlen() - Azure Data Explorer | Microsoft Docs
description: This article describes strlen() in Azure Data Explorer.
services: data-explorer
author: orspod
ms.author: orspodek
ms.reviewer: alexans
ms.service: data-explorer
ms.topic: reference
ms.date: 02/13/2020
---
# strlen()

Returns the length, in characters, of the input string.

## Syntax

`strlen(`*source*`)`

## Arguments

* *source*: The source string that will be measured for string length.

## Returns

Returns the length, in characters, of the input string.

**Notes**

This function counts Unicode [code points](https://en.wikipedia.org/wiki/Code_point).

## Examples

```kusto
print length = strlen("hello")
```

|length|
|---|
|5|

```kusto
print length = strlen("⒦⒰⒮⒯⒪")
```

|length|
|---|
|5|

```kusto
print strlen('Çedilla') // the first character is a grapheme cluster
                        // that requires 2 code points to represent
```

|length|
|---|
|8|