---
title: Reset to Factory Defaults (Function Index 21)
description: This function resets the NVDIMM-N back to the settings the vendor pre-configured.
ms.assetid: 64CEF5C8-FC2A-4C6E-829C-27E18A4EDC26
ms.localizationpriority: medium
ms.date: 10/17/2018
---

# Reset to Factory Defaults (Function Index 21)


This function resets the NVDIMM-N back to the settings the vendor pre-configured.

## <span id="Input"></span><span id="input"></span><span id="INPUT"></span>Input


### <span id="Args3"></span><span id="args3"></span><span id="ARGS3"></span>Args3

None.

## <span id="Output"></span><span id="output"></span><span id="OUTPUT"></span>Output


<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Field</th>
<th align="left">Byte Length</th>
<th align="left">Byte Offset</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong>Status</strong></td>
<td align="left">4</td>
<td align="left">0</td>
<td align="left"><p>This function can return the following Function-Specific Error Code:</p>
<p>1: The operation timed out.</p>
<p>Go to <a href="-dsm-interface-for-byte-addressable-energy-backed-function-class--function-interface-1-.md" data-raw-source="[_DSM Method Output](-dsm-interface-for-byte-addressable-energy-backed-function-class--function-interface-1-.md)">_DSM Method Output</a> for more information.</p></td>
</tr>
</tbody>
</table>

 

> [!NOTE]
> The platform shall wait three times the maximum save timeout for the factory default operation to finish (For example, if the maximum save timeout is 60 seconds, the platform shall wait 180 seconds). If the operation takes longer than that interval, the platform shall abort the operation and return with the function-specific error code 1(the operation timed out).

 

## <span id="related_topics"></span>Related topics


[\_DSM Interface for Byte Addressable Energy Backed Function Class (Function Interface 1)](-dsm-interface-for-byte-addressable-energy-backed-function-class--function-interface-1-.md)

 

 






