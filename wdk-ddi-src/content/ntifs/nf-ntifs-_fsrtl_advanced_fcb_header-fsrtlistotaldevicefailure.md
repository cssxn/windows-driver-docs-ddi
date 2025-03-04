---
UID: NF:ntifs.FsRtlIsTotalDeviceFailure
title: FsRtlIsTotalDeviceFailure function (ntifs.h)
description: The FsRtlIsTotalDeviceFailure function (ntifs.h) determines whether a media or other hardware failure has occurred.
old-location: ifsk\fsrtlistotaldevicefailure.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FsRtlIsTotalDeviceFailure function"]
ms.keywords: FsRtlIsTotalDeviceFailure, FsRtlIsTotalDeviceFailure routine [Installable File System Drivers], fsrtlref_b4ec70b9-8a76-4e47-905a-54238a0b9173.xml, ifsk.fsrtlistotaldevicefailure, ntddk/FsRtlIsTotalDeviceFailure
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 and later versions of Windows operating systems.
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
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - FsRtlIsTotalDeviceFailure
 - ntifs/FsRtlIsTotalDeviceFailure
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlIsTotalDeviceFailure
---

# FsRtlIsTotalDeviceFailure function (ntifs.h)


## -description

The <b>FsRtlIsTotalDeviceFailure</b> routine determines whether a media or other hardware failure has occurred.

## -parameters

### -param Status 

[in]
Specifies the current NTSTATUS value, usually within a file system's or fault-tolerant disk driver's completion routine.

## -returns

The <b>FsRtlIsTotalDeviceFailure</b> routine returns <b>TRUE</b> if an I/O request failed because the physical device has failed.

## -remarks

If <b>FsRtlIsTotalDeviceFailure</b> returns <b>TRUE</b>, a higher-level driver, such as a file system or fault-tolerant disk driver, usually logs an error before completing the IRP.

<b>FsRtlIsTotalDeviceFailure</b> does not return <b>TRUE</b> for either of the status values STATUS_DEVICE_DATA_ERROR and STATUS_CRC_ERROR, which are assumed to indicate a sector failure rather than a total disk failure.

For more information about handling device failure, see <a href="/windows/win32/seccrypto/common-hresult-values">Error Handling</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlisntstatusexpected">FsRtlIsNtstatusExpected</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnormalizentstatus">FsRtlNormalizeNtstatus</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iowriteerrorlogentry">IoWriteErrorLogEntry</a>
