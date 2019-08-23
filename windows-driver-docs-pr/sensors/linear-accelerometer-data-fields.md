---
title: Linear accelerometer data fields
description: This topic provides information about the data fields that are specific to the linear accelerometer.
ms.assetid: FD869359-C1C2-4B2F-95F3-01234331DC54
ms.date: 07/20/2018
ms.localizationpriority: medium
---

#  Linear accelerometer data fields

This topic provides information about the data fields that are specific to the linear accelerometer.

The following table shows the data fields. For more information about the types shown in the type column, see [MSDN PROPVARIANT structure](https://go.microsoft.com/fwlink/p/?linkid=313395).

|Property key|Type|Required/Optional|Description|
|--|--|--|--|
|PKEY_SensorData_AccelerationX_Gs|VT_R4|Required|The x-axis acceleration in g’s.|
|PKEY_SensorData_AccelerationY_Gs|VT_R4|Required|The y-axis acceleration in g’s.|
|PKEY_SensorData_AccelerationZ_Gs|VT_R4|Required|The z-axis acceleration in g’s.|
|PKEY_SensorData_Shake|VT_BOOL|Optional|An indication that a shake has been detected by the linear accelerometer. This must be true if the data field is sent up.|

 

## Related topics


[MSDN PROPVARIANT structure](https://go.microsoft.com/fwlink/p/?linkid=313395)





