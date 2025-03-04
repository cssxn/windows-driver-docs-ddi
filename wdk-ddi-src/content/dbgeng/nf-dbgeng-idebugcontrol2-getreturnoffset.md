---
UID: NF:dbgeng.IDebugControl2.GetReturnOffset
title: IDebugControl2::GetReturnOffset (dbgeng.h)
description: Learn about the GetReturnOffset method, which returns the return address for the current function.
old-location: debugger\getreturnoffset.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugControl2::GetReturnOffset"]
ms.keywords: GetReturnOffset, GetReturnOffset method [Windows Debugging], GetReturnOffset method [Windows Debugging],IDebugControl interface, GetReturnOffset method [Windows Debugging],IDebugControl2 interface, GetReturnOffset method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetReturnOffset method, IDebugControl2 interface [Windows Debugging],GetReturnOffset method, IDebugControl2.GetReturnOffset, IDebugControl2::GetReturnOffset, IDebugControl3 interface [Windows Debugging],GetReturnOffset method, IDebugControl3::GetReturnOffset, IDebugControl::GetReturnOffset, IDebugControl_7c101d44-aa43-48d4-8176-2ed110eca231.xml, dbgeng/IDebugControl2::GetReturnOffset, dbgeng/IDebugControl3::GetReturnOffset, dbgeng/IDebugControl::GetReturnOffset, debugger.getreturnoffset
req.header: dbgeng.h
req.include-header: Dbgeng.h
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IDebugControl2::GetReturnOffset
 - dbgeng/IDebugControl2::GetReturnOffset
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl2::GetReturnOffset
---

# IDebugControl2::GetReturnOffset


## -description

The <b>GetReturnOffset</b> method returns the return address for the current function.

## -parameters

### -param Offset 

[out]
Receives the return address.

## -returns

This method may also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
</table>

## -remarks

The return address is the location in the process's virtual address space of the instruction that will be executed when the current function returns.

