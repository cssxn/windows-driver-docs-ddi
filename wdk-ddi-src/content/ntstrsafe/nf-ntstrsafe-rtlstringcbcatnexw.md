---
UID: NF:ntstrsafe.RtlStringCbCatNExW
title: RtlStringCbCatNExW function (ntstrsafe.h)
description: Learn how the RtlStringCbCatNExW and RtlStringCbCatNExA functions concatenate two byte-counted strings while limiting the size of the appended string.
old-location: kernel\rtlstringcbcatnex.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["RtlStringCbCatNExW function"]
ms.keywords: RtlStringCbCatNEx, RtlStringCbCatNExA, RtlStringCbCatNExW, RtlStringCbCatNExW function [Kernel-Mode Driver Architecture], STRSAFE_FILL_BEHIND_NULL, STRSAFE_FILL_ON_FAILURE, STRSAFE_IGNORE_NULLS, STRSAFE_NO_TRUNCATION, STRSAFE_NULL_ON_FAILURE, kernel.rtlstringcbcatnex, ntstrsafe/RtlStringCbCatNExA, ntstrsafe/RtlStringCbCatNExW, safestrings_9e639754-980b-4a6d-9760-b826a8e09351.xml
req.header: ntstrsafe.h
req.include-header: Ntstrsafe.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP with Service Pack 1 (SP1) and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: RtlStringCbCatNExW (Unicode) and RtlStringCbCatNExA (ANSI)
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ntstrsafe.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlStringCbCatNExW
 - ntstrsafe/RtlStringCbCatNExW
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ntstrsafe.lib
 - Ntstrsafe.dll
api_name:
 - RtlStringCbCatNExW
---

# RtlStringCbCatNExW function


## -description

The <b>RtlStringCbCatNExW</b> and <b>RtlStringCbCatNExA</b> functions concatenate two byte-counted strings while limiting the size of the appended string.

## -parameters

### -param pszDest 

[in, out, optional]
A pointer to a buffer which, on input, contains a null-terminated string to which <i>pszSrc</i> will be concatenated. On output, this is the destination buffer that contains the entire resultant string. The string at <i>pszSrc</i>, up to <i>cbMaxAppend</i> bytes, is added to the end of the string at <i>pszDest</i>, and terminated with a null character. The <i>pszDest</i> pointer can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>.

### -param cbDest 

[in]
The size of the destination buffer, in bytes. The buffer must be large enough to include both strings and the terminating null character.

For Unicode strings, the maximum number of bytes is NTSTRSAFE_MAX_CCH * sizeof(WCHAR). 

For ANSI strings, the maximum number of bytes is NTSTRSAFE_MAX_CCH * sizeof(char). 

If <i>pszDest</i> is <b>NULL</b>, <i>cbDest</i> must be zero.

### -param pszSrc 

[in, optional]
A pointer to a null-terminated string. This string will be concatenated to the end of the string that is contained in the buffer at <i>pszDest</i>. The <i>pszSrc</i> pointer can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>.

### -param cbToAppend

<p>The maximum number of bytes to append to <i>pszDest</i>. </p>

### -param ppszDestEnd 

[out, optional]
If the caller supplies a non-<b>NULL</b> address pointer, then after the concatenation operation completes, the function loads that address with a pointer to the destination buffer's resulting <b>NULL</b> string terminator.

### -param pcbRemaining 

[out, optional]
If the caller supplies a non-<b>NULL</b> address pointer, the function loads the address with the number of unused bytes that are in the buffer pointed to by <i>pszDest</i>, including bytes used for the terminating null character.

### -param dwFlags 

[in]
One or more flags and, optionally, a fill byte. The flags are defined as follows: 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="STRSAFE_FILL_BEHIND_NULL_"></a><a id="strsafe_fill_behind_null_"></a><dl>
<dt><b>STRSAFE_FILL_BEHIND_NULL </b></dt>
</dl>
</td>
<td width="60%">
If set and the function succeeds, the low byte of <i>dwFlags</i> is used to fill the portion of the destination buffer that follows the terminating null character. 

</td>
</tr>
<tr>
<td width="40%"><a id="STRSAFE_IGNORE_NULLS_"></a><a id="strsafe_ignore_nulls_"></a><dl>
<dt><b>STRSAFE_IGNORE_NULLS </b></dt>
</dl>
</td>
<td width="60%">
If set, either <i>pszDest </i>or<i> pszSrc</i>, or both, can be <b>NULL</b>. <b>NULL</b> <i>pszSrc</i> pointers are treated like empty strings (TEXT("")), which can be copied. <b>NULL</b> <i>pszDest</i> pointers cannot receive nonempty strings. 

