---
title: Sincronice los productos de Finance and Operations con productos en Sales
description: En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar productos de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition a Microsoft Dynamics 365 for Sales.
author: ChristianRytt
manager: AnnBe
ms.date: 08/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 405a6cf9f3e6cc52925ff7d9f10836196343c36b
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-products-from-finance-and-operations-to-products-in-sales"></a>Sincronice los productos de Finance and Operations con productos en Sales

[!include[banner](../includes/banner.md)]

> [!NOTE]
> Para poder usar el cliente potencial para cobrar la solución, familiarícese con [Integración de datos de Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration). 

En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar productos de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition a Microsoft Dynamics 365 for Sales.

## <a name="template-and-task"></a>Plantilla y tarea

Las siguientes plantillas y tareas subyacentes que se usan para sincronizar productos de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (finanzas y operaciones) a Microsoft Dynamics 365 for Sales (ventas).

-   Nombre de la plantilla: Productos (Fin and Ops a Sales)

-   Nombre de la tarea en el proyecto: Productos

Tareas de sincronización requeridas antes de la sincronización del producto: Ninguna

## <a name="entity-set"></a>Conjunto de entidades

| **Finance and Operations** | **CDS** | **Ventas**  |
|----------------------------|---------|------------|
| Productos liberados para ventas | Producto | Productos   |

## <a name="entity-flow"></a>Flujo de la entidad

Los productos se administran en Finance and Operations y se sincronizan en Sales. La entidad de datos **Productos liberados para ventas** en Finance and Operations exporta solo los productos que son para ventas, lo que significa que los productos tienen la información necesaria para usarse en un pedido de ventas. Se aplican las mismas reglas cuando un producto se valida con la función **Validar** en la página **Producto emitido**.

El **Número de producto** se usa como clave, lo que significa que las variantes del producto se sincronizan con CDS y Sales con **Identificadores de producto** individuales por **Variante del producto**.

## <a name="prospect-to-cash-solution-for-sales"></a>Cliente potencial para cobrar la solución por Sales

En Sales, se agrega un campo nuevo en los productos **Mantenidos externamente** para indicar que un producto determinado se mantiene externamente. El valor se establece en **Sí** de forma predeterminada durante la importación a Sales.

-   **Mantenido externamente = Sí**: el producto se origina en Finance and Operatios y no se puede editar en Sales.

-   **Mantenido externamente = No**: el producto se introduce directamente en Sales.

-   **Mantenido externamente = En blanco**: el producto existe en Sales antes de habilitar solución Prospect to cash.

La información **Mantenido externamente** se usa para asegurarse que solo se sincronizarán **Presupuestos** y **Pedidos de ventas** con **Productos mantenidos externamente** con Finance and Operations.

Los **Productos mantenidos externamente** se agregan automáticamente a la primera **Lista de precios** válida con la misma divisa. Tenga en cuenta que la lista se organiza alfabéticamente por **Nombre**. El precio de venta del producto de Finance and Operations se usa como precio en la **Lista de precios**. Esto significa que es necesario tener una **Lista de precios** en Sales para cada **Divisa de ventas del producto** en Finance and Operations. La divisa en los productos liberados para ventas se establece en la divisa de contabilidad de la entidad jurídica, desde la que se exporta el producto.

> [!NOTE]
> La sincronización de productos no se realizará correctamente sin una **Lista de precios** con la divisa correspondiente.

## <a name="preconditions-and-mapping-setup"></a>Condiciones previas y configuración de asignación

-   Antes de ejecutar la primera sincronización, debe rellenar la **tabla de producto único** para los productos existentes en Finance and Operations. Los productos existentes no se sincronizarán hasta que este trabajo esté completado.

    -   En Finance and Operations, utilice Buscar para buscar **Rellenar tabla de producto único**.

    -   Haga clic en **Rellenar tabla de producto único** para ejecutar el trabajo. Este trabajo solo necesita ejecutarse una vez.

-   Asegúrese de que el **ValueMap** necesario para vender la **Unidad de medida** (U. de M.) en Finance and Operations existe en la asignación **Origen -\> CDS SalesUnitSymbol / DefaultSellingUnitOfMeasure**.

-   Actualice el **identificador de la organización de CDS Organization_OrganizationId** en **Origen -\> CDS** .

    -   El valor de plantilla se establece de forma predeterminada como ORG001.

-   Actualice **ValueMap** para el **Grupo de unidad** (**defaultuomscheduleid.name**) en **CDS -\> Destino** para que coincida con los **Grupos de unidad** en Sales.

    -   El valor de la plantilla se establece de forma predeterminada como **Unidad predeterminada**.

-   Asegúrese de que todos los productos que venden U. de M. desde Finance and Operations existen en Sales con el valor **Listas de selección de CDS** .

-   Asegúrese de que las **Listas de precios** existen en Sales para cada divisa de ventas del producto en Finance and Operations.

-   Los productos se pueden crear en Sales con el estado **Borrador** o **Activo**. Esto se controla en **Configuración del sistema** en **Ventas** en Sales.

    -   Los productos creados con estado de borrador tiene que activarse antes de que se puedan añadir a **Presupuesto** o **Pedido de ventas**.

## <a name="template-mapping-in-data-integrator"></a>Asignación de la plantilla en el integrador de datos

Las siguientes ilustraciones muestran un ejemplo de una asignación de plantilla en el integrador de los datos.

![asignación de la plantilla en el integrador de datos](./media/products-template-mapping-data-integrator-1.png)

![asignación de la plantilla para productos en el integrador de datos](./media/products-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a>Temas relacionados

[Sincronizar cuentas de Sales con clientes de Finance and Operations](accounts-template-mapping.md)

[Sincronizar contactos de Sales con contactos o clientes de Finance and Operations](contacts-template-mapping.md)

[Sincronizar encabezados y líneas de presupuesto de ventas de Sales con Finance and Operations](sales-quotation-template-mapping.md)

[Sincronizar encabezados y líneas de pedido de ventas de Finance and Operations en Sales](sales-order-template-mapping.md)

[Sincronizar encabezados y líneas de factura de Finance and Operations en Sales](sales-invoice-template-mapping.md)


