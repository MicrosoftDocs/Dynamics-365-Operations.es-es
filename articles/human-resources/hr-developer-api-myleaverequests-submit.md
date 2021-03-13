---
title: Enviar una solicitud de baja al flujo de trabajo
description: En Microsoft Dynamics 365 Human Resources, puede utilizar la interfaz de programación de aplicaciones (API) MyLeaveRequests submit() para enviar una solicitud de baja al flujo de trabajo.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 51be70edbe1439340377fd01b9760d49d3a75348
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2021
ms.locfileid: "5115521"
---
# <a name="submit-a-leave-request-to-workflow"></a>Enviar una solicitud de baja al flujo de trabajo

En Microsoft Dynamics 365 Human Resources, puede utilizar la interfaz de programación de aplicaciones (API) MyLeaveRequests submit() para enviar una solicitud de baja al flujo de trabajo. Esta API se expone como una acción en la entidad OData MyLeaveRequests.

## <a name="prerequisites"></a>Requisitos previos

La solicitud de baja debe guardarse en la base de datos y se debe poder recuperar a través de la entidad MyLeaveRequests.

## <a name="permissions"></a>Permisos

Se requiere uno de los siguientes permisos para llamar a esta API. Para obtener más información acerca de los permisos y de cómo seleccionarlos, consulte [Autenticación](hr-developer-api-authentication.md).

| Tipo de permiso                    | Permisos (de menos a más privilegios) |
|------------------------------------|--------------------------------------------------------|
| Delegado (cuenta profesional o educativa) | usuario\_suplantación                                    |

## <a name="https-request"></a>Solicitud HTTPS

<!-- { "blockType": "ignored" } -->
```HTTP
POST https://{cluster}.hr.talent.dynamics.com/namespaces/{namespace_guid}/data/MyLeaveRequests(RequestId='{requestId}', LeaveType='{leaveType}', LeaveDate={leaveDate}, dataAreaId={dataArea})/Microsoft.Dynamics.DataEntities.submit?cross-company=true
```

La solicitud se ajusta a los estándares OData. Los parámetros {requestId}, {leaveType}, {leaveDate} y {dataArea} hacen referencia a los campos que componen la clave natural compuesta para la entidad MyLeaveRequests.

> [!NOTE]
> Si bien los campos para la entidad MyLeaveRequests se refieren a una línea individual en la solicitud de baja, al llamar a la API de envío se enviará toda la solicitud de baja (todas las líneas) al flujo de trabajo.

### <a name="request-headers"></a>Encabezados de solicitud

| Encabezado         | Valor                     |
|----------------|---------------------------|
| Autorización  | Portador {token} (requerido) |
| Content-Type   | application/json          |

### <a name="request-body"></a>Cuerpo de solicitud

No proporcione un cuerpo de solicitud para este método.

### <a name="response"></a>Respuesta

Una respuesta exitosa siempre es una respuesta **204 Sin contenido**.

Las personas que llaman no autorizadas recibirán una respuesta **401 No autorizado** o **403 Prohibido**.

Si el envío no tiene éxito (debido a la validación, por ejemplo), la respuesta será un **500 Error de servidor** y el cuerpo de la respuesta incluirá un objeto JSON con más detalles.

## <a name="example"></a>Ejemplo

```http
POST https://aos-rts-sf-550e5c091f6-prod-westus2.hr.talent.dynamics.com/namespaces/b2eb8003-334f-4a84-ab63-edbe23569090/data/MyLeaveRequests(RequestId='USMF-000065', LeaveType='Vacation', LeaveDate=2019-10-04T12:00:00Z, dataAreaId='USMF')/Microsoft.Dynamics.DataEntities.submit
```

```json
{
  "error": {
    "code": "",
    "message": "An error has occurred.",
    "innererror": {
      "message": "Exception occurred while executing action submit on Entity MyLeaveRequest: The request would put the 'Vacation' balance below the allowed minimum balance on 9/10/2019.",
      "type": "System.InvalidOperationException",
      "stacktrace": "   at Microsoft.Dynamics.Platform.Integration.Services.OData.Action.ActionInvokable.Invoke()   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.UpdateProcessor.ActionInvocation(ChangeOperationContext context, ActionInvokable action)   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.UpdateManager.<>c__DisplayClass13_0.<ScheduleInvokable>b__0(ChangeOperationContext context)   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.ChangeInfo.ExecuteActionsInCompanyContext(IEnumerable`1 actionList, ChangeOperationContext operationContext)\r\n   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.ChangeInfo.ExecuteActions(ChangeOperationContext context)   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.UpdateManager.SaveChanges()   at Microsoft.Dynamics.Platform.Integration.Services.OData.AxODataDelegatingHandler.<SaveChangesAsync>d__3.MoveNext()"
    }
  }
}
```

## <a name="validation-and-error-messages"></a>Validación y mensajes de error

Como parte de la llamada a la API de envío, Recursos Humanos realiza la validación de la lógica de negocios antes del envío, lo que garantiza que la solicitud de baja se encuentre en un estado válido para el envío. Los posibles mensajes de error que puede recibir en la respuesta si se produce un error en las validaciones son:

 - La solicitud pondría el saldo '{LeaveTypeId}' por debajo del saldo mínimo permitido en {date}.
 - La solicitud de permiso en el estado Completado no se puede enviar.
 - No se puede enviar o guardar la solicitud ya que no se han realizado cambios. Agregue o actualice la cantidad o el tipo de baja e inténtelo de nuevo.
 - La solicitud de indisponibilidad introducida contiene uno o más días con la misma fecha y tipo de baja que una solicitud pendiente existente. Recupere la solicitud existente para realizar cambios.
 - El código de motivo '{ReasonCodeId}' no se aplica a ninguno de los tipos de bajas de la solicitud.
 - El tipo de baja "{LeaveTypeId}" requiere un código de motivo. Seleccione el tipo adecuado y el código de motivo.
 - La indisponibilidad no se ha enviado correctamente. La indisponibilidad se ha guardado como un borrador de solicitud.

## <a name="see-also"></a>Consulte también

- [Visión general de MyLeaveRequests](hr-developer-api-myleaverequests-overview.md)
- [Autenticación](hr-developer-api-authentication.md)