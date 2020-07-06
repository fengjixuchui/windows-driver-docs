---
title: KsIrqlDeviceCallbacks rule ()
description: The KsIrqlDeviceCallbacks rule specifies that a kernel-streaming (KS) miniport driver returns from a KS device callback function with the same IRQL it had when it was called.
ms.assetid: 8C73EE2F-AA5B-478B-925A-C7DC4F6EFF6A
ms.date: 05/21/2018
keywords: ["KsIrqlDeviceCallbacks rule ()"]
topic_type:
- apiref
api_name:
- KsIrqlDeviceCallbacks
api_type:
- NA
ms.localizationpriority: medium
---

# KsIrqlDeviceCallbacks rule ()


The KsIrqlDeviceCallbacks rule specifies that a kernel-streaming (KS) miniport driver returns from a KS device callback function with the same IRQL it had when it was called.

**Tips for debugging**

When Driver Verifier detects a violation of this rule, it triggers [**Bug Check 0xC4: DRIVER\_VERIFIER\_DETECTED\_VIOLATION**](https://docs.microsoft.com/windows-hardware/drivers/debugger/bug-check-0xc4--driver-verifier-detected-violation), with an *arg1* value of 0x00081006. The *arg3* (RuleState) and *arg4* (SubState) of the bug check provide pointers to additional information about the rule violation.

Use the [**!ruleinfo**](https://docs.microsoft.com/windows-hardware/drivers/debugger/-ruleinfo) debugger extension to find out what the IRQL values were at function entry and exit.

Use the command:

**!ruleinfo 0x81006** *RuleState* *SubState*.

In the rule state data, the *OldIrql* is the IRQL when the callback is entered. The *NewIrql* is the IRQL when the callback function is exited.

Don't use [**!irql**](https://docs.microsoft.com/windows-hardware/drivers/debugger/-irql) to determine the current IRQL because Driver Verifier might have raised IRQL before the bug check. Instead, use **!verifier 0x008** to view the IRQL logs.

**Driver model: KS**

**Bug check(s) found with this rule**: [**Bug Check 0xC4: DRIVER\_VERIFIER\_DETECTED\_VIOLATION**](https://docs.microsoft.com/windows-hardware/drivers/debugger/bug-check-0xc4--driver-verifier-detected-violation) (0x00081006)


How to test
-----------

<table>
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">At run time</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>To verify this rule, open a Command Prompt window. Enter a Driver Verifier command and specify <strong>/domain ks</strong>.</p>
<p>For example:</p>
<p><strong>verifier /domain ks</strong> [<em>options</em>] <strong>/driver</strong> <em>&lt;yourdriver&gt;</em></p>
<p>For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/driver-verifier" data-raw-source="[Driver Verifier](https://docs.microsoft.com/windows-hardware/drivers/devtest/driver-verifier)">Driver Verifier</a>.</p></td>
</tr>
</tbody>
</table>

 

 

 





