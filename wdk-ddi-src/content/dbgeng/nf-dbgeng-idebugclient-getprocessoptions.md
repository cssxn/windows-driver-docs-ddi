---
UID: NF:dbgeng.IDebugClient.GetProcessOptions
title: IDebugClient::GetProcessOptions (dbgeng.h)
description: The GetProcessOptions method retrieves the process options affecting the current process. This method belongs to the IDebugClient interface.
old-location: debugger\getprocessoptions.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugClient::GetProcessOptions"]
ms.keywords: GetProcessOptions, GetProcessOptions method [Windows Debugging], GetProcessOptions method [Windows Debugging],IDebugClient interface, GetProcessOptions method [Windows Debugging],IDebugClient2 interface, GetProcessOptions method [Windows Debugging],IDebugClient3 interface, GetProcessOptions method [Windows Debugging],IDebugClient4 interface, GetProcessOptions method [Windows Debugging],IDebugClient5 interface, IDebugClient interface [Windows Debugging],GetProcessOptions method, IDebugClient.GetProcessOptions, IDebugClient2 interface [Windows Debugging],GetProcessOptions method, IDebugClient2::GetProcessOptions, IDebugClient3 interface [Windows Debugging],GetProcessOptions method, IDebugClient3::GetProcessOptions, IDebugClient4 interface [Windows Debugging],GetProcessOptions method, IDebugClient4::GetProcessOptions, IDebugClient5 interface [Windows Debugging],GetProcessOptions method, IDebugClient5::GetProcessOptions, IDebugClient::GetProcessOptions, IDebugClient_5d54bc2a-5691-4a3a-b3c9-92fc577cdabb.xml, dbgeng/IDebugClient2::GetProcessOptions, dbgeng/IDebugClient3::GetProcessOptions, dbgeng/IDebugClient4::GetProcessOptions, dbgeng/IDebugClient5::GetProcessOptions, dbgeng/IDebugClient::GetProcessOptions, debugger.getprocessoptions
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
 - IDebugClient::GetProcessOptions
 - dbgeng/IDebugClient::GetProcessOptions
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugClient::GetProcessOptions
---

# IDebugClient::GetProcessOptions


## -description

The <b>GetProcessOptions</b> method retrieves the process options affecting the current process.

## -parameters

### -param Options 

[out]
Receives a set of flags representing the process options for the current process.  For details on these options, see <a href="/windows-hardware/drivers/debugger/debug-process-xxx">DEBUG_PROCESS_XXX</a>.

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

This method is only available in live user-mode debugging.

Some of the process options are global options, others are specific to the current process.

For more information about creating and attaching to live user-mode targets, see <a href="/windows-hardware/drivers/debugger/live-user-mode-targets">Live User-Mode Targets</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-addprocessoptions">AddProcessOptions</a>



<a href="/windows-hardware/drivers/debugger/debug-process-xxx">DEBUG_PROCESS_XXX</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient">IDebugClient</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient2">IDebugClient2</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient3">IDebugClient3</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient5">IDebugClient5</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-removeprocessoptions">RemoveProcessOptions</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugclient5-setprocessoptions">SetProcessOptions</a>

