---
UID: NF:dbgeng.IDebugBreakpoint.GetParameters
title: IDebugBreakpoint::GetParameters (dbgeng.h)
description: The GetParameters method returns the parameters for a breakpoint. This method belongs to the IDebugBreakpoint interface.
old-location: debugger\getparameters.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugBreakpoint::GetParameters"]
ms.keywords: ComOther_1e2f7a47-0f38-492a-a8b2-9eaa124a2f20.xml, GetParameters, GetParameters method [Windows Debugging], GetParameters method [Windows Debugging],IDebugBreakpoint interface, GetParameters method [Windows Debugging],IDebugBreakpoint2 interface, IDebugBreakpoint interface [Windows Debugging],GetParameters method, IDebugBreakpoint.GetParameters, IDebugBreakpoint2 interface [Windows Debugging],GetParameters method, IDebugBreakpoint2::GetParameters, IDebugBreakpoint::GetParameters, dbgeng/IDebugBreakpoint2::GetParameters, dbgeng/IDebugBreakpoint::GetParameters, debugger.getparameters
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
 - IDebugBreakpoint::GetParameters
 - dbgeng/IDebugBreakpoint::GetParameters
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugBreakpoint::GetParameters
---

# IDebugBreakpoint::GetParameters


## -description

The <b>GetParameters</b> method returns the parameters for a breakpoint.

## -parameters

### -param Params 

[out]
The breakpoint's parameters.  For more information about the parameters, see <a href="/windows-hardware/drivers/ddi/dbgeng/ns-dbgeng-_debug_breakpoint_parameters">DEBUG_BREAKPOINT_PARAMETERS</a>.

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

The <b>GetParameters</b> method is a convenience method that returns most of the parameters that the other <a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugbreakpoint">IDebugBreakpoint</a> methods return.

For a list of the parameters and flags that this method retrieves, and for other ways to read and write these parameters and flags, see <a href="/windows-hardware/drivers/debugger/controlling-breakpoint-flags-and-parameters">Controlling Breakpoint Flags and Parameters</a> and <a href="/windows-hardware/drivers/debugger/using-breakpoints2">Using Breakpoints</a>.

