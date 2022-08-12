---
title: Solucionar problemas durante la sincronización
description: Este artículo proporciona información para la solución de problemas que puede ayudarlo a solucionar problemas durante la sincronización inicial.
author: RamaKrishnamoorthy
ms.date: 06/24/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: f8fb27a6af2962be31288a3d2260110e5fe6a201
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2022
ms.locfileid: "9112094"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a>Solucionar problemas durante la sincronización

[!include [banner](../../includes/banner.md)]



Este artículo proporciona información para solución de problemas de integración de escritura doble entre las aplicaciones de finanzas y operaciones y Dataverse. Específicamente proporciona información que puede ayudarlo a solucionar problemas durante la sincronización inicial.

> [!IMPORTANT]
> Algunos de los problemas que aborda este artículo pueden requerir la característica de administrador del sistema o Microsoft Azure Active Directory (Azure AD) credenciales de administrador de inquilinos. La sección para cada problema explica si se requiere una característica o credenciales específicas.

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a>Verificar los errores de sincronización inicial en una aplicación de finanzas y operaciones

Después de habilitar las plantillas de asignación, el estado de los mapas debe ser **Ejecutando**. Si el estado es **No ejecutando**, se produjeron errores durante la sincronización inicial. Para ver los errores, seleccione la pestaña **Detalles de sincronización inicial** en la página **Escritura doble**.

![Error en la pestaña Detalles de sincronización inicial.](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a>No puede completar la sincronización inicial: 400 Solicitud incorrecta

**Rol requerido para arreglar el error:** Administrador del sistema

Es posible que reciba el siguiente mensaje de error cuando intente ejecutar la asignación y la sincronización inicial:

*(\[Solicitud incorrecta\]: el servidor remoto devolvió un error: (400) Solicitud incorrecta.), se produjo un error en la exportación de AX*.

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

1. Inicie sesión en la máquina virtual (VM) para la aplicación de finanzas y operaciones.
2. Abra Microsoft Management Console.
3. En el panel **Servicios**, asegúrese de que el servicio de exportación de marco de Microsoft Dynamics 365 Data se está ejecutando. Reinícielo si se ha detenido, porque la sincronización inicial lo requiere.

## <a name="initial-synchronization-error-403-forbidden"></a>Error de sincronización inicial: 403 Prohibido

Es posible que reciba el siguiente mensaje de error durante la sincronización inicial:

*(\[Prohibido\], el servidor remoto devolvión un error: (403) Prohibido.), exportación AX encontró un error*

Para arreglar el problema, siga estos pasos.

1. Iniciar sesión en la aplicación de finanzas y operaciones.
2. En la págona **aplicaciones Azure Active Directory**, elimine el cliente **DtAppID**, y luego agréguelo nuevamente.

![Cliente DtAppID en la lista de aplicaciones de Azure AD.](media/aad_applications.png)

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

1. En la aplicación de finanzas y operaciones, elimine las columnas **PrimaryContactPersonId** e **InvoiceVendorAccountNumber** de la asignación y guarde la asignación.

    1. En la página de asignación de doble escritura para **Proveedores V2 (msdyn\_vendors)**, en la pestaña **Asignaciones de tablas**, en el filtro izquierdo, seleccione **Aplicaciones de finanzas y operaciones.Proveedores V2**. En el filtro derecho, seleccione **Sales.Vendor**.
    2. Busque **primarycontactperson** para encontrar la columna de origen **PrimaryContactPersonId**.
    3. Seleccione **Acciones** y luego seleccione **Eliminar**.

        ![Eliminar la columna PrimaryContactPersonId.](media/vend_selfref3.png)

    4. Repita estos pasos para eliminar la columna **InvoiceVendorAccountNumber**.

        ![Eliminar la columna InvoiceVendorAccountNumber.](media/vend-selfref4.png)

    5. Guardar los cambios en la asignación.

2. Active el seguimiento de cambios para la tabla **Proveedores V2**.

    1. En espacio de trabajo **Administración de datos**, seleccione la ventana **Tablas de datos**.
    2. Seleccione la tabla **Proveedores V2**.
    3. En el panel de acciones, seleccione **Opciones** y después seleccione **Change Tracking**.

        ![Seleccionar la opción Change Tracking.](media/selfref_options.png)

    4. Seleccione **Deshabilitar Change Tracking**.

        ![Seleccionar Deshabilitar Change Tracking.](media/selfref_tracking.png)

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

1. En la aplicación de finanzas y operaciones, elimine las columnas **ContactPersonId** e **InvoiceAccount** de la asignación **Clientes V3 (cuentas)** y guarde la asignación.

    1. En la página de mapeo de doble escritura para **Clientes V3 (cuentas)**, en la pestaña **Asignaciones de tablas**. En el filtro izquierdo, seleccione **Aplicaciones de finanzas y operaciones.Clientes V3**. En el filtro derecho, seleccione **Dataverse.Account**.
    2. Busque **contactperson** para encontrar la columna de origen **ContactPersonID**.
    3. Seleccione **Acciones** y luego seleccione **Eliminar**.

        ![Eliminar la columna ContactPersonID.](media/cust_selfref3.png)

    4. Repita estos pasos para eliminar la columna **InvoiceAccount**.

        ![Eliminar la columna InvoiceAccount.](media/cust_selfref4.png)

    5. Guardar los cambios en la asignación.

2. Desactive el seguimiento de cambios para la tabla **Clientes V3**.

    1. En espacio de trabajo **Administración de datos**, seleccione la ventana **Tablas de datos**.
    2. Seleccione la tabla **Clientes V3**.
    3. En el panel de acciones, seleccione **Opciones** y después seleccione **Change Tracking**.

        ![Seleccionar la opción Change Tracking.](media/selfref_options.png)

    4. Seleccione **Deshabilitar Change Tracking**.

        ![Seleccionar Deshabilitar Change Tracking.](media/selfref_tracking.png)

3. Ejecute otra vez la sincronización inicial para la asignación **Clientes V3 (Cuentas)**. La sincronización inicial debe ejecutarse correctamente sin ningún error.
4. Ejecute la sincronización inicial para la asignación **Contactos CDS V2 (contactos)**.

    > [!NOTE]
    > Hay dos asignaciones que tienen el mismo nombre. Asegúrese de seleccionar la asignación tenga la descripción siguiente en la pestaña **Detalles**: **Plantilla de doble escritura para sincronización entre Contactos de proveedor FO.CDS V2 con CDS.Contacts. Requiere nuevo paquete \[Dynamics365SupplyChainExtended\].**

5. Vuelva a agregar las columnas **InvoiceAccount** y **ContactPersonId** a la asignación **Clientes V3 (Cuentas)** y guarde la asignación. Tanto la columna **InvoiceAccount** como la columna **ContactPersonId** vuelven a ser parte del modo de sincronización en vivo. En el siguiente paso, completará la sincronización inicial para estas columnas.
6. Ejecute otra vez la sincronización inicial para la asignación **Clientes V3 (Cuentas)**. Debido a que el seguimiento de cambios está deshabilitado, los datos para **InvoiceAccount** y **ContactPersonId** se sincronizarán desde la aplicación de finanzas y operaciones a Dataverse.
7. Para sincronizar los datos para **InvoiceAccount** y **ContactPersonId** de Dataverse a la aplicación de finanzas y operaciones, debe utilizar un proyecto de integración de datos.

    1. En Power Apps, cree un proyecto de integración de datos entre **Sales.Account** y las tablas de **Aplicaciones de finanzas y operaciones.Clientes V3**. La dirección de datos debe ser de Dataverse a la aplicación de finanzas y operaciones. Como **InvoiceAccount** es un nuevo atributo en doble escritura, es posible que desee omitir la sincronización inicial para este atributo. Para obtener más información, consulte [Integrar datos en Dataverse](/power-platform/admin/data-integrator).

        La siguiente ilustración muestra un proyecto que actualiza **CustomerAccount** y **ContactPersonId**.

        ![Proyecto de integración de datos para actualizar CustomerAccount y ContactPersonId.](media/cust_selfref6.png)

    2. Agregue los criterios de la empresa en el filtro del lado de Dataverse, de forma que solo las filas que coinciden con los criterios de filtro se actualizarán en la aplicación de finanzas y operaciones. Para agregar un filtro, seleccione el botón del filtro. Posteriormente, en el cuadro de diálogo **Editar consulta** puede agregar una consulta de filtro como **\_msdyn\_company\_value eq '\<guid\>'**.

        > [NOTA] Si el botón del filtro no está presente, cree un ticket de soporte para solicitar al equipo de integración de datos que habilite la capacidad de filtro en su inquilino.

        Si no especifica una consulta de filtro para **\_msdyn\_company\_value**, entonces todas las filas se sincronizarán.

        ![Agregar una consulta de filtro.](media/cust_selfref7.png)

    La sincronización inicial de las filas ahora se ha completado.

8. En la aplicación de finanzas y operaciones, vuelva a activar Change Tracking en la tabla **Clientes V3**.

## <a name="initial-sync-failures-on-maps-with-more-than-10-lookup-fields"></a>Errores de sincronización inicial en asignaciones con más de 10 campos de búsqueda

Es posible que reciba el siguiente mensaje de error cuando intente ejecutar una sincronización inicial en asignaciones **Clientes V3 - Cuentas** y **Pedidos de venta**, o en cualquier asignación con más de 10 campos de búsqueda:

*CRMExport: ejecución del paquete finalizada. Descripción del error: Cinco intentos sin éxito de obtener datos de https://xxxxx//datasets/yyyyy/tables/accounts/items?$select=accountnumber, address2_city, address2_country, ... (msdyn_company/cdm_companyid eq 'id')&$orderby=accountnumber asc.*

Debido a la limitación de búsqueda en la consulta, se produce un error en la sincronización inicial cuando la asignación de entidad contiene más de 10 búsquedas. Para obtener más información, consulte [Recuperar registros de tabla relacionados con una consulta](/powerapps/developer/common-data-service/webapi/retrieve-related-entities-query).

Para solucionar este problema, siga estos pasos:

1. Quite los campos de búsqueda opcionales de la asignación de entidad de doble escritura para que el número de búsquedas sea 10 o menos.
2. Guarde la asignación y realice la sincronización inicial.
3. Cuando haya finalizado correctamente la sincronización inicial para el primer, agregue los campos de búsqueda restantes y quite los campos de búsqueda que sincronizó en el primer paso. Asegúrese de que el número de campos de búsqueda sea 10 o menos. Guarde la asignación y ejecute la sincronización inicial.
4. Repita estos pasos hasta que todos los campos de búsqueda estén sincronizados.
5. Vuelva a agregar todos los campos de búsqueda a la asignación, guarde la asignación y ejecútela con la opción **Omitir sincronización inicial** activada.

Este proceso habilita la asignación para el modo de sincronización en vivo.

## <a name="known-issue-during-initial-sync-of-party-postal-addresses-and-party-electronic-addresses"></a>Problema conocido durante la sincronización inicial de las direcciones postales de las partes y las direcciones electrónicas de las partes

Es posible que reciba el siguiente mensaje de error cuando intente ejecutar la sincronización inicial de las direcciones postales de las partes y las direcciones electrónicas de las partes:

*No se encontró el número de parte en Dataverse*.

Hay un rango establecido en **DirPartyCDSEntity** para aplicaciones de finanzas y operaciones que filtra grupos de tipo **Persona** y **Organización**. Como resultado, una sincronización inicial de la asignación **Partes de CDS - msdyn_parties** no sincronizará partes de otros tipos, como **Entidad jurídica** y **Unidad Operativa**. El error puede aparecer al ejecutar la sincronización inicial para **Direcciones postales de parte de CDS (msdyn_partypostaladdresses)** o **Contactos de parte V3 (msdyn_partyelectronicaddresses)**.

Estamos trabajando en una solución que elimine el rango de tipo de parte en la entidad de tablas de finanzas y operaciones para que las partes de todo tipo puedan sincronizarse correctamente con Dataverse.

## <a name="are-there-any-performance-issues-while-running-initial-sync-for-customers-or-contacts-data"></a>¿Hay algún problema de rendimiento al ejecutar la sincronización inicial para los datos de Clientes o Contactos?

Si ha ejecutado la sincronización inicial para datos de **Cliente** y tiene las asignaciones de **Cliente** en ejecución, y luego se ejecuta la sincronización inicial para datos de **Contactos**, puede haber problemas de rendimiento durante las inserciones y actualizaciones de las tablas **LogisticsPostalAddress** y **LogisticsElectronicAddress** para direcciones de **Contacto**. Se realiza un seguimiento de las mismas tablas de direcciones postales y direcciones electrónicas globales para **CustCustomerV3Entity** y **VendVendorV2Entity**, y la doble escritura intenta generar más consultas para escribir datos en el otro lado. Si ya ha ejecutado la sincronización inicial para **Cliente**, detenga la asignación correspondiente mientras ejecuta la sincronización inicial para datos de **Contactos**. Haga lo mismo para los datos de **Proveedor**. Una vez finalizada la sincronización inicial, podrá ejecutar todas las asignaciones omitiendo la sincronización inicial.

## <a name="float-data-type-that-has-a-zero-value-cant-be-synchronized"></a>El tipo de datos Float que tiene un valor cero no se puede sincronizar

La sincronización inicial puede fallar para los registros que tienen un valor cero para un campo de precio, como **Importe de pago fijo** o **Importe** en la moneda de la transacción. En este caso, recibirá un mensaje de error similar al siguiente ejemplo:

*Ocurrió un error al validar los parámetros de entrada: Microsoft.OData.ODataException: no se puede convertir el literal '000000' al tipo esperado 'Edm.Decimal',...*

El problema es con el valor **Idioma local** en **Formatos de datos de origen** en el módulo **Administración de datos**. Cambie el valor del campo **Idioma local** a **en-us** y, a continuación, inténtelo de nuevo.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

