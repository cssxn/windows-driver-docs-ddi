---
UID: NF:dbgmodel.IKeyEnumerator.AddRef
title: IKeyEnumerator::AddRef (dbgmodel.h)
description: "The IKeyEnumerator::AddRef method increments the reference count for an interface on an object."
ms.date: 08/13/2018
keywords: ["IKeyEnumerator::AddRef"]
ms.keywords: IKeyEnumerator::AddRef, AddRef, IKeyEnumerator.AddRef, IKeyEnumerator::AddRef, IKeyEnumerator.AddRef
req.header: dbgmodel.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - IKeyEnumerator::AddRef
 - dbgmodel/IKeyEnumerator::AddRef
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IKeyEnumerator::AddRef
---

# IKeyEnumerator::AddRef


## -description

Increments the reference count for an interface on an object. This method should be called for every new copy of a pointer to an interface on an object. 

For more information, see [IUnknown::AddRef](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref) and [Introduction to COM](/cpp/atl/introduction-to-com).

## -parameters

## -returns

This method returns ULONG.

## -remarks

## -see-also

[IKeyEnumerator interface](nn-dbgmodel-ikeyenumerator.md)

