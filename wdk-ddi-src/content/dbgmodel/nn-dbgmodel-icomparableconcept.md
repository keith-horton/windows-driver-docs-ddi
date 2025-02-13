---
UID: NN:dbgmodel.IComparableConcept
title: IComparableConcept (dbgmodel.h)
description: The IComparableConcept interface compares this object to another object of arbitrary type. E_NOT_SET is returned if the comparison cannot be performed.
ms.date: 07/13/2018
keywords: ["IComparableConcept interface"]
req.header: dbgmodel.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.umdf-ver: 
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
 - IComparableConcept
 - dbgmodel/IComparableConcept
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IComparableConcept
---

# IComparableConcept interface


## -description

Compares this object to another (of arbitrary type).  If the comparison cannot be performed, E_NOT_SET should be returned.

## -inheritance

IComparableConcept inherits from IUnknown.

## -remarks

The return value passed in comparison result has the following meaning:

```text
< 0 : contextObject < otherObject
0 : contextObject == otherObject
> 0 : contextObject > otherObject
```

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)
