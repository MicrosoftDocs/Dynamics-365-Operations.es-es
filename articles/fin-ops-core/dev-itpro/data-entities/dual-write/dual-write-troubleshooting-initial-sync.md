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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: a2f0e0cbf0f8710dc020a48506775fa28df9c2d2
ms.sourcegitcommit: 7e1be696894731e1c58074d9b5e9c5b3acf7e52a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "4744646"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a>Solucionar problemas durante la sincronización

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tema proporciona información para solución de problemas de integración de escritura doble entre las aplicaciones de Finance and Operations y Dataverse. Específicamente proporciona información que puede ayudarlo a solucionar problemas durante la sincronización inicial.

> [!IMPORTANT]
> Algunos de los problemas que aborda este tema pueden requerir la característica de administrador del sistema o Microsoft Azure Active Directory (Azure AD) credenciales de administrador de inquilinos. La sección para cada problema explica si se requiere una característica o credenciales específicas.

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a>Verificar los errores de sincronización inicial en una aplicación Finance and Operations

Después de habilitar las plantillas de asignación, el estado de los mapas debe ser **Ejecutando**. Si el estado es **No ejecutando**, se produjeron errores durante la sincronización inicial. Para ver los errores, seleccione la pestaña **Detalles de sincronización inicial** en la página **Escritura doble**.

