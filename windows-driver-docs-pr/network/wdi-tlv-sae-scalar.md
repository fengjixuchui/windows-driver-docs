---
title: WDI_TLV_SAE_SCALAR
description: WDI_TLV_SAE_SCALAR is a TLV that contains the Finite Field Element (FFE) for a Simultaneous Authentication of Equals (SAE) Commit request.
ms.assetid: 23B8B2DB-D451-4E8D-B8A3-D66A81DF599C
ms.date: 02/15/2019
keywords:
 - WDI_TLV_SAE_SCALAR Network Drivers Starting with Windows Vista
ms.localizationpriority: medium
ms.custom: 19H1
---

# WDI_TLV_SAE_SCALAR

**WDI_TLV_SAE_SCALAR** is a TLV that contains the Finite Field Element (FFE) for a Simultaneous Authentication of Equals (SAE) Commit request.

This TLV is used in [WDI_TLV_SAE_COMMIT_REQUEST](wdi-tlv-sae-commit-request.md).

## TLV Type

0x153

## Length

The size (in bytes) of the array of UINT8 elements. The array must contain 1 or more elements.

## Values

| Type | Description |
| --- | --- |
| UINT8[] | The FFE. |

## Requirements

**Minimum supported client**: Windows 10, version 1903
**Minimum supported server**: Windows Server 2016
**Header**: Wditypes.hpp
