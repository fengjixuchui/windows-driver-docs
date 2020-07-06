---
title: WDI_TLV_SAE_COMMIT_RESPONSE
description: WDI_TLV_SAE_COMMIT_RESPONSE is a TLV that contains the Simultaneous Authentication of Equals (SAE) Commit response frame.
ms.assetid: 3E243737-F1C8-4554-96D2-E05C77DBA8B6
ms.date: 02/15/2019
keywords:
 - WDI_TLV_SAE_COMMIT_RESPONSE Network Drivers Starting with Windows Vista
ms.localizationpriority: medium
ms.custom: 19H1
---

# WDI_TLV_SAE_COMMIT_RESPONSE

**WDI_TLV_SAE_COMMIT_RESPONSE** is a TLV that contains the Simultaneous Authentication of Equals (SAE) Commit response frame.

This TLV is used in the payload data of [NDIS_STATUS_WDI_INDICATION_SAE_AUTH_PARAMS_NEEDED](ndis-status-wdi-indication-sae-auth-params-needed.md).

## TLV Type

0x14D

## Length

The size (in bytes) of the array of UINT8 elements. The array must contain 1 or more elements.

## Values

| Type | Description |
| --- | --- |
| UINT8[] | The SAE Commit response frame. |

## Requirements

**Minimum supported client**: Windows 10, version 1903
**Minimum supported server**: Windows Server 2016
**Header**: Wditypes.hpp
