---
UID: NF:dbgeng.IDebugBreakpoint2.GetFlags
title: IDebugBreakpoint2::GetFlags (dbgeng.h)
description: The GetFlags method returns the flags for a breakpoint. This method belongs to the IDebugBreakpoint2 interface.
old-location: debugger\getflags.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugBreakpoint2::GetFlags"]
ms.keywords: ComOther_5898a703-87fb-4d47-9d06-026783243e10.xml, GetFlags, GetFlags method [Windows Debugging], GetFlags method [Windows Debugging],IDebugBreakpoint interface, GetFlags method [Windows Debugging],IDebugBreakpoint2 interface, IDebugBreakpoint interface [Windows Debugging],GetFlags method, IDebugBreakpoint2 interface [Windows Debugging],GetFlags method, IDebugBreakpoint2.GetFlags, IDebugBreakpoint2::GetFlags, IDebugBreakpoint::GetFlags, dbgeng/IDebugBreakpoint2::GetFlags, dbgeng/IDebugBreakpoint::GetFlags, debugger.getflags
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
 - IDebugBreakpoint2::GetFlags
 - dbgeng/IDebugBreakpoint2::GetFlags
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugBreakpoint2::GetFlags
---

# IDebugBreakpoint2::GetFlags


## -description

The <b>GetFlags</b> method returns the flags for a breakpoint.

## -parameters

### -param Flags 

[out]
The breakpoint's flags.  For more information about the flag bit field and an explanation of each flag, see <a href="/windows-hardware/drivers/debugger/controlling-breakpoint-flags-and-parameters">Controlling Breakpoint Flags and Parameters</a>.

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
 

This method can also return error values.  For more information, see <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a>.

## -remarks

The <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-getparameters">GetParameters</a> method also returns the breakpoint's flags.

For more information about breakpoint properties, see <a href="/windows-hardware/drivers/debugger/controlling-breakpoint-flags-and-parameters">Controlling Breakpoint Flags and Parameters</a>.

