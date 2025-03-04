---
UID: NF:dbgeng.IDebugSymbolGroup.OutputAsType
title: IDebugSymbolGroup::OutputAsType (dbgeng.h)
description: The IDebugSymbolGroup::OutputAsType method changes the type of a symbol in a symbol group. The symbol's entry is updated to represent the new type.
old-location: debugger\outputastype.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugSymbolGroup::OutputAsType"]
ms.keywords: ComOther_6805cc12-0d46-4114-a40d-54c7e32b3c7c.xml, IDebugSymbolGroup interface [Windows Debugging],OutputAsType method, IDebugSymbolGroup.OutputAsType, IDebugSymbolGroup2 interface [Windows Debugging],OutputAsType method, IDebugSymbolGroup2::OutputAsType, IDebugSymbolGroup::OutputAsType, OutputAsType, OutputAsType method [Windows Debugging], OutputAsType method [Windows Debugging],IDebugSymbolGroup interface, OutputAsType method [Windows Debugging],IDebugSymbolGroup2 interface, dbgeng/IDebugSymbolGroup2::OutputAsType, dbgeng/IDebugSymbolGroup::OutputAsType, debugger.outputastype
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
 - IDebugSymbolGroup::OutputAsType
 - dbgeng/IDebugSymbolGroup::OutputAsType
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugSymbolGroup::OutputAsType
---

# IDebugSymbolGroup::OutputAsType


## -description

The <b>OutputAsType</b>  method changes the type of a symbol in a symbol group.  The symbol's entry is updated to represent the new type.

## -parameters

### -param Index 

[in]
The index of the entry in this symbol group.  The <i>index</i> of a symbol is an identification number. The index ranges from zero through the number of symbols in the symbol group minus one.

### -param Type 

[in]
The name of the type of the symbol that you want.  If the name begins with an exclamation mark (<b>!</b>), the name is treated as an extension.  For more information about how to use an extension as a type, see the Remarks section.

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

Because the children of the new entry type might differ from the children of the old entry type, the <b>OutputAsType</b> method removes all of the children of the entry from the symbol group.  You can add the children back by using the <a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbolgroup2-expandsymbol">ExpandSymbol</a> method.

If <i>Type</i> is an extension, the address of the symbol is passed to the extension.  Every line of output from the extension becomes a child symbol of the specified symbol.  These child symbols are text and you cannot manipulate them in any way.  For example, if the name of a variable is <b>@$teb</b>, you can change its type to <b>!teb</b>.

For more information about symbol groups, see <a href="/windows-hardware/drivers/debugger/scopes-and-symbol-groups">Scopes and Symbol Groups</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbolgroup2-expandsymbol">ExpandSymbol</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugsymbolgroup2-getnumbersymbols">GetNumberSymbols</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbolgroup">IDebugSymbolGroup</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugsymbolgroup2">IDebugSymbolGroup2</a>

