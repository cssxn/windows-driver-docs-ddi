---
UID: NF:pep_x.PEP_ACPI_INITIALIZE_INTERRUPT_RESOURCE
title: PEP_ACPI_INITIALIZE_INTERRUPT_RESOURCE function (pep_x.h)
description: Learn how the PEP_ACPI_INITIALIZE_INTERRUPT_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_INTERRUPT_RESOURCE structure.
old-location: kernel\pep_acpi_initialize_interrupt_resource.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PEP_ACPI_INITIALIZE_INTERRUPT_RESOURCE function"]
ms.keywords: PEP_ACPI_INITIALIZE_INTERRUPT_RESOURCE, PEP_ACPI_INITIALIZE_INTERRUPT_RESOURCE function [Kernel-Mode Driver Architecture], kernel.pep_acpi_initialize_interrupt_resource, pepfx/PEP_ACPI_INITIALIZE_INTERRUPT_RESOURCE
req.header: pep_x.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
 - PEP_ACPI_INITIALIZE_INTERRUPT_RESOURCE
 - pep_x/PEP_ACPI_INITIALIZE_INTERRUPT_RESOURCE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - PEP_ACPI_INITIALIZE_INTERRUPT_RESOURCE
---

# PEP_ACPI_INITIALIZE_INTERRUPT_RESOURCE function (pep_x.h)


## -description

The <b>PEP_ACPI_INITIALIZE_INTERRUPT_RESOURCE</b> function initializes a platform extension plug-in's (PEP) <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_interrupt_resource">PEP_ACPI_INTERRUPT_RESOURCE</a> structure.

## -parameters

### -param ResourceUsage 

[in]
Indicates if this device is in use.

### -param EdgeLevel 

[in]
A <a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_kinterrupt_mode">KINTERRUPT_MODE</a> enumeration value that identifies the interrupt type.

### -param InterruptLevel 

[in]
A <a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_kinterrupt_polarity">KINTERRUPT_POLARITY</a> enumeration value that identifies how a device signals an interrupt request on an interrupt line.

### -param ShareType 

[in]
Indicates if the device can be shared.

### -param Wake 

[in]
Indicates if the device can be woken from a low-power state.

### -param PinTable 

[in]
A list of pin numbers on the resource.

### -param PinCount 

[in]
The number of pins described by the <i>PinTable</i> parameter.

### -param Resource 

[out]
A pointer to the resource. The structure behind the pointer is of type <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_interrupt_resource">PEP_ACPI_INTERRUPT_RESOURCE</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_interrupt_resource">PEP_ACPI_INTERRUPT_RESOURCE</a>
