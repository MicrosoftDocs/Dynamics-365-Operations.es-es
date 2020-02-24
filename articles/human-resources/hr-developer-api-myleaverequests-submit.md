---
title: Enviar una solicitud de baja al flujo de trabajo
description: ''
author: andreabichsel
manager: AnnBe
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
ms.openlocfilehash: 008ee231ca9f0459e332b17cea9f2a3f3e3cc2a5
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010514"
---
# <a name="submit-a-leave-request-to-workflow"></a><span data-ttu-id="e4030-102">Enviar una solicitud de baja al flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="e4030-102">Submit a leave request to workflow</span></span>

<span data-ttu-id="e4030-103">En Microsoft Dynamics 365 Human Resources, puede utilizar la interfaz de programación de aplicaciones (API) MyLeaveRequests submit() para enviar una solicitud de baja al flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e4030-103">In Microsoft Dynamics 365 Human Resources, you can use the MyLeaveRequests submit() application programming interface (API) to submit a leave request to workflow.</span></span> <span data-ttu-id="e4030-104">Esta API se expone como una acción en la entidad OData MyLeaveRequests.</span><span class="sxs-lookup"><span data-stu-id="e4030-104">This API is exposed as an action on the MyLeaveRequests OData entity.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e4030-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="e4030-105">Prerequisites</span></span>

<span data-ttu-id="e4030-106">La solicitud de baja debe guardarse en la base de datos y se debe poder recuperar a través de la entidad MyLeaveRequests.</span><span class="sxs-lookup"><span data-stu-id="e4030-106">The leave request must be saved in the database and must be retrievable through the MyLeaveRequests entity.</span></span>

## <a name="permissions"></a><span data-ttu-id="e4030-107">Permisos</span><span class="sxs-lookup"><span data-stu-id="e4030-107">Permissions</span></span>

<span data-ttu-id="e4030-108">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="e4030-108">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e4030-109">Para obtener más información acerca de los permisos y de cómo seleccionarlos, consulte [Autenticación](hr-developer-api-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="e4030-109">For more information about permissions and how to select them, see [Authentication](hr-developer-api-authentication.md).</span></span>

| <span data-ttu-id="e4030-110">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="e4030-110">Permission type</span></span>                    | <span data-ttu-id="e4030-111">Permisos (de menos a más privilegios)</span><span class="sxs-lookup"><span data-stu-id="e4030-111">Permissions (from least privileged to most privileged)</span></span> |
|------------------------------------|--------------------------------------------------------|
| <span data-ttu-id="e4030-112">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="e4030-112">Delegated (work or school account)</span></span> | <span data-ttu-id="e4030-113">usuario\_suplantación</span><span class="sxs-lookup"><span data-stu-id="e4030-113">user\_impersonation</span></span>                                    |

## <a name="https-request"></a><span data-ttu-id="e4030-114">Solicitud HTTPS</span><span class="sxs-lookup"><span data-stu-id="e4030-114">HTTPS request</span></span>

<!-- { "blockType": "ignored" } -->
```HTTP
POST https://{cluster}.hr.talent.dynamics.com/namespaces/{namespace_guid}/data/MyLeaveRequests(RequestId='{requestId}', LeaveType='{leaveType}', LeaveDate={leaveDate}, dataAreaId={dataArea})/Microsoft.Dynamics.DataEntities.submit?cross-company=true
```

<span data-ttu-id="e4030-115">La solicitud se ajusta a los estándares OData.</span><span class="sxs-lookup"><span data-stu-id="e4030-115">The request conforms to OData standards.</span></span> <span data-ttu-id="e4030-116">Los parámetros {requestId}, {leaveType}, {leaveDate} y {dataArea} hacen referencia a los campos que componen la clave natural compuesta para la entidad MyLeaveRequests.</span><span class="sxs-lookup"><span data-stu-id="e4030-116">The {requestId}, {leaveType}, {leaveDate}, and {dataArea} parameters refer to the fields that make up the composite natural key for the MyLeaveRequests entity.</span></span>

> [!NOTE]
> <span data-ttu-id="e4030-117">Si bien los campos para la entidad MyLeaveRequests se refieren a una línea individual en la solicitud de baja, al llamar a la API de envío se enviará toda la solicitud de baja (todas las líneas) al flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e4030-117">While the fields for the MyLeaveRequests entity refer to an individual line in the leave request, calling the submit API will submit the entire leave request (all lines) to workflow.</span></span>

### <a name="request-headers"></a><span data-ttu-id="e4030-118">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="e4030-118">Request headers</span></span>

| <span data-ttu-id="e4030-119">Encabezado</span><span class="sxs-lookup"><span data-stu-id="e4030-119">Header</span></span>         | <span data-ttu-id="e4030-120">Valor</span><span class="sxs-lookup"><span data-stu-id="e4030-120">Value</span></span>                     |
|----------------|---------------------------|
| <span data-ttu-id="e4030-121">Autorización</span><span class="sxs-lookup"><span data-stu-id="e4030-121">Authorization</span></span>  | <span data-ttu-id="e4030-122">Portador {token} (requerido)</span><span class="sxs-lookup"><span data-stu-id="e4030-122">Bearer {token} (required)</span></span> |
| <span data-ttu-id="e4030-123">Content-Type</span><span class="sxs-lookup"><span data-stu-id="e4030-123">Content-Type</span></span>   | <span data-ttu-id="e4030-124">application/json</span><span class="sxs-lookup"><span data-stu-id="e4030-124">application/json</span></span>          |

### <a name="request-body"></a><span data-ttu-id="e4030-125">Cuerpo de solicitud</span><span class="sxs-lookup"><span data-stu-id="e4030-125">Request body</span></span>

