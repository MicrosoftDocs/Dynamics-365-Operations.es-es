---
title: Solucionar problemas durante la sincronización
description: Este tema proporciona información para la solución de problemas que puede ayudarlo a solucionar problemas durante la sincronización inicial.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: d51b547093825a6e7730b5fdfcfb1c081776c63c
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172723"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a>Solucionar problemas durante la sincronización

[!include [banner](../../includes/banner.md)]



Este tema proporciona información para solución de problemas de integración de escritura doble entre las aplicaciones de Finance and Operations y Common Data Service. Específicamente proporciona información que puede ayudarlo a solucionar problemas durante la sincronización inicial. 

> [!IMPORTANT]
> Algunos de los problemas que aborda este tema pueden requerir la función de administrador del sistema o Microsoft Azure Active Directory (Azure AD) credenciales de administrador de inquilinos. La sección para cada problema explica si se requiere una función o credenciales específicas.

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a>Verificar los errores de sincronización inicial en una aplicación Finance and Operations

Después de habilitar las plantillas de asignación, el estado de los mapas debe ser **Ejecutando**. Si el estado es **No ejecutando**, se produjeron errores durante la sincronización inicial. Para ver los errores, seleccione la pestaña **Detalles de sincronización inicial** en la página **Escritura doble**.

![Pestaña de detalles de sincronización inicial](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a>No puede completar la sincronización inicial: 400 Solicitud incorrecta

**Rol requerido para arreglar el error:** Administrador del sistema

Es posible que reciba el siguiente mensaje de error cuando intente ejecutar la asignación y la sincronización inicial:

*El servidor remoto devolvió un error: (400) Solicitud incorrecta.), exportación AX encontró un error*

A continuación se muestra un ejemplo del mensaje de error completo.

```console
Dual write Initial Sync completed with status: Error. Following are the details:
Executed leg: From AX Financial dimensions to CRM msdyn_dimensionattributes
with exported records count: 0, ImportRecordsErrorCount: 0,
ImportRecordsInsertedCount: 0 and ImportRecordsUpdatedCount: 0
ErrorsDetails:
Dual write Initial sync failed
Message: ([Bad Request], The remote server returned an error: (400) Bad Request.), AX export encountered an error
Stacktrace: at
Microsoft.Dynamics.Integrator.QueryGenerator.AxClient.\<ExportAxPackage\>d__16.MoveNext()
in X:\\bt\\1024532\\repo\\src\\Core\\QueryGenerator\\AxClient.cs:line 265
\--- End of stack trace from previous location where exception was thrown ---
at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
at Microsoft.D365.ServicePlatform.Context.ServiceContext.Activity.\<ExecuteAsync\>d__11\`2.MoveNext()
\--- End of stack trace from previous location where exception was thrown ---
```

Si este error ocurre de manera constante y no puede completar la sincronización inicial, siga estos pasos para solucionar el problema.

1. Inicie sesión en la máquina virtual (VM) para la aplicación Finance and Operations.
2. Abra Microsoft Management Console. 
3. En el panel **Servicios**, asegúrese de que el servicio de exportación de marco de Microsoft Dynamics 365 Data se está ejecutando. Reinícielo si se ha detenido, porque la sincronización inicial lo requiere.

## <a name="initial-synchronization-error-403-forbidden"></a>Error de sincronización inicial: 403 Prohibido

Es posible que reciba el siguiente mensaje de error durante la sincronización inicial:

*(\[Prohibido\], el servidor remoto devolvión un error: (403) Prohibido.), exportación AX encontró un error*

Para arreglar el problema, siga estos pasos.

1. Iniciar sesión en la aplicación Finance and Operations.
2. En la págona **aplicaciones Azure Active Directory**, elimine el cliente **DtAppID**, y luego agréguelo nuevamente.

![Lista de aplicaciones Azure AD](media/aad_applications.png)

## <a name="self-reference-failures-during-initial-synchronization"></a>Fallos de autorreferencia durante la sincronización inicial

Es posible que reciba un mensaje de error similar al siguiente ejemplo si alguna de sus asignaciones tiene autorreferencias:

*En Vendors V2, aparece el siguiente error: ID de registro: nuevo registro, Mensaje de error: No se pudo resolver el guid para el campo: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. No se encontró el valor de búsqueda: CN-001. Pruebe estas URL para verificar si los datos de referencia existen: `https://sampleorg.crm.dynamics.com/api/data/v9.0/msdyn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber` eq 'CN-001'*

Este tipo de error ocurre durante la sincronización inicial de las asignaciones que tienen autorreferencias. En el ejemplo anterior, la cuenta de la factura de campo hace referencia a la entidad del proveedor.

Para solucionar el problema, es posible que deba ejecutar la asignación dos veces antes de que la sincronización inicial sea exitosa.