</td>
</tr>
<tr>
<td width="40%"><a id="STRSAFE_FILL_ON_FAILURE_"></a><a id="strsafe_fill_on_failure_"></a><dl>
<dt><b>STRSAFE_FILL_ON_FAILURE </b></dt>
</dl>
</td>
<td width="60%">
If set and the function fails, the low byte of <i>dwFlags</i> is used to fill the entire destination buffer, and the buffer is null-terminated. This operation overwrites any preexisting buffer contents. 

</td>
</tr>
<tr>
<td width="40%"><a id="STRSAFE_NULL_ON_FAILURE_"></a><a id="strsafe_null_on_failure_"></a><dl>
<dt><b>STRSAFE_NULL_ON_FAILURE </b></dt>
</dl>
</td>
<td width="60%">
If set and the function fails, the destination buffer is set to an empty string (TEXT("")). This operation overwrites any preexisting buffer contents. 

</td>
</tr>
<tr>
<td width="40%"><a id="STRSAFE_NO_TRUNCATION_"></a><a id="strsafe_no_truncation_"></a><dl>
<dt><b>STRSAFE_NO_TRUNCATION </b></dt>
</dl>
</td>
<td width="60%">
If set and the function returns STATUS_BUFFER_OVERFLOW, the contents of the destination buffer are not modified.

</td>
</tr>
</table>

## -returns

The function returns one of the NTSTATUS values that are listed in the following table. For information about how to test NTSTATUS values, see <a href="/windows-hardware/drivers/kernel/using-ntstatus-values">Using NTSTATUS Values</a>.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
This <i>success</i> status means source data was present, the strings were fully concatenated without truncation, and the resultant destination buffer is null-terminated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
This <i>warning</i> status means the copy operation did not complete due to insufficient space in the destination buffer. If STRSAFE_NO_TRUNCATION is set in <i>dwFlags</i>, the destination buffer is not modified. If the flag is not set, the destination buffer contains a truncated version of the concatenated string.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
This <i>error</i> status means the function received an invalid input parameter. For more information, see the following paragraph.

The function returns the STATUS_INVALID_PARAMETER value when:

<ul>
<li>An invalid flag was specified.</li>
<li>The value in <i>cbDest</i> is larger than the maximum buffer size.</li>
<li>The destination buffer was already full.</li>
<li>A <b>NULL</b> pointer was present without the STRSAFE_IGNORE_NULLS flag.</li>
<li>The destination buffer pointer was <b>NULL</b>, but the buffer size was not zero.</li>
<li>The destination buffer pointer was <b>NULL</b>, or its length was zero, but a nonzero length source string was present.</li>
</ul>
</td>
</tr>
</table>

## -remarks

<b>RtlStringCbCatNExW</b> and <b>RtlStringCbCatNExA</b> should be used instead of the following functions: 

<ul>
<li>
<b>strncat</b>

</li>
<li>
<b>wcsncat</b>

</li>
</ul>
The size, in bytes, of the destination buffer is provided to <b>RtlStringCbCatNExW</b> and <b>RtlStringCbCatNExA</b> to ensure that they do not write past the end of the buffer. 

<b>RtlStringCbCatNEx</b> adds to the functionality of <a href="/windows-hardware/drivers/ddi/ntstrsafe/nf-ntstrsafe-rtlstringcbcatna">RtlStringCbCatN</a> by returning a pointer to the end of the destination string as well as the number of bytes left unused in that string. Flags can be passed to the function for additional control.

Use <b>RtlStringCbCatNExW</b> to handle Unicode strings and  <b>RtlStringCbCatNExA</b> to handle ANSI strings. The form you use depends on your data, as shown in the following table.

<table>
<tr>
<th>String data type</th>
<th>String literal</th>
<th>Function</th>
</tr>
<tr>
<td>
WCHAR

</td>
<td>
L"string"

</td>
<td>
<b>RtlStringCbCatNExW</b>

</td>
</tr>
<tr>
<td>
<b>char</b>

</td>
<td>
"string"

</td>
<td>
<b>RtlStringCbCatNExA</b>

</td>
</tr>
</table>
 

If <i>pszSrc</i> and <i>pszDest</i> point to overlapping strings, the behavior of the function is undefined.

Neither <i>pszSrc</i> nor <i>pszDest</i> can be <b>NULL</b> unless the STRSAFE_IGNORE_NULLS flag is set, in which case either or both can be <b>NULL</b>. If <i>pszDest</i> is <b>NULL</b>, <i>pszSrc</i> must either be <b>NULL</b> or point to an empty string.

For more information about the safe string functions, see <a href="/windows-hardware/drivers/kernel/using-safe-string-functions">Using Safe String Functions</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntstrsafe/nf-ntstrsafe-rtlstringcbcatexa">RtlStringCbCatEx</a>



<a href="/windows-hardware/drivers/ddi/ntstrsafe/nf-ntstrsafe-rtlstringcbcatna">RtlStringCbCatN</a>



<a href="/windows-hardware/drivers/ddi/ntstrsafe/nf-ntstrsafe-rtlstringcchcatnexa">RtlStringCchCatNEx</a>

