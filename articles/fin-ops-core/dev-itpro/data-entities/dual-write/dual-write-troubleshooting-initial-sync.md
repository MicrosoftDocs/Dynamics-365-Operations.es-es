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
ms.openlocfilehash: 10065039fce441d7f96f700ff826d959e96f2479
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410090"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a>Solucionar problemas durante la sincronización

[!include [banner](../../includes/banner.md)]

Este tema proporciona información para solución de problemas de integración de escritura doble entre las aplicaciones de Finance and Operations y Common Data Service. Específicamente proporciona información que puede ayudarlo a solucionar problemas durante la sincronización inicial.

> [!IMPORTANT]
> Algunos de los problemas que aborda este tema pueden requerir la característica de administrador del sistema o Microsoft Azure Active Directory (Azure AD) credenciales de administrador de inquilinos. La sección para cada problema explica si se requiere una característica o credenciales específicas.

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

## <a name="self-reference-or-circular-reference-failures-during-initial-synchronization"></a>Errores de autorreferencia o de referencia circular durante la sincronización inicial

Es posible que reciba mensajes de error si alguna de sus asignaciones tiene autorreferencias o referencias circulares. Los errores se dividen en estas categorías:

- [Mapeo de entidades Proveedores V2 con msdyn_vendors](#error-vendor-map)
- [Mapeo de entidades Clientes V3 a Cuentas](#error-customer-map)

## <a name="resolve-an-error-in-vendors-v2-to-msdyn_vendors-entity-mapping"></a><a id="error-vendor-map"></a>Resolver un error en el mapeo de entidades Vendors V2 a msdyn_vendors

Puede encontrar los siguientes errores de sincronización inicial en el mapeo **Proveedores V2** con **msdyn_vendors** si las entidades tienen registros existentes con valores en los campos **PrimaryContactPersonId** e **InvoiceVendorAccountNumber**. Esto se debe a que **InvoiceVendorAccountNumber** es un campo de autorreferencia y **PrimaryContactPersonId** es una referencia circular en el mapeo del proveedor.

*No se pudo resolver el guid para el campo: <field> . No se encontró la búsqueda: <value> . Pruebe estas URL para verificar si los datos de referencia existen: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>*

Aquí hay un par de ejemplos:

- *No se pudo resolver el guid para el campo: msdyn_vendorprimarycontactperson.msdyn_contactpersonid. No se encontró la búsqueda: 000056. Pruebe estas URL para verificar si los datos de referencia existen: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*
- *No se pudo resolver el guid para el campo: msdyn_invoicevendoraccountnumber.msdyn_vendoraccountnumber. No se encontró la búsqueda: V24-1. Pruebe estas URL para verificar si los datos de referencia existen: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'*

Si tiene registros con valores en estos campos en la entidad del proveedor, siga los pasos en la sección a continuación para completar la sincronización inicial con éxito.

1. En la aplicación Finance and Operations, elimine los campos **PrimaryContactPersonId** e **InvoiceVendorAccountNumber** del mapeo y guarde los cambios.

    1. Navegue a la página de mapeo de doble escritura para **Proveedores V2 (msdyn_vendors)** y seleccione la pestaña **Asignaciones de entidades**. En el filtro izquierdo, seleccione **Aplicaciones Finance and Operations.Proveedores V2**. En el filtro derecho, seleccione **Sales.Vendor**.

    2. Busque **primarycontactperson** para encontrar el campo de origen **PrimaryContactPersonId**.
    
    3. Haga clic en el botón **Accionees** y seleccione **Eliminar**.
    
        ![Autorreferencia o referencia circular 3](media/vend_selfref3.png)
    
    4. Repita para eliminar el campo **InvoiceVendorAccountNumber**.
    
        ![Autorreferencia o referencia circular 4](media/vend-selfref4.png)
    
    5. Guardar los cambios de mapeo.

2. Deshabilite el seguimiento de cambios para la entidad **Proveedores V2**.

    1. Navegue a **Gestión de datos \> Entidades de datos**.
    
    2. Seleccione la entidad **Proveedores V2**.
    
    3. Haga clic en **Opciones** en la barra de menú, y luego **Seguimiento de cambios**.
    
        ![Autorreferencia o referencia circular 5](media/selfref_options.png)
    
    4. Haga clic en **Deshabilitar seguimiento de cambios**.
    
        ![Autorreferencia o referencia circular 6](media/selfref_tracking.png)

3. Ejecute la sincronización inicial de mapeo de **Proveedores V2 (msdyn_vendors)**. La sincronización inicial debe ejecutarse correctamente sin ningún error.

4. Ejecute la sincronización inicial para el mapeo **Contactos CDS V2 (contactos)**. Debe sincronizar esta asignación si desea sincronizar el campo de contacto principal en la entidad del proveedor, ya que los registros de contactos también deben sincronizarse inicialmente.

5. Agregue los campos **PrimaryContactPersonId** e **InvoiceVendorAccountNumber** de vuelta al mapeo **Proveedores V2 (msdyn_vendors)** y guarde el mapeo.

6. Ejecute de nuevo la sincronización inicial para el mapeo **Proveedores V2 (msdyn_vendors)**. Todos los registros se sincronizarán porque el seguimiento de cambios está deshabilitado.

7. Habilite el seguimiento de cambios para la entidad **Proveedores V2**.

## <a name="resolve-an-error-in-customers-v3-to-accounts-entity-mapping"></a><a id="error-customer-map"></a>Resolver un error en la asignación de entidades Clientes V3 a Cuentas

Puede encontrar los siguientes errores de sincronización inicial en el mapeo **Clientes V3** con **Cuentas** si las entidades tienen registros existentes con valores en los campos **ContactPersonID** e **InvoiceAccount**. Esto se debe a que **InvoiceAccount** es un campo de autorreferencia y **ContactPersonID** es una referencia circular en el mapeo del proveedor.

*No se pudo resolver el guid para el campo: <field> . No se encontró la búsqueda: <value> . Pruebe estas URL para verificar si los datos de referencia existen: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>*

- *No se pudo resolver el guid para el campo: primarycontactid.msdyn_contactpersonid. No se encontró la búsqueda: 000056. Pruebe estas URL para verificar si los datos de referencia existen: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*
- *No se pudo resolver el guid para el campo: msdyn_billingaccount.accountnumber. No se encontró la búsqueda: 1206-1. Pruebe estas URL para verificar si los datos de referencia existen: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'*

Si tiene registros con valores en estos campos en la entidad del cliente, siga los pasos de la sección a continuación para completar la sincronización inicial con éxito. Puede usar este enfoque para cualquier entidad lista para usar como Cuentas y Contactos.

1. En la aplicación Finance and Operations, elimine los campos **ContactPersonId** e **InvoiceAccount** del mapeo **Customers V3 (cuentas)** y guarde el mapeo.

    1. Navegue a la página de mapeo de doble escritura para **Proveedores V3 (cuentass)** y seleccione la pestaña **Mapeos de entidades**. En el filtro izquierdo, seleccione **Aplicación Finance and Operations.Proveedores V3**. En el filtro derecho, seleccione **Common Data Service.Account**.

    2. Busque **contactperson** para encontrar el campo de origen **ContactPersonID**.
    
    3. Haga clic en el botón **Accionees** y seleccione **Eliminar**.
    
        ![Autorreferencia o referencia circular 3](media/cust_selfref3.png)
    
    4. Repita para eliminar el campo **InvoiceAccount**.
    
        ![Autorreferencia o referencia circular](media/cust_selfref4.png)
    
    5. Guardar los cambios de mapeo.

2. Deshabilite el seguimiento de cambios para la entidad **Clientes V3**.

    1. Navegue a **Gestión de datos \> Entidades de datos**.
    
    2. Seleccione la entidad **Clientes V3**.
    
    3. Haga clic en **Opciones** en la barra de menú, y luego **Seguimiento de cambios**.
    
        ![Autorreferencia o referencia circular 5](media/selfref_options.png)
    
    4. Haga clic en **Deshabilitar seguimiento de cambios**.
    
        ![Autorreferencia o referencia circular 6](media/selfref_tracking.png)

3. Ejecute la sincronización inicial para el mapeo **Clientes V3 (Cuentas)**. La sincronización inicial debe ejecutarse correctamente sin ningún error.

4. Ejecute la sincronización inicial para el mapeo **Contactos CDS V2 (contactos)**. Hay 2 mapas con el mismo nombre. Seleccione el que tenga la descripción **Plantilla de doble escritura para sincronización entre Contactos de proveedor FO.CDS V2 con CDS.Contacts. Requiere nuevo paquete \[Dynamics365SupplyChainExtended\].** en la pestaña **Detalles** del mapa.

5. Agregue los campos **InvoiceAccount** y **ContactPersonId** de vuelta al mapeo **Clientes V3 (Cuentas)** y guarde el mapeo. Ahora, tanto el campo **InvoiceAccount** como el campo **ContactPersonId** vuelven a ser parte del modo de sincronización en vivo. En el siguiente paso, completará la sincronización inicial para estos campos.

6. Ejecute otra vez la sincronización inicial para el mapeo **Clientes V3 (Cuentas)**. Debido a que el seguimiento de cambios está deshabilitado, ejecutar la sincronización sincronizará los datos para **InvoiceAccount** y **ContactPersonId** desde la aplicación Finance and Operations a Common Data Service.

7. Para sincronizar los datos para **InvoiceAccount** y **ContactPersonId** desde Common Data Service a Finance and Operations, utilice un proyecto de integración de datos.

    1. En Power Apps, cree un proyecto de integración de datos entre **Sales.Account** y las entidades **Aplicaciones de Finance and Operations.Clientes V3**. La dirección de datos debe ser de Common Data Service a la aplicación Finance and Operations.  Como **InvoiceAccount** es un nuevo atributo en doble escritura, es posible que desee omitir la sincronización inicial para este atributo. Para obtener más información, consulte [Integrar datos en Common Data Service](https://docs.microsoft.com/power-platform/admin/data-integrator).

        La siguiente imagen muestra un proyecto que actualiza **CustomerAccount** y **ContactPersonId**.

        ![Autorreferencia o referencia circular](media/cust_selfref6.png)

    2. Agregue los criterios de la empresa en el filtro del lado Common Data Service, porque solo los registros que coinciden con los criterios de filtro se actualizarán en la aplicación Finance and Operations. Para agregar un filtro, haga clic en el icono del filtro. En el cuadro de diálogo **Editar consulta** puede agregar una consulta de filtro como **_msdyn_company_value eq '\<guid\>'**. Si el icono de filtro no está presente, cree un ticket de soporte para solicitar al equipo de integración de datos que habilite la capacidad de filtro en su inquilino. Si no introduce una consulta de filtro para **_msdyn_company_value**, entonces todos los registros están sincronizados.

        ![Autorreferencia o referencia circular](media/cust_selfref7.png)

        Esto completa la sincronización inicial de los registros.

8. Habilite el seguimiento de cambios para la entidad **Clientes V3** en la aplicación Finance and Operations.

