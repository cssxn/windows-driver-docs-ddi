---
UID: NF:dbgeng.IDebugBreakpoint2.GetCommand
title: IDebugBreakpoint2::GetCommand (dbgeng.h)
description: Learn how the GetCommand method returns the command string that is executed when a breakpoint is triggered. This method belongs to the IDebugBreakpoint2 interface.
old-location: debugger\getcommand.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugBreakpoint2::GetCommand"]
ms.keywords: ComOther_4bb08d44-5a99-4177-b8a4-8926f1e45dcf.xml, GetCommand, GetCommand method [Windows Debugging], GetCommand method [Windows Debugging],IDebugBreakpoint interface, GetCommand method [Windows Debugging],IDebugBreakpoint2 interface, IDebugBreakpoint interface [Windows Debugging],GetCommand method, IDebugBreakpoint2 interface [Windows Debugging],GetCommand method, IDebugBreakpoint2.GetCommand, IDebugBreakpoint2::GetCommand, IDebugBreakpoint::GetCommand, dbgeng/IDebugBreakpoint2::GetCommand, dbgeng/IDebugBreakpoint::GetCommand, debugger.getcommand
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
 - IDebugBreakpoint2::GetCommand
 - dbgeng/IDebugBreakpoint2::GetCommand
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugBreakpoint2::GetCommand
---

# IDebugBreakpoint2::GetCommand


## -description

The <b>GetCommand</b>  method returns the command string that is executed when a breakpoint is triggered.

## -parameters

### -param Buffer 

[out, optional]
The command string that is executed when the breakpoint is triggered.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.

### -param BufferSize 

[in]
The size, in characters, of the buffer that <i>Buffer</i> points to.

### -param CommandSize 

[out, optional]
The size of the command string.  If <i>CommandSize</i> is <b>NULL</b>, this information is not returned.

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
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful, but the buffer was not large enough to hold the command string and so the command string was truncated to fit.

</td>
</tr>
</table>
 

This method can also return error values.  For more information, see <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a>.

## -remarks

The command string is a list of debugger commands that are separated by semicolons.  These commands are executed every time that the breakpoint is triggered.  The commands are executed before the engine informs any event callbacks that the breakpoint has been triggered.

The <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugbreakpoint2-getparameters">GetParameters</a> method also returns the size of the breakpoint's command, <i>CommandSize</i>.

For more information about breakpoint properties, see <a href="/windows-hardware/drivers/debugger/controlling-breakpoint-flags-and-parameters">Controlling Breakpoint Flags and Parameters</a>.

