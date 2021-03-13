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
# <a name="submit-a-leave-request-to-workflow"></a><span data-ttu-id="38bbd-103">Enviar una solicitud de baja al flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="38bbd-103">Submit a leave request to workflow</span></span>

<span data-ttu-id="38bbd-104">En Microsoft Dynamics 365 Human Resources, puede utilizar la interfaz de programación de aplicaciones (API) MyLeaveRequests submit() para enviar una solicitud de baja al flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="38bbd-104">In Microsoft Dynamics 365 Human Resources, you can use the MyLeaveRequests submit() application programming interface (API) to submit a leave request to workflow.</span></span> <span data-ttu-id="38bbd-105">Esta API se expone como una acción en la entidad OData MyLeaveRequests.</span><span class="sxs-lookup"><span data-stu-id="38bbd-105">This API is exposed as an action on the MyLeaveRequests OData entity.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="38bbd-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="38bbd-106">Prerequisites</span></span>

<span data-ttu-id="38bbd-107">La solicitud de baja debe guardarse en la base de datos y se debe poder recuperar a través de la entidad MyLeaveRequests.</span><span class="sxs-lookup"><span data-stu-id="38bbd-107">The leave request must be saved in the database and must be retrievable through the MyLeaveRequests entity.</span></span>

## <a name="permissions"></a><span data-ttu-id="38bbd-108">Permisos</span><span class="sxs-lookup"><span data-stu-id="38bbd-108">Permissions</span></span>

