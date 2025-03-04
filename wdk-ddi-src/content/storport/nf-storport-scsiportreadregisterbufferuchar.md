---
UID: NF:storport.ScsiPortReadRegisterBufferUchar
title: ScsiPortReadRegisterBufferUchar macro (storport.h)
description: Learn how the ScsiPortReadRegisterBufferUchar routine transfers a specified number of unsigned bytes from the HBA to a buffer.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportreadregisterbufferuchar.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["ScsiPortReadRegisterBufferUchar macro"]
ms.keywords: ScsiPortReadRegisterBufferUchar, ScsiPortReadRegisterBufferUchar routine [Storage Devices], scsiprt_cfe4caf7-bfae-4d7a-aa70-8f44b52ca33c.xml, srb/ScsiPortReadRegisterBufferUchar, storage.scsiportreadregisterbufferuchar
req.header: storport.h
req.include-header: Miniport.h, Scsi.h, Storport.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Scsiport.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - ScsiPortReadRegisterBufferUchar
 - storport/ScsiPortReadRegisterBufferUchar
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Scsiport.lib
 - Scsiport.dll
api_name:
 - ScsiPortReadRegisterBufferUchar
---

# ScsiPortReadRegisterBufferUchar macro


## -description

The <b>ScsiPortReadRegisterBufferUchar</b> routine transfers a specified number of unsigned bytes from the HBA to a buffer.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters

### -param Register 

[in]
Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <b>ScsiPortGetDeviceBase</b>.

### -param Buffer 

[in]
Pointer to the buffer.

### -param Count 

[in]
Specifies the number of bytes to be read from the HBA.

## -remarks

<b>ScsiPortReadRegisterBufferUchar</b> ensures that the data is transferred correctly.

## -see-also

<a href="/windows-hardware/drivers/ddi/srb/nf-srb-scsiportgetdevicebase">ScsiPortGetDeviceBase</a>
