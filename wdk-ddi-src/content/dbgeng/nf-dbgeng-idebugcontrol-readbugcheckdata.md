---
UID: NF:dbgeng.IDebugControl.ReadBugCheckData
title: IDebugControl::ReadBugCheckData (dbgeng.h)
description: Learn how the ReadBugCheckData method reads the kernel bug check code and related parameters.
old-location: debugger\readbugcheckdata.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugControl::ReadBugCheckData"]
ms.keywords: IDebugControl interface [Windows Debugging],ReadBugCheckData method, IDebugControl.ReadBugCheckData, IDebugControl2 interface [Windows Debugging],ReadBugCheckData method, IDebugControl2::ReadBugCheckData, IDebugControl3 interface [Windows Debugging],ReadBugCheckData method, IDebugControl3::ReadBugCheckData, IDebugControl::ReadBugCheckData, IDebugControl_d96bd559-1a82-4d5d-8aa8-7a32242f2b68.xml, ReadBugCheckData, ReadBugCheckData method [Windows Debugging], ReadBugCheckData method [Windows Debugging],IDebugControl interface, ReadBugCheckData method [Windows Debugging],IDebugControl2 interface, ReadBugCheckData method [Windows Debugging],IDebugControl3 interface, dbgeng/IDebugControl2::ReadBugCheckData, dbgeng/IDebugControl3::ReadBugCheckData, dbgeng/IDebugControl::ReadBugCheckData, debugger.readbugcheckdata
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
 - IDebugControl::ReadBugCheckData
 - dbgeng/IDebugControl::ReadBugCheckData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugControl::ReadBugCheckData
---

# IDebugControl::ReadBugCheckData


## -description

The <b>ReadBugCheckData</b> method reads the kernel bug check code and related parameters.

## -parameters

### -param Code 

[out]
Receives the bug check code.

### -param Arg1 

[out]
Receives the first parameter associated with the bug check.  The interpretation of this parameter depends on the bug check code.

### -param Arg2 

[out]
Receives the second parameter associated with the bug check.  The interpretation of this parameter depends on the bug check code.

### -param Arg3 

[out]
Receives the third parameter associated with the bug check.  The interpretation of this parameter depends on the bug check code.

### -param Arg4 

[out]
Receives the fourth parameter associated with the bug check.  The interpretation of this parameter depends on the bug check code.

## -returns

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
 

This method can also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

## -remarks

This method is only available in kernel-mode debugging.

For more information about bug checks, including a list of bug check codes and their interpretations, see <a href="/windows-hardware/drivers/debugger/bug-checks--blue-screens-">Bug Checks (Blue Screens)</a>.

