---
UID: NF:wdtfpnpaction.IWDTFPNPAction2.EDTTryStopDeviceFailRestart
title: IWDTFPNPAction2::EDTTryStopDeviceFailRestart (wdtfpnpaction.h)
description: Learn how this method attempts to send an IRP_MN_STOP_DEVICE event to the target device and then fail the subsequent device restart.
old-location: dtf\iwdtfpnpaction2_edttrystopdevicefailrestart.htm
tech.root: dtf
ms.date: 04/04/2018
keywords: ["IWDTFPNPAction2::EDTTryStopDeviceFailRestart"]
ms.keywords: EDTTryStopDeviceFailRestart, EDTTryStopDeviceFailRestart method [Windows Device Testing Framework], EDTTryStopDeviceFailRestart method [Windows Device Testing Framework],IWDTFPNPAction2 interface, IWDTFPNPAction2 interface [Windows Device Testing Framework],EDTTryStopDeviceFailRestart method, IWDTFPNPAction2.EDTTryStopDeviceFailRestart, IWDTFPNPAction2::EDTTryStopDeviceFailRestart, Microsoft.WDTF.IWDTFPNPAction2.EDTTryStopDeviceFailRestart, Microsoft::WDTF::IWDTFPNPAction2::EDTTryStopDeviceFailRestart, dtf.iwdtfpnpaction2_edttrystopdevicefailrestart, wdtfpnpaction/IWDTFPNPAction2::EDTTryStopDeviceFailRestart
req.header: wdtfpnpaction.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFPNPAction.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTFDriverPNPAction.Interop.dll
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDTFPNPAction2::EDTTryStopDeviceFailRestart
 - wdtfpnpaction/IWDTFPNPAction2::EDTTryStopDeviceFailRestart
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WDTFDriverPNPAction.Interop.dll
api_name:
 - IWDTFPNPAction2::EDTTryStopDeviceFailRestart
---

# IWDTFPNPAction2::EDTTryStopDeviceFailRestart


## -description

Attempts to send an IRP_MN_STOP_DEVICE event to the target device and 
then fail the subsequent device restart.

## -parameters

### -param pbSuccess 

[out, retval]
True if the operation succeeds; otherwise, false.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -remarks

<div class="alert"><b>Note</b>  The <a href="/windows-hardware/drivers/ddi/wdtfedtaction/nf-wdtfedtaction-iwdtfenhanceddevicetestsupportaction2-enable">IWDTFEnhancedDeviceTestSupportAction2::Enable</a>  
method must be called for the target device before calling this method.</div>
<div> </div>
<b>EDTTryStopDeviceFailRestart</b> attempts to trigger a PnP resource 
rebalance (an Query Stop, Stop, Start IRP sequence) in which it fails the IRP_MN_START_DEVICE event 
which follows a successful Query Stop and Stop. The failed Start IRP, in turn, causes the system 
to surprise remove the device (IRP_MN_SURPRISE_REMOVAL).

The Stop IRP is not guaranteed. Other drivers on the stack can fail an 
IRP_MN_QUERY_STOP_DEVICE event which precedes the Stop IRP (resulting in IRP_MN_CANCEL_STOP_DEVICE). 
Also, the system may optimize if it detects that the target device does not use hardware 
resources (e.g. a USB mouse) and send a CancelStop IRP instead.

If your device does not consume hardware resources but you still wish to attempt to test 
how the drivers and applications handle the PnP resource rebalance with a failed start, you can 
instead run the <b>EDTTryStopDeviceFailRestart</b> method on a parent 
device, grandparent, etc., which does consume hardware resources. For example, if your device 
is a USB mouse, you can run this method on the parent USB controller instead.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdtfpnpaction/nn-wdtfpnpaction-iwdtfpnpaction2">IWDTFPNPAction2</a>