<span data-ttu-id="e4030-126">No proporcione un cuerpo de solicitud para este método.</span><span class="sxs-lookup"><span data-stu-id="e4030-126">Don't supply a request body for this method.</span></span>

### <a name="response"></a><span data-ttu-id="e4030-127">Respuesta</span><span class="sxs-lookup"><span data-stu-id="e4030-127">Response</span></span>

<span data-ttu-id="e4030-128">Una respuesta exitosa siempre es una respuesta **204 Sin contenido**.</span><span class="sxs-lookup"><span data-stu-id="e4030-128">A successful response is always a **204 No Content** response.</span></span>

<span data-ttu-id="e4030-129">Las personas que llaman no autorizadas recibirán una respuesta **401 No autorizado** o **403 Prohibido**.</span><span class="sxs-lookup"><span data-stu-id="e4030-129">Unauthorized callers will receive a **401 Unauthorized** or a **403 Forbidden** response.</span></span>

<span data-ttu-id="e4030-130">Si el envío no tiene éxito (debido a la validación, por ejemplo), la respuesta será un **500 Error de servidor** y el cuerpo de la respuesta incluirá un objeto JSON con más detalles.</span><span class="sxs-lookup"><span data-stu-id="e4030-130">If submission is unsuccessful (because of validation, for example), the response will be a **500 Server Error**, and the response body will include a JSON object with further details.</span></span>

## <a name="example"></a><span data-ttu-id="e4030-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e4030-131">Example</span></span>

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

## <a name="validation-and-error-messages"></a><span data-ttu-id="e4030-132">Validación y mensajes de error</span><span class="sxs-lookup"><span data-stu-id="e4030-132">Validation and error messages</span></span>

<span data-ttu-id="e4030-133">Como parte de la llamada a la API de envío, Recursos Humanos realiza la validación de la lógica de negocios antes del envío, lo que garantiza que la solicitud de baja se encuentre en un estado válido para el envío.</span><span class="sxs-lookup"><span data-stu-id="e4030-133">As part of the call to the submit API, Human Resources performs business logic validation before submission, which ensures the leave request is in a valid state for submission.</span></span> <span data-ttu-id="e4030-134">Los posibles mensajes de error que puede recibir en la respuesta si se produce un error en las validaciones son:</span><span class="sxs-lookup"><span data-stu-id="e4030-134">The possible error messages you may receive in the response if validations fail are:</span></span>

 - <span data-ttu-id="e4030-135">La solicitud pondría el saldo '{LeaveTypeId}' por debajo del saldo mínimo permitido en {date}.</span><span class="sxs-lookup"><span data-stu-id="e4030-135">The request would put the '{LeaveTypeId}' balance below the allowed minimum balance on {date}.</span></span>
 - <span data-ttu-id="e4030-136">La solicitud de permiso en el estado Completado no se puede enviar.</span><span class="sxs-lookup"><span data-stu-id="e4030-136">Time off request in Completed state cannot be submitted.</span></span>
 - <span data-ttu-id="e4030-137">No se puede enviar o guardar la solicitud ya que no se han realizado cambios.</span><span class="sxs-lookup"><span data-stu-id="e4030-137">Unable to submit or save request as no changes have been made.</span></span> <span data-ttu-id="e4030-138">Agregue o actualice la cantidad o el tipo de baja e inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="e4030-138">Add or update the amount or the leave type and try again.</span></span>
 - <span data-ttu-id="e4030-139">La solicitud de indisponibilidad introducida contiene uno o más días con la misma fecha y tipo de baja que una solicitud pendiente existente.</span><span class="sxs-lookup"><span data-stu-id="e4030-139">The time off request entered contains one or more days with the same date and leave type as an existing pending request.</span></span> <span data-ttu-id="e4030-140">Recupere la solicitud existente para realizar cambios.</span><span class="sxs-lookup"><span data-stu-id="e4030-140">Please recall the existing request to make changes.</span></span>
 - <span data-ttu-id="e4030-141">El código de motivo '{ReasonCodeId}' no se aplica a ninguno de los tipos de bajas de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="e4030-141">Reason code '{ReasonCodeId}' doesn't apply to any of the leave types in the request.</span></span>
 - <span data-ttu-id="e4030-142">El tipo de baja "{LeaveTypeId}" requiere un código de motivo.</span><span class="sxs-lookup"><span data-stu-id="e4030-142">Leave type '{LeaveTypeId}' requires a reason code.</span></span> <span data-ttu-id="e4030-143">Seleccione el tipo adecuado y el código de motivo.</span><span class="sxs-lookup"><span data-stu-id="e4030-143">Select the appropriate type and reason code.</span></span>
 - <span data-ttu-id="e4030-144">La indisponibilidad no se ha enviado correctamente.</span><span class="sxs-lookup"><span data-stu-id="e4030-144">The time off was not submitted successfully.</span></span> <span data-ttu-id="e4030-145">La indisponibilidad se ha guardado como un borrador de solicitud.</span><span class="sxs-lookup"><span data-stu-id="e4030-145">The time off has been saved as a draft request.</span></span>

## <a name="see-also"></a><span data-ttu-id="e4030-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e4030-146">See also</span></span>

- [<span data-ttu-id="e4030-147">Visión general de MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="e4030-147">MyLeaveRequests overview</span></span>](hr-developer-api-myleaverequests-overview.md)
- [<span data-ttu-id="e4030-148">Autenticación</span><span class="sxs-lookup"><span data-stu-id="e4030-148">Authentication</span></span>](hr-developer-api-authentication.md)