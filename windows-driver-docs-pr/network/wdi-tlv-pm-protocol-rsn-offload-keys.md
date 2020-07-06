---
title: WDI_TLV_PM_PROTOCOL_RSN_OFFLOAD_KEYS
description: WDI_TLV_PM_PROTOCOL_RSN_OFFLOAD_KEYS is a TLV that contains currently configured Rsn Eapol key information.
ms.assetid: DFF81CBD-1B10-456F-AD8D-1163DD80C981
ms.date: 04/02/2018
keywords:
 - WDI_TLV_PM_PROTOCOL_RSN_OFFLOAD_KEYS Network Drivers Starting with Windows Vista
ms.localizationpriority: medium
---

# WDI_TLV_PM_PROTOCOL_RSN_OFFLOAD_KEYS

WDI_TLV_PM_PROTOCOL_RSN_OFFLOAD_KEYS is a TLV that contains currently configured Rsn Eapol key information. This TLV is used in the [NDIS_STATUS_WDI_INDICATION_CIPHER_KEY_UPDATED](ndis-status-wdi-indication-cipher-key-updated.md) status indication.

## TLV Type

0x149

## Values

| Type | Description |
| --- | --- |
| WDI_RSN_OFFLOAD_KEYS_CONTAINER | The currently configured Rsn Eapol key information. |

## Requirements

**Minimum supported client**: Windows 10, version 1803

**Minimum supported server**: Windows Server 2016

**Header**: Wditypes.hpp

