---
UID: NF:dbgeng.IDebugDataSpaces3.CheckLowMemory
title: IDebugDataSpaces3::CheckLowMemory (dbgeng.h)
description: Learn about the CheckLowMemory method, which checks for memory corruption in the low 4 GB of memory.
old-location: debugger\checklowmemory.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugDataSpaces3::CheckLowMemory"]
ms.keywords: CheckLowMemory, CheckLowMemory method [Windows Debugging], CheckLowMemory method [Windows Debugging],IDebugDataSpaces interface, CheckLowMemory method [Windows Debugging],IDebugDataSpaces2 interface, CheckLowMemory method [Windows Debugging],IDebugDataSpaces3 interface, CheckLowMemory method [Windows Debugging],IDebugDataSpaces4 interface, IDebugDataSpaces interface [Windows Debugging],CheckLowMemory method, IDebugDataSpaces2 interface [Windows Debugging],CheckLowMemory method, IDebugDataSpaces2::CheckLowMemory, IDebugDataSpaces3 interface [Windows Debugging],CheckLowMemory method, IDebugDataSpaces3.CheckLowMemory, IDebugDataSpaces3::CheckLowMemory, IDebugDataSpaces4 interface [Windows Debugging],CheckLowMemory method, IDebugDataSpaces4::CheckLowMemory, IDebugDataSpaces::CheckLowMemory, IDebugDataSpaces_6682f39e-295a-4dae-b8a3-d83b1d5e41be.xml, dbgeng/IDebugDataSpaces2::CheckLowMemory, dbgeng/IDebugDataSpaces3::CheckLowMemory, dbgeng/IDebugDataSpaces4::CheckLowMemory, dbgeng/IDebugDataSpaces::CheckLowMemory, debugger.checklowmemory
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
 - IDebugDataSpaces3::CheckLowMemory
 - dbgeng/IDebugDataSpaces3::CheckLowMemory
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Dbgeng.h
api_name:
 - IDebugDataSpaces3::CheckLowMemory
---

# IDebugDataSpaces3::CheckLowMemory


## -description

The <b>CheckLowMemory</b> method checks for memory corruption in the low 4 GB of memory.

## -parameters

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
No corruption was found.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>FACILITY_NT_BIT |<i>Page</i></b></dt>
</dl>
</td>
<td width="60%">
Corruption was found on the memory page <i>Page</i>.

</td>
</tr>
</table>
 

This method can also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

## -remarks

This method is only available in <a href="/windows-hardware/drivers/debugger/k">kernel-mode debugging</a>, and is only useful when the <a href="/windows-hardware/drivers/debugger/k">kernel</a> was booted using the <b>/nolowmem</b> option.

When the kernel is booted with the <b>/nolowmem</b> option, the kernel, drivers, operating system and applications are loaded in memory above 4 GB, while the low 4 GB of memory is filled with a unique pattern.  The <b>CheckLowMemory</b> method checks this pattern for corruption.

This may be used to verify that a driver behaves well when using physical addresses greater than 32 bits in length.  See <i>Physical Address Extension (PAE)</i>, <b>/pae</b>, and <b>/nolowmem</b> in the Windows Driver Kit.

