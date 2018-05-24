---
title: "Órdenes de cuarentena"
description: "Este tema describe cómo se usan los pedidos de cuarentena para bloquear el inventario."
author: perlynne
manager: AnnBe
ms.date: 11/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventLocation, InventModelGroup, InventQuarantineOrder, InventQuarantineParmEnd, InventQuarantineParmReportFinished, InventQuarantineParmStartUp, InventTrans
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 30021
ms.assetid: d5047727-653c-49da-b489-6fd3fe50445e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 9a05c35d2e4a9e3ad81421eac863d182e8a6b499
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---

# <a name="quarantine-orders"></a>Órdenes de cuarentena

[!include [banner](../includes/banner.md)]

Este tema describe cómo se usan los pedidos de cuarentena para bloquear el inventario.

Los pedidos de cuarentena se pueden usar para bloquear el inventario. Por ejemplo, puede que desee poner en cuarentena los artículos por motivos de control de calidad. El inventario que se ha puesto en cuarentena se transfiere a un almacén de cuarentena. **Nota:** Si utiliza procesos avanzados de administración de almacenes (en Administración de almacenes), el procesamiento de pedidos en cuarentena solo se usa para los pedidos de ventas de devolución.

## <a name="quarantine-on-hand-inventory-items"></a>Poner en cuarentena artículos de inventario disponibles
Cuando ponga los artículos en cuarentena, puede crear órdenes de cuarentena manualmente o configurar el sistema para crear las órdenes de cuarentena automáticamente durante el proceso de entrada. Para crear órdenes de cuarentena automáticamente, seleccione la opción **Gestión de cuarentena** de la ficha **Directivas de inventario** de la página **Grupos de modelos de artículo**. También debe especificar el almacén de cuarentena predeterminado en el campo **Almacén de cuarentena** para los almacenes de recepción. Cuando el inventario disponible físicamente se registra en un pedido de compra o pedido de producción, los artículos en cuarentena se mueven automáticamente a un almacén de cuarentena en Microsoft Dynamics 365 for Finance and Operations. Este movimiento se produce porque el estado del pedido de cuarentena se cambia a **Iniciado**. Al crear órdenes de cuarentena manualmente, el artículo no se tiene que configurar para gestión de cuarentena en el grupo de modelos del artículo asociado. Para este proceso, debe especificar el inventario disponible que se debe poner en cuarentena y el almacén de cuarentena que se debe utilizar. Puede usar los estados de orden de cuarentena para ayudar a planear el proceso.

## <a name="quarantine-order-statuses"></a>Estados de la orden de cuarentena
Las órdenes de cuarentena pueden tener los siguientes estados:

-   Creado
-   Iniciado
-   Notificado como terminado
-   Finalizado

### <a name="created"></a>Creado

Cuando la orden de cuarentena se ha creado manualmente, pero el artículo aún no se ha colocado en un almacén de cuarentena, la orden de cuarentena recibe el estado de **Creado**. Se crean dos transacciones de inventario. Una transacción es una transacción de emisión que puede tener un estado de **En pedido**, **Reservado físicamente** o **Seleccionado**. La otra transacción es una transacción de recepción que puede tener un estado de **Pedido** o **Registrado** en el almacén de cuarentena. Puede reservar, seleccionar y registrar actualizaciones en el inventario mediante los procesos habituales.

### <a name="started"></a>Iniciado

Una vez que el pedido de cuarentena tenga un estado **Iniciado**, el inventario se transfiere del almacén habitual al almacén de cuarentena y se generan dos transacciones de inventario. Una transacción tiene el estado de **Descontada** y otra tiene un estado de **Recibida**. Al mismo tiempo, se crean dos transacciones de inventario para gestionar la transferencia de devolución. Estas transacciones no se fechan. Una transacción tiene el estado de **Reservado físicamente** y otra tiene un estado de **Pedida**.

### <a name="reported-as-finished"></a>Notificado como terminado

Al hacer clic en **Informe como finalizado**, puede notificar una orden de cuarentena iniciada como terminada. El artículo se libera desde la cuarentena aunque aún no se ha vuelto a trasladar al almacén habitual. El movimiento de vuelta al almacén habitual se puede procesar mediante un diario de recepción de artículos que se pueda inicializar durante el Informe como proceso terminado.

### <a name="ended"></a>Finalizado

Cuando se finaliza una orden de cuarentena, el artículo se traslada desde el almacén de cuarentena de nuevo al almacén habitual. El estado de la transacción de artículos se establece en **Vendido** en el almacén de cuarentena y en **Comprado** en el almacén de cuarentena.

## <a name="quarantine-order-scrap"></a>Eliminación de órdenes de cuarentena
Como parte del proceso de la orden de cuarentena, puede eliminar inventario. Al procesar el residuo, el estado del inventario se establecerá en **Vendido** por una transacción de emisión del almacén de cuarentena.

<a name="additional-resources"></a>Recursos adicionales
--------

[Bloqueo del inventario](inventory-blocking.md)

