---
title: IMemoryAllocator class
description: Implemented by the memory allocator for the StgConvertPropertyToVariant function.
ms.assetid: 'a0735b62-5ed3-42df-a320-b58c742645a8'
keywords: ["IMemoryAllocator class Structured Storage", "IMemoryAllocator class Structured Storage , described"]
topic_type:
- apiref
api_name:
- IMemoryAllocator
api_location:
- Ole32.lib
- Ole32.dll
api_type:
- COM
---

# IMemoryAllocator class

The **IMemoryAllocator** class is implemented by the memory allocator for the [**StgConvertPropertyToVariant**](https://msdn.microsoft.com/library/windows/desktop/aa380321) function.

## Methods



| Name                                                     | Description                                                                                                                                                                                                        |
|----------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [**Allocate**](imemoryallocator-allocate.md)<br/> | Allocates memory for the [**StgConvertPropertyToVariant**](https://msdn.microsoft.com/library/windows/desktop/aa380321) function when the function converts a **SERIALIZEDPROPERTYVALUE** data type to a **PROPVARIANT** data type.<br/> |
| [**Free**](https://msdn.microsoft.com/library/windows/desktop/aa381543)<br/>        | Frees the memory allocated by the [**Allocate**](imemoryallocator-allocate.md) method.<br/>                                                                                                                 |



�

## Remarks

This class is only used by the [**StgConvertPropertyToVariant**](https://msdn.microsoft.com/library/windows/desktop/aa380321) function.

## Requirements



|                                     |                                                                                      |
|-------------------------------------|--------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows�2000 Professional \[desktop apps only\]<br/>                           |
| Minimum supported server<br/> | Windows�2000 Server \[desktop apps only\]<br/>                                 |
| Library<br/>                  | <dl> <dt>Ole32.lib</dt> </dl> |



�

�




