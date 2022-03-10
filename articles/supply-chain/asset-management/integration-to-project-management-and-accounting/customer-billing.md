---
title: Facturar por mantenimiento de activos del cliente
description: Este tema explica cómo crear, procesar y facturar el trabajo de mantenimiento que se realiza sobre los activos que poseen sus clientes.
author: johanhoffmann
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProjProjectContractsListPage, ProjInvoiceTable, ProjProjectsListPage, ProjTable, EntAssetWorkOrderType, EntAssetWorkOrderProjectSetup, EntAssetObjectTable, EntAssetWorkOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: a48e681da1801ef3c0d1c9c03cebaa5eecd37d76349a7b1c3cfe53e892fae489
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6774954"
---
# <a name="bill-for-maintenance-on-customer-owned-assets"></a>Facturar por mantenimiento de activos del cliente

[!include [banner](../../includes/banner.md)]

La característica *Facturación de órdenes de trabajo* le permite crear, procesar y facturar el trabajo de mantenimiento que se realiza en los activos que poseen sus clientes. Esta característica le permite realizar las tareas siguientes:

- Conectar a los clientes con los activos que poseen.
- Seleccionar un cliente y ver los activos que posee cuando crea una orden de trabajo.
- Configurar un proyecto principal para cada cliente.
- Registrar horas, artículos, gastos y tarifas en la orden de trabajo y crear una propuesta de factura para el cliente más tarde.

Además, la función proporciona la siguiente funcionalidad:

- El contrato de proyecto del proyecto principal de un cliente se copia automáticamente en el proyecto de orden de trabajo relevante.
- La administración de activos ahora puede utilizar el tipo de transacción de proyecto *tarifa* tanto en las previsiones de órdenes de trabajo como en los diarios de órdenes de trabajo.

## <a name="turn-on-the-customer-billing-feature"></a>Activar la característica de facturación al cliente

Antes de poder usar esta característica debe estar activada en su sistema. Los administradores pueden usar la configuración de [gestión de funciones](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla. En el espacio de trabajo **Administración de funciones**, la función aparece de la siguiente forma:

- **Módulo:** *Gestión y contabilidad de proyectos*
- **Nombre de la característica:** *Facturación de órdenes de trabajo*

## <a name="example-scenario"></a>Supuesto de ejemplo

Para aprender cómo funciona esta característica, trabaje con el siguiente escenario de ejemplo.

Para trabajar en este escenario mediante el uso de los registros y valores de muestra que se especifican aquí, debe estar en un sistema donde estén instalados los [datos de demostración](../../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) estándar. Debe seleccionar la entidad legal **USMF** antes de comenzar.

También puede usar este escenario como guía para usar la característica cuando trabaje en un sistema de producción. Sin embargo, en ese caso, debe sustituir sus propios valores y puede que le falten algunos tipos de registros necesarios que proporcionan los datos de demostración estándar.

### <a name="step-1-create-a-new-project-contract-for-the-customer"></a>Paso 1: crear un nuevo contrato de proyecto para el cliente

1. Vaya a **Gestión de proyectos y contabilidad \> Proyectos \> Contratos de proyecto**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En el cuadro de diálogo **Nuevo contrato de proyecto**, establezca los valores siguientes:

    - **Nombre:** *Pelican Wholesales*
    - **Tipo de financiación:** *Cliente*
    - **Fuente de financiación:** *US-013* (*Pelican Wholesales*)

1. Seleccione **Aceptar**.

### <a name="step-2-create-a-new-parent-project-for-the-customer"></a>Paso 2: crear un nuevo proyecto principal para el cliente

El proyecto principal que cree aquí se utilizará cuando se creen las órdenes de trabajo para el cliente.

1. Vaya a **Gestión de proyectos y contabilidad \> Proyectos \> Todos los proyectos**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En el cuadro de diálogo **Nuevo proyecto**, establezca los valores siguientes:

    - **Tipo de proyecto:** *Tiempo y material*
    - **Nombre del proyecto:** *Órdenes de trabajo de Pelican Wholesales*
    - **Grupo de proyecto:** *TM*
    - **Id. del contrato del proyecto:** *Pelican Wholesales* (el contrato que creaste antes)
    - **Fecha de inicio:** seleccione la fecha de hoy.

1. Seleccione **Crear proyecto**.
1. El nuevo proyecto está abierto. Anote el valor **Id. del proyecto**. Tendrá que introducirlo más tarde.

### <a name="step-3-create-a-new-work-order-type-in-asset-management"></a>Paso 3: crear un nuevo tipo de orden de trabajo en la Administración de activos

1. Vaya a **Administración de activos \> Configuración \> Orden de trabajo \> Tipos de órdenes de trabajo**.
1. En el panel de acciones, haga clic en **Nueva**.
1. Se agrega un nuevo registro a la lista. Establezca los siguientes valores para este registro:

    - **Tipo de orden de trabajo:** *Servicio*
    - **Nombre:** *Órdenes de trabajo de servicios*
    - **Estado del ciclo de vida de la orden de trabajo:** *Estándar*

### <a name="step-4-link-the-customer-account-to-the-parent-project"></a>Paso 4: vincular la cuenta del cliente al proyecto principal

Ahora debe vincular la cuenta del cliente al proyecto principal en la configuración del proyecto en Administración de activos.

1. Vaya a **Administración de activos \> Configuración \> Órdenes de trabajo \> Configuración del proyecto**.
1. En la pestaña **Proyecto principal**, seleccione **Agregar** para agregar una línea.
1. En la nueva línea, establezca los siguientes valores:

    - **Cuenta de cliente:** *US-013* (*Pelican Wholesales*)
    - **Id. del proyecto:** introduzca el Id. del proyecto que anotó anteriormente.

### <a name="step-5-link-the-project-group-and-type-to-the-work-order-project"></a>Paso 5: vincular el grupo y tipo del proyecto al proyecto de la orden de trabajo

Todavía debería estar en la página de **Configuración del proyecto** (**Administración de activos \> Configuración \> Órdenes de trabajo \> Configuración del proyecto**).

1. En la pestaña **Grupo del proyecto**, seleccione **Agregar** para agregar una línea.
1. En la nueva línea, establezca los siguientes valores:

    - **Tipo de orden de trabajo:** *Servicio* (el tipo de orden de trabajo que creó anteriormente)
    - **Grupo de proyecto:** *TM*

> [!NOTE]
> El contrato del proyecto en el proyecto de la orden de trabajo siempre se hereda del proyecto principal.

### <a name="step-6-link-an-asset-to-the-customer-id"></a>Paso 6: vincular un activo al Id. de cliente

1. Vaya a **Administración de activos \> Activos \> Activos activos**.
1. En el campo **Filtrar**, introduzca *VE-102* y seleccione filtrar por **Activo**.
1. Seleccione el activo para abrir su configuración.
1. En la ficha desplegable **Cliente**, configure el campo **Cuenta de cliente** a *US-013* (*Pelican Wholesales*).

    El campo **Nombre** se actualiza automáticamente a *Pelican Wholesales*.

### <a name="step-7-create-a-new-work-order-on-the-asset"></a>Paso 7: crear una nueva orden de trabajo sobre el activo

1. Vaya a **Administración de activos \> Órdenes de trabajo \> Órdenes de trabajo activas**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En el cuadro de diálogo **Crear orden de trabajo**, establezca los siguientes valores:

    - **Tipo de orden de trabajo:** *Servicio*
    - **Descripción:** *Reparar camión*
    - **Cuenta de cliente:** *US-013* (*Pelican Wholesales*)
    - **Activo:** *VE-102*

        > [!NOTE]
        > La búsqueda muestra solo los activos que están vinculados a la cuenta de cliente seleccionada.

    - **Tipo de trabajo de mantenimiento:** *Reparación*
    - **Comercio:** *Mecánico*
    - **Nivel de servicio:** *4*

1. Seleccione **Aceptar**.

### <a name="step-8-review-the-work-order-and-start-to-work-on-it"></a>Paso 8: revisar la orden de trabajo y comenzar a trabajar en ella

En esta sección, trabajará en la orden de trabajo que creó en la sección anterior.

1. Siga estos pasos para verificar que el proyecto principal es el proyecto *Orden de trabajo de Pelican Wholesales*:

    1. En la sección **Trabajos de mantenimiento de orden de trabajo**, seleccione una línea.
    1. En la ficha desplegable **Detalles de línea**, inspeccione el valor **Id. de proyecto**. Debe ser un número con guion de la siguiente forma *\<Parent-Project-ID\>-\<Project-ID\>*. Este valor es un vínculo.
    1. Seleccione el vínculo del Id. del proyecto para abrir una página donde puede ver el proyecto principal y los nombres del proyecto.

1. En el panel de acciones, en la ficha **Orden de trabajo**, en el grupo **Estado de ciclo de vida**, seleccione **Actualizar el estado de la orden de trabajo**.
1. En el cuadro de diálogo **Actualizar el estado de la orden de trabajo**, en la columna **Seleccionar**, seleccione la casilla de la fila donde el campo **Estado de ciclo de vida** se encuentre *En curso*.
1. Seleccione **Aceptar**.
1. En el cuadro de diálogo **Estado de ciclo de vida: En curso**, seleccione **Aceptar**.

### <a name="step-9-post-the-hours-that-were-spent-on-the-work-order-and-create-a-new-invoice-proposal"></a>Paso 9: publicar las horas dedicadas a la orden de trabajo y crear una nueva propuesta de factura

En esta sección, seguirá trabajando en la orden de trabajo en la que trabajó en la sección anterior.

1. En el panel de acciones, en la ficha **Orden de trabajo**, en el grupo **Proyecto**, seleccione **Diarios**.

    Aparecerá la página **Diarios de órdenes de trabajo**. Aquí puede registrar el tiempo que dedicó a la orden de trabajo.

1. En la ficha desplegable **Horas**, seleccione **Agregar línea**.
1. En la nueva línea, establezca el campo **Horas** a *4*.
1. En el panel de acciones, seleccione **Registrar diarios**.
1. Cierra la página **Diarios de órdenes de trabajo** para volver a la orden de trabajo.
1. En el panel de acciones, en la pestaña **Facturación**, seleccione **Nueva propuesta de factura**.
1. En el cuadro de diálogo **Crear propuesta de factura**, en la sección **Transacciones de proyecto**, seleccione la casilla **Seleccionar** para todas las líneas que quiera facturar.
1. Seleccione **Aceptar** para cerrar el cuadro de diálogo y ver la nueva propuesta de factura.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]