---
UID: NF:storport.ScsiPortWritePortBufferUchar
title: ScsiPortWritePortBufferUchar macro (storport.h)
description: Learn how the ScsiPortWritePortBufferUchar routine transfers a given number of unsigned bytes from a buffer to the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportwriteportbufferuchar.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["ScsiPortWritePortBufferUchar macro"]
ms.keywords: ScsiPortWritePortBufferUchar, ScsiPortWritePortBufferUchar routine [Storage Devices], scsiprt_19277863-04fb-4f72-85f5-9bc877bd83c1.xml, srb/ScsiPortWritePortBufferUchar, storage.scsiportwriteportbufferuchar
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
 - ScsiPortWritePortBufferUchar
 - storport/ScsiPortWritePortBufferUchar
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Scsiport.lib
 - Scsiport.dll
api_name:
 - ScsiPortWritePortBufferUchar
---

# ScsiPortWritePortBufferUchar macro


## -description

The <b>ScsiPortWritePortBufferUchar</b> routine transfers a given number of unsigned bytes from a buffer to the HBA.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters

### -param Port 

[in]
Pointer to the I/O port. The given <i>Port</i> must be in a mapped I/O-space range returned by <b>ScsiPortGetDeviceBase</b>.

### -param Buffer 

[in]
Pointer to a buffer.

### -param Count 

[in]
Specifies the number of bytes to be written to the HBA.

## -see-also

<a href="/windows-hardware/drivers/ddi/srb/nf-srb-scsiportgetdevicebase">ScsiPortGetDeviceBase</a>
