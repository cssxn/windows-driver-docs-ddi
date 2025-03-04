---
UID: NC:d3dumddi.PFND3DDDI_OFFERALLOCATIONSCB
title: PFND3DDDI_OFFERALLOCATIONSCB (d3dumddi.h)
description: The PFND3DDDI_OFFERALLOCATIONSCB callback function is called by the user-mode display driver to offer video memory allocations for reuse.
old-location: display\pfnofferallocationscb.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["PFND3DDDI_OFFERALLOCATIONSCB callback function"]
ms.keywords: PFND3DDDI_OFFERALLOCATIONSCB, d3dumddi/pfnOfferAllocationsCb, display.pfnofferallocationscb, pfnOfferAllocationsCb, pfnOfferAllocationsCb callback, pfnOfferAllocationsCb callback function [Display Devices]
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - PFND3DDDI_OFFERALLOCATIONSCB
 - d3dumddi/PFND3DDDI_OFFERALLOCATIONSCB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - PFND3DDDI_OFFERALLOCATIONSCB
product:
 - Windows
---

# PFND3DDDI_OFFERALLOCATIONSCB callback function


## -description

Called by the user-mode display driver   to offer  video memory allocations for reuse.

## -parameters

### -param hDevice

A handle to the display device (graphics context). The Direct3D runtime passed the user-mode driver this handle as the <b>hDevice</b> member of the <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createdevice">D3DDDIARG_CREATEDEVICE</a> structure at device creation.

### -param unnamedParam2

*pData* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_offerallocations">D3DDDICB_OFFERALLOCATIONS</a> structure  that defines the video memory allocations that the driver offers.

## -returns

Returns one of the following values.

| **Return code** | **Description** | 
|:--|:--|
| **S_OK** | The allocations were successfully offered.<br/>**Note:** If the driver does not need to call [pfnOfferAllocationsCb](), it should return S_OK. |
| **D3DDDIERR_DEVICEREMOVED** |The video memory manager or display miniport driver could not complete the operation because either a Plug and Play (PnP) Stop event or a Timeout Detection and Recovery (TDR) event occurred.<br/>**Note:** If this error code is returned, the driver's calling function (typically the [pfnOfferResources](./nc-d3dumddi-pfnd3dddi_offerresources.md)  routine) must return this error code to the Direct3D runtime. | 
| **E_INVALIDARG** | An invalid parameter was supplied. |

## -remarks

The user-mode display driver calls <b>pfnOfferAllocationsCb</b> to notify the Microsoft DirectX graphics kernel subsystem that, after it completes any previously submitted render operations,  it can offer the allocations' memory for other processes to use.

After the driver calls <b>pfnOfferAllocationsCb</b> to offer an allocation to reuse, it must call <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_reclaimallocationscb">pfnReclaimAllocationsCb</a>  before it locks the allocation or submits it for rendering operations.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createdevice">D3DDDIARG_CREATEDEVICE</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_offerallocations">D3DDDICB_OFFERALLOCATIONS</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicecallbacks">D3DDDI_DEVICECALLBACKS</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_offerresources">pfnOfferResources</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_reclaimallocationscb">pfnReclaimAllocationsCb</a>