<span data-ttu-id="38bbd-109">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="38bbd-109">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="38bbd-110">Para obtener más información acerca de los permisos y de cómo seleccionarlos, consulte [Autenticación](hr-developer-api-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="38bbd-110">For more information about permissions and how to select them, see [Authentication](hr-developer-api-authentication.md).</span></span>

| <span data-ttu-id="38bbd-111">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="38bbd-111">Permission type</span></span>                    | <span data-ttu-id="38bbd-112">Permisos (de menos a más privilegios)</span><span class="sxs-lookup"><span data-stu-id="38bbd-112">Permissions (from least privileged to most privileged)</span></span> |
|------------------------------------|--------------------------------------------------------|
| <span data-ttu-id="38bbd-113">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="38bbd-113">Delegated (work or school account)</span></span> | <span data-ttu-id="38bbd-114">usuario\_suplantación</span><span class="sxs-lookup"><span data-stu-id="38bbd-114">user\_impersonation</span></span>                                    |

## <a name="https-request"></a><span data-ttu-id="38bbd-115">Solicitud HTTPS</span><span class="sxs-lookup"><span data-stu-id="38bbd-115">HTTPS request</span></span>

<!-- { "blockType": "ignored" } -->
```HTTP
POST https://{cluster}.hr.talent.dynamics.com/namespaces/{namespace_guid}/data/MyLeaveRequests(RequestId='{requestId}', LeaveType='{leaveType}', LeaveDate={leaveDate}, dataAreaId={dataArea})/Microsoft.Dynamics.DataEntities.submit?cross-company=true
```

<span data-ttu-id="38bbd-116">La solicitud se ajusta a los estándares OData.</span><span class="sxs-lookup"><span data-stu-id="38bbd-116">The request conforms to OData standards.</span></span> <span data-ttu-id="38bbd-117">Los parámetros {requestId}, {leaveType}, {leaveDate} y {dataArea} hacen referencia a los campos que componen la clave natural compuesta para la entidad MyLeaveRequests.</span><span class="sxs-lookup"><span data-stu-id="38bbd-117">The {requestId}, {leaveType}, {leaveDate}, and {dataArea} parameters refer to the fields that make up the composite natural key for the MyLeaveRequests entity.</span></span>

> [!NOTE]
> <span data-ttu-id="38bbd-118">Si bien los campos para la entidad MyLeaveRequests se refieren a una línea individual en la solicitud de baja, al llamar a la API de envío se enviará toda la solicitud de baja (todas las líneas) al flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="38bbd-118">While the fields for the MyLeaveRequests entity refer to an individual line in the leave request, calling the submit API will submit the entire leave request (all lines) to workflow.</span></span>

### <a name="request-headers"></a><span data-ttu-id="38bbd-119">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="38bbd-119">Request headers</span></span>

| <span data-ttu-id="38bbd-120">Encabezado</span><span class="sxs-lookup"><span data-stu-id="38bbd-120">Header</span></span>         | <span data-ttu-id="38bbd-121">Valor</span><span class="sxs-lookup"><span data-stu-id="38bbd-121">Value</span></span>                     |
|----------------|---------------------------|
| <span data-ttu-id="38bbd-122">Autorización</span><span class="sxs-lookup"><span data-stu-id="38bbd-122">Authorization</span></span>  | <span data-ttu-id="38bbd-123">Portador {token} (requerido)</span><span class="sxs-lookup"><span data-stu-id="38bbd-123">Bearer {token} (required)</span></span> |
| <span data-ttu-id="38bbd-124">Content-Type</span><span class="sxs-lookup"><span data-stu-id="38bbd-124">Content-Type</span></span>   | <span data-ttu-id="38bbd-125">application/json</span><span class="sxs-lookup"><span data-stu-id="38bbd-125">application/json</span></span>          |

### <a name="request-body"></a><span data-ttu-id="38bbd-126">Cuerpo de solicitud</span><span class="sxs-lookup"><span data-stu-id="38bbd-126">Request body</span></span>

<span data-ttu-id="38bbd-127">No proporcione un cuerpo de solicitud para este método.</span><span class="sxs-lookup"><span data-stu-id="38bbd-127">Don't supply a request body for this method.</span></span>

### <a name="response"></a><span data-ttu-id="38bbd-128">Respuesta</span><span class="sxs-lookup"><span data-stu-id="38bbd-128">Response</span></span>

<span data-ttu-id="38bbd-129">Una respuesta exitosa siempre es una respuesta **204 Sin contenido**.</span><span class="sxs-lookup"><span data-stu-id="38bbd-129">A successful response is always a **204 No Content** response.</span></span>

<span data-ttu-id="38bbd-130">Las personas que llaman no autorizadas recibirán una respuesta **401 No autorizado** o **403 Prohibido**.</span><span class="sxs-lookup"><span data-stu-id="38bbd-130">Unauthorized callers will receive a **401 Unauthorized** or a **403 Forbidden** response.</span></span>

<span data-ttu-id="38bbd-131">Si el envío no tiene éxito (debido a la validación, por ejemplo), la respuesta será un **500 Error de servidor** y el cuerpo de la respuesta incluirá un objeto JSON con más detalles.</span><span class="sxs-lookup"><span data-stu-id="38bbd-131">If submission is unsuccessful (because of validation, for example), the response will be a **500 Server Error**, and the response body will include a JSON object with further details.</span></span>

## <a name="example"></a><span data-ttu-id="38bbd-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="38bbd-132">Example</span></span>

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

## <a name="validation-and-error-messages"></a><span data-ttu-id="38bbd-133">Validación y mensajes de error</span><span class="sxs-lookup"><span data-stu-id="38bbd-133">Validation and error messages</span></span>

<span data-ttu-id="38bbd-134">Como parte de la llamada a la API de envío, Recursos Humanos realiza la validación de la lógica de negocios antes del envío, lo que garantiza que la solicitud de baja se encuentre en un estado válido para el envío.</span><span class="sxs-lookup"><span data-stu-id="38bbd-134">As part of the call to the submit API, Human Resources performs business logic validation before submission, which ensures the leave request is in a valid state for submission.</span></span> <span data-ttu-id="38bbd-135">Los posibles mensajes de error que puede recibir en la respuesta si se produce un error en las validaciones son:</span><span class="sxs-lookup"><span data-stu-id="38bbd-135">The possible error messages you may receive in the response if validations fail are:</span></span>

 - <span data-ttu-id="38bbd-136">La solicitud pondría el saldo '{LeaveTypeId}' por debajo del saldo mínimo permitido en {date}.</span><span class="sxs-lookup"><span data-stu-id="38bbd-136">The request would put the '{LeaveTypeId}' balance below the allowed minimum balance on {date}.</span></span>
 - <span data-ttu-id="38bbd-137">La solicitud de permiso en el estado Completado no se puede enviar.</span><span class="sxs-lookup"><span data-stu-id="38bbd-137">Time off request in Completed state cannot be submitted.</span></span>
 - <span data-ttu-id="38bbd-138">No se puede enviar o guardar la solicitud ya que no se han realizado cambios.</span><span class="sxs-lookup"><span data-stu-id="38bbd-138">Unable to submit or save request as no changes have been made.</span></span> <span data-ttu-id="38bbd-139">Agregue o actualice la cantidad o el tipo de baja e inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="38bbd-139">Add or update the amount or the leave type and try again.</span></span>
 - <span data-ttu-id="38bbd-140">La solicitud de indisponibilidad introducida contiene uno o más días con la misma fecha y tipo de baja que una solicitud pendiente existente.</span><span class="sxs-lookup"><span data-stu-id="38bbd-140">The time off request entered contains one or more days with the same date and leave type as an existing pending request.</span></span> <span data-ttu-id="38bbd-141">Recupere la solicitud existente para realizar cambios.</span><span class="sxs-lookup"><span data-stu-id="38bbd-141">Please recall the existing request to make changes.</span></span>
 - <span data-ttu-id="38bbd-142">El código de motivo '{ReasonCodeId}' no se aplica a ninguno de los tipos de bajas de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="38bbd-142">Reason code '{ReasonCodeId}' doesn't apply to any of the leave types in the request.</span></span>
 - <span data-ttu-id="38bbd-143">El tipo de baja "{LeaveTypeId}" requiere un código de motivo.</span><span class="sxs-lookup"><span data-stu-id="38bbd-143">Leave type '{LeaveTypeId}' requires a reason code.</span></span> <span data-ttu-id="38bbd-144">Seleccione el tipo adecuado y el código de motivo.</span><span class="sxs-lookup"><span data-stu-id="38bbd-144">Select the appropriate type and reason code.</span></span>
 - <span data-ttu-id="38bbd-145">La indisponibilidad no se ha enviado correctamente.</span><span class="sxs-lookup"><span data-stu-id="38bbd-145">The time off was not submitted successfully.</span></span> <span data-ttu-id="38bbd-146">La indisponibilidad se ha guardado como un borrador de solicitud.</span><span class="sxs-lookup"><span data-stu-id="38bbd-146">The time off has been saved as a draft request.</span></span>

## <a name="see-also"></a><span data-ttu-id="38bbd-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="38bbd-147">See also</span></span>

- [<span data-ttu-id="38bbd-148">Visión general de MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="38bbd-148">MyLeaveRequests overview</span></span>](hr-developer-api-myleaverequests-overview.md)
- [<span data-ttu-id="38bbd-149">Autenticación</span><span class="sxs-lookup"><span data-stu-id="38bbd-149">Authentication</span></span>](hr-developer-api-authentication.md)