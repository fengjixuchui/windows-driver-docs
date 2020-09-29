---
title: Allocator Properties
description: Allocator Properties
ms.assetid: 851bc3d8-46f6-46d0-87a8-81de2536492a
keywords:
- allocator properties WDK video capture
- PROPSETID_ALLOCATOR_CONTROL
ms.date: 04/20/2017
ms.localizationpriority: medium
---

# Allocator Properties


The [PROPSETID\_ALLOCATOR\_CONTROL](./propsetid-allocator-control.md) property set contains properties related to controlling the allocation and operations of video port surfaces. User-mode filters, such as the Overlay Mixer, use PROPSETID\_ALLOCATOR\_CONTROL. The following table describes properties that are part of the PROPSETID\_ALLOCATOR\_CONTROL property set.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>PROPSETID_ALLOCATOR_CONTROL KS properties</th>
<th>Property description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="/windows-hardware/drivers/stream/ksproperty-allocator-control-honor-count" data-raw-source="[&lt;strong&gt;KSPROPERTY_ALLOCATOR_CONTROL_HONOR_COUNT&lt;/strong&gt;](./ksproperty-allocator-control-honor-count.md)"><strong>KSPROPERTY_ALLOCATOR_CONTROL_HONOR_COUNT</strong></a></p></td>
<td><p>Controls how a filter determines the number of video port overlay surfaces to allocate.</p></td>
</tr>
<tr class="even">
<td><p><a href="/windows-hardware/drivers/stream/ksproperty-allocator-control-surface-size" data-raw-source="[&lt;strong&gt;KSPROPERTY_ALLOCATOR_CONTROL_SURFACE_SIZE&lt;/strong&gt;](./ksproperty-allocator-control-surface-size.md)"><strong>KSPROPERTY_ALLOCATOR_CONTROL_SURFACE_SIZE</strong></a></p></td>
<td><p>Controls the dimensions of the video port overlay surface.</p></td>
</tr>
<tr class="odd">
<td><p><a href="/windows-hardware/drivers/stream/ksproperty-allocator-control-capture-caps" data-raw-source="[&lt;strong&gt;KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS&lt;/strong&gt;](./ksproperty-allocator-control-capture-caps.md)"><strong>KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS</strong></a></p></td>
<td><p>Describes the capture capabilities of the video port.</p></td>
</tr>
<tr class="even">
<td><p><a href="/windows-hardware/drivers/stream/ksproperty-allocator-control-capture-interleave" data-raw-source="[&lt;strong&gt;KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE&lt;/strong&gt;](./ksproperty-allocator-control-capture-interleave.md)"><strong>KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_INTERLEAVE</strong></a></p></td>
<td><p>Returns if the video port supports interleaved capture.</p></td>
</tr>
</tbody>
</table>

 

