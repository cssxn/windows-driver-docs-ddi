---
UID: NC:d3dkmthk.PFND3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME
title: PFND3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME (d3dkmthk.h)
description: The D3DKMTQueryRemoteVidPnSourceFromGdiDisplayName function maps a GDI display name to a remote video present network (VidPN) source ID.
old-location: display\d3dkmtqueryremotevidpnsourcefromgdidisplayname.htm
ms.date: 05/10/2018
keywords: ["PFND3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME callback function"]
ms.keywords: D3DKMTQueryRemoteVidPnSourceFromGdiDisplayName, D3DKMTQueryRemoteVidPnSourceFromGdiDisplayName callback function [Display Devices], PFND3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME, PFND3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME callback, d3dkmthk/D3DKMTQueryRemoteVidPnSourceFromGdiDisplayName, display.d3dkmtqueryremotevidpnsourcefromgdidisplayname
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
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
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME
 - d3dkmthk/PFND3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3dkmthk.h
api_name:
 - PFND3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME
---

# PFND3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME callback function


## -description

Maps a GDI display name to a remote video present network (VidPN) source ID that is needed for a call to the <a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtoutputduplpresent">D3DKMTOutputDuplPresent</a> function.

## -parameters

### -param unnamedParam1

*pData* 

[in, out] A pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_queryremotevidpnsourcefromgdidisplayname">D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME</a> structure that describes information that is required to perform the mapping.

## -returns

Returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The mapping was performed successfully.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|


This function might also return other NTSTATUS values.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtoutputduplpresent">D3DKMTOutputDuplPresent</a>



<a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_queryremotevidpnsourcefromgdidisplayname">D3DKMT_QUERYREMOTEVIDPNSOURCEFROMGDIDISPLAYNAME</a>

