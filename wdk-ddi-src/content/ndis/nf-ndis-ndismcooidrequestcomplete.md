---
UID: NF:ndis.NdisMCoOidRequestComplete
title: NdisMCoOidRequestComplete function (ndis.h)
description: The NdisMCoOidRequestComplete function returns the final status of an OID request that a miniport driver's MiniportCoOidRequest function returned NDIS_STATUS_PENDING for.
old-location: netvista\ndismcooidrequestcomplete.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisMCoOidRequestComplete function"]
ms.keywords: NdisMCoOidRequestComplete, NdisMCoOidRequestComplete function [Network Drivers Starting with Windows Vista], condis_request_ref_516edd5f-ceae-4330-87b1-48a3a383e736.xml, ndis/NdisMCoOidRequestComplete, netvista.ndismcooidrequestcomplete
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_MCO_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisMCoOidRequestComplete
 - ndis/NdisMCoOidRequestComplete
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisMCoOidRequestComplete
---

# NdisMCoOidRequestComplete function


## -description

The 
  <b>NdisMCoOidRequestComplete</b> function returns the final status of an OID request that a miniport driver's
  
  <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_oid_request">MiniportCoOidRequest</a> function
  returned NDIS_STATUS_PENDING for.

## -parameters

### -param MiniportAdapterHandle [in]


A miniport adapter handle that NDIS passed to the 
     <i>MiniportAdapterHandle</i> parameter of the 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">
     MiniportInitializeEx</a> function.

### -param NdisMiniportVcHandle

A handle that identifies the virtual connection (VC). The miniport driver obtained this handle as
     an input parameter to its 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_create_vc">MiniportCoCreateVc</a> function, either
     when a client set up an outgoing call or when the call manager created a VC for a client-registered
     service access point (SAP). The call manager created the VC to indicate an incoming-call notification.
     If the request is 
     <u>not</u> VC-specific, this parameter is <b>NULL</b>.

### -param Request

A pointer to a buffer that is formatted as an 
     <a href="/windows-hardware/drivers/ddi/oidrequest/ns-oidrequest-ndis_oid_request">NDIS_OID_REQUEST</a> structure. The miniport
     driver obtained this pointer as an input parameter to its 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_oid_request">
     MiniportCoOidRequest</a> function.

### -param Status [in]


The final status of the request operation, either NDIS_STATUS_SUCCESS,
     NDIS_STATUS_REQUEST_ABORTED, or any driver-determined NDIS_STATUS_<i>XXX</i> value 
     <u>except</u> NDIS_STATUS_PENDING.

## -remarks

A CoNDIS miniport driver that returns NDIS_STATUS_PENDING from its 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_oid_request">MiniportCoOidRequest</a> function must
    call 
    <b>NdisMCoOidRequestComplete</b> after the miniport driver has finished the request operation.

A call to 
    <b>NdisMCoOidRequestComplete</b> causes a call to the 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_oid_request_complete">
    ProtocolCoOidRequestComplete</a> function of the overlying driver that called the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscooidrequest">NdisCoOidRequest</a> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_create_vc">MiniportCoCreateVc</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_oid_request">MiniportCoOidRequest</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="/windows-hardware/drivers/ddi/oidrequest/ns-oidrequest-ndis_oid_request">NDIS_OID_REQUEST</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscooidrequest">NdisCoOidRequest</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_oid_request_complete">
   ProtocolCoOidRequestComplete</a>