![Error en la pestaña Detalles de sincronización inicial](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a>No puede completar la sincronización inicial: 400 Solicitud incorrecta

**Rol requerido para arreglar el error:** Administrador del sistema

Es posible que reciba el siguiente mensaje de error cuando intente ejecutar la asignación y la sincronización inicial:

*(\[Solicitud incorrecta\]: el servidor remoto devolvió un error: (400) Solicitud incorrecta.), se produjo un error en la exportación de AX*

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

![Cliente DtAppID en la lista de aplicaciones de Azure AD](media/aad_applications.png)

## <a name="self-reference-or-circular-reference-failures-during-initial-synchronization"></a>Errores de autorreferencia o de referencia circular durante la sincronización inicial

Es posible que reciba mensajes de error si alguna de sus asignaciones tiene autorreferencias o referencias circulares. Los errores se dividen en estas categorías:

- [Errores en la asignación de tabla Proveedores V2–to–msdyn_vendors](#error-vendor-map)
- [Errores en la asignación de tabla Clientes V3–to–Accounts](#error-customer-map)

## <a name="resolve-errors-in-the-vendors-v2tomsdyn_vendors-table-mapping"></a><a id="error-vendor-map"></a>Resolver errores en la asignación de tabla Proveedores V2–to–msdyn_vendors

Puede encontrar los siguientes errores de sincronización inicial en la asignación de **Proveedores V2** a **msdyn\_vendors** si las tablas tienen filas existentes con valores en las columnas **PrimaryContactPersonId** e **InvoiceVendorAccountNumber**. Estos errores se producen porque **InvoiceVendorAccountNumber** es una columna de autorreferencia y **PrimaryContactPersonId** es una referencia circular en la asignación del proveedor.

Los mensajes de error que reciba tendrán el siguiente formulario.

*No se pudo resolver el guid para el campo: \<field\>. No se encontró la búsqueda: \<value\>. Pruebe estas URL para verificar si los datos de referencia existen: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*

A continuación, encontrará algunos ejemplos:

- *No se pudo resolver el guid para el campo: msdyn\_vendorprimarycontactperson.msdyn\_contactpersonid. No se encontró la busqueda: 000056. Pruebe estas URL para verificar si los datos de referencia existen: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*
- *No se pudo resolver el guid para el campo: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. No se encontró la búsqueda V24-1 . Pruebe estas URL para verificar si los datos de referencia existen: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'`*

Si tiene filas con valores en estos campos en la tabla del proveedor, en las columnas **PrimaryContactPersonId** e **InvoiceVendorAccountNumber** siga estos pasos para completar la sincronización inicial.

1. En la aplicación Finance and Operations, elimine las columnas **PrimaryContactPersonId** e **InvoiceVendorAccountNumber** de la asignación y guarde la asignación.

    1. En la página de asignación de doble escritura para **Proveedores V2 (msdyn\_vendors)**, en la pestaña **Asignaciones de tablas**, en el filtro izquierdo, seleccione **Finance and Operations apps.Vendors V2**. En el filtro derecho, seleccione **Sales.Vendor**.
    2. Busque **primarycontactperson** para encontrar la columna de origen **PrimaryContactPersonId**.
    3. Seleccione **Acciones** y luego seleccione **Eliminar**.

        ![Eliminar la columna PrimaryContactPersonId](media/vend_selfref3.png)

    4. Repita estos pasos para eliminar la columna **InvoiceVendorAccountNumber**.

        ![Eliminar la columna InvoiceVendorAccountNumber](media/vend-selfref4.png)

    5. Guardar los cambios en la asignación.

2. Active el seguimiento de cambios para la tabla **Proveedores V2**.

    1. En espacio de trabajo **Administración de datos**, seleccione la ventana **Tablas de datos**.
    2. Seleccione la tabla **Proveedores V2**.
    3. En el panel de acciones, seleccione **Opciones** y después seleccione **Change Tracking**.

        ![Seleccionar la opción Change Tracking](media/selfref_options.png)

    4. Seleccione **Deshabilitar Change Tracking**.

        ![Seleccionar Deshabilitar Change Tracking](media/selfref_tracking.png)

3. Ejecutar la sincronización inicial para la asignación de **Proveedores V2 (msdyn\_vendors)**. La sincronización inicial debe ejecutarse correctamente sin ningún error.
4. Ejecute la sincronización inicial para la asignación **Contactos CDS V2 (contactos)**. Debe sincronizar esta asignación si desea sincronizar la columna de contacto principal en la tabla proveedores, ya que la sincronización inicial también debe efectuarse para las filas de contactos.
5. Agregue las columnas **PrimaryContactPersonId** e **InvoiceVendorAccountNumber** otra vez a la asignación **Proveedores V2 (msdyn\_vendors)** y guarde la asignación.
6. Vuelva a ejecutar la sincronización inicial para la asignación de **Proveedores V2 (msdyn\_vendors)**. Dado que Change Tracking está desactivado, todas las filas se sincronizarán.
7. Vuelva a activar Change Tracking para la tabla **Proveedores V2**.

## <a name="resolve-errors-in-the-customers-v3toaccounts-table-mapping"></a><a id="error-customer-map"></a>Resolver errores en la asignación de tabla Clientes V3–to–Accounts

Puede encontrar los siguientes errores de sincronización inicial en la asignación de **Clientes V3** a **Cuentas** si las tablas tienen filas existentes con valores en las columnas **ContactPersonID** e **InvoiceAccount**. Estos errores se producen porque **InvoiceAccount** es una columna de autorreferencia y **ContactPersonID** es una referencia circular en la asignación del proveedor.

Los mensajes de error que reciba tendrán el siguiente formulario.

*No se pudo resolver el guid para el campo: \<field\>. No se encontró la búsqueda: \<value\>. Pruebe estas URL para verificar si los datos de referencia existen: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*

A continuación, encontrará algunos ejemplos:

- *No se pudo resolver el guid para el campo: primarycontactid.msdyn\_contactpersonid. No se encontró la busqueda: 000056. Pruebe estas URL para verificar si los datos de referencia existen: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*
- *No se pudo resolver el guid para el campo: msdyn\_billingaccount.accountnumber. No se encontró la búsqueda: 1206-1 . Pruebe estas URL para verificar si los datos de referencia existen: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'`*

Si tiene filas en la tabla del cliente con valores en las columnas **ContactPersonID** e **InvoiceAccount**, siga estos pasos para completar la sincronización inicial. Puede usar este enfoque para cualquier tabla lista para usar como **Cuentas** y **Contactos**.

1. En la aplicación Finance and Operations, elimine las columnas **ContactPersonId** e **InvoiceAccount** de la asignación **Clientes V3 (cuentas)** y guarde la asignación.

    1. En la página de mapeo de doble escritura para **Clientes V3 (cuentas)**, en la pestaña **Asignaciones de tablas**. En el filtro izquierdo, seleccione **Finance and Operations app.Customers V3**. En el filtro derecho, seleccione **Dataverse.Account**.
    2. Busque **contactperson** para encontrar la columna de origen **ContactPersonID**.
    3. Seleccione **Acciones** y luego seleccione **Eliminar**.

        ![Eliminar la columna ContactPersonID](media/cust_selfref3.png)

    4. Repita estos pasos para eliminar la columna **InvoiceAccount**.

        ![Eliminar la columna InvoiceAccount](media/cust_selfref4.png)

    5. Guardar los cambios en la asignación.

2. Desactive el seguimiento de cambios para la tabla **Clientes V3**.

    1. En espacio de trabajo **Administración de datos**, seleccione la ventana **Tablas de datos**.
    2. Seleccione la tabla **Clientes V3**.
    3. En el panel de acciones, seleccione **Opciones** y después seleccione **Change Tracking**.

        ![Seleccionar la opción Change Tracking](media/selfref_options.png)

    4. Seleccione **Deshabilitar Change Tracking**.

        ![Seleccionar Deshabilitar Change Tracking](media/selfref_tracking.png)

3. Ejecute otra vez la sincronización inicial para la asignación **Clientes V3 (Cuentas)**. La sincronización inicial debe ejecutarse correctamente sin ningún error.
4. Ejecute la sincronización inicial para la asignación **Contactos CDS V2 (contactos)**.

    > [!NOTE]
    > Hay dos asignaciones que tienen el mismo nombre. Asegúrese de seleccionar la asignación tenga la descripción siguiente en la pestaña **Detalles**: **Plantilla de doble escritura para sincronización entre Contactos de proveedor FO.CDS V2 con CDS.Contacts. Requiere nuevo paquete \[Dynamics365SupplyChainExtended\].**

5. Vuelva a agregar las columnas **InvoiceAccount** y **ContactPersonId** a la asignación **Clientes V3 (Cuentas)** y guarde la asignación. Tanto la columna **InvoiceAccount** como la columna **ContactPersonId** vuelven a ser parte del modo de sincronización en vivo. En el siguiente paso, completará la sincronización inicial para estas columnas.
6. Ejecute otra vez la sincronización inicial para la asignación **Clientes V3 (Cuentas)**. Debido a que el seguimiento de cambios está deshabilitado, los datos para **InvoiceAccount** y **ContactPersonId** se sincronizarán desde la aplicación Finance and Operations a Dataverse.
7. Para sincronizar los datos para **InvoiceAccount** y **ContactPersonId** desde Dataverse a la aplicación Finance and Operations, debe utilizar un proyecto de integración de datos.

    1. En Power Apps, cree un proyecto de integración de datos entre **Sales.Account** y las tablas **Finance and Operations.Customers V3**. La dirección de datos debe ser de Dataverse a la aplicación Finance and Operations. Como **InvoiceAccount** es un nuevo atributo en doble escritura, es posible que desee omitir la sincronización inicial para este atributo. Para obtener más información, consulte [Integrar datos en Dataverse](https://docs.microsoft.com/power-platform/admin/data-integrator).

        La siguiente ilustración muestra un proyecto que actualiza **CustomerAccount** y **ContactPersonId**.

        ![Proyecto de integración de datos para actualizar CustomerAccount y ContactPersonId](media/cust_selfref6.png)

    2. Agregue los criterios de la empresa en el filtro del lado Dataverse, de forma que solo las filas que coinciden con los criterios de filtro se actualizarán en la aplicación Finance and Operations. Para agregar un filtro, seleccione el botón del filtro. Posteriormente, en el cuadro de diálogo **Editar consulta** puede agregar una consulta de filtro como **\_msdyn\_company\_value eq '\<guid\>'**. 

        > [NOTA] Si el botón del filtro no está presente, cree un ticket de soporte para solicitar al equipo de integración de datos que habilite la capacidad de filtro en su inquilino.

        Si no especifica una consulta de filtro para **\_msdyn\_company\_value**, entonces todas las filas se sincronizarán.

        ![Agregar una consulta de filtro](media/cust_selfref7.png)

    La sincronización inicial de las filas ahora se ha completado.

8. En la aplicación Finance and Operations, vuelva a activar Change Tracking en la tabla **Clientes V3**.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]