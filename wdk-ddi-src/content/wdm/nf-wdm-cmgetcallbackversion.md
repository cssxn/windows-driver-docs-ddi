---
UID: NF:wdm.CmGetCallbackVersion
title: CmGetCallbackVersion function (wdm.h)
description: The CmGetCallbackVersion routine retrieves the major and minor version numbers for the current version of the configuration manager's registry callback feature.
old-location: kernel\cmgetcallbackversion.htm
tech.root: kernel
ms.date: 07/29/2021
keywords: ["CmGetCallbackVersion function"]
ms.keywords: CmGetCallbackVersion, CmGetCallbackVersion routine [Kernel-Mode Driver Architecture], ConfigMgrRef_f15e2e9c-8b84-40b2-abb4-b37a6d38f920.xml, kernel.cmgetcallbackversion, wdm/CmGetCallbackVersion
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - CmGetCallbackVersion
 - wdm/CmGetCallbackVersion
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - CmGetCallbackVersion
---

# CmGetCallbackVersion function

## -description

The **CmGetCallbackVersion** routine retrieves the major and minor version numbers for the current version of the configuration manager's registry callback feature.

## -parameters

### -param Major

[out, optional] A pointer to a location that receives the major version number.

### -param Minor

[out, optional] A pointer to a location that receives the minor version number.

## -remarks

The **CmGetCallbackVersion** routine is available starting with Windows Vista.

For Windows Vista, the major version number is 1 and the minor version number is 0.

Starting with Windows 7, the major version number is 1 and the minor version number is 1.

Version 1.1 contains two changes from version 1.0.

First, in version 1.0, if multiple registry filter drivers are active on the computer at the same time, the **REG_POST_*XXX*_KEY_INFORMATION** structure passed to a driver's registry callback routine during the post-notification phase for a create-key or open-key operation might contain a non-NULL **Object** member, even though the operation failed and the **Status** member contains an error status. In version 1.1, the **Object** member is always NULL if the **Status** member is set to an error status value to indicate that the operation failed.

Second, in version 1.0, an uncaught exception in a registry callback routine is quietly accepted by the operating system. In version 1.1, this exception causes the computer to bug check.

For more information on the differences between versions, see [Filtering Registry Calls](/windows-hardware/drivers/kernel/filtering-registry-calls).

## -see-also

[REG_POST_CREATE_KEY_INFORMATION](/windows-hardware/drivers/ddi/wdm/ns-wdm-_reg_post_create_key_information)

[ZwCreateKey](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey)

[ZwOpenKey](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwopenkey)
