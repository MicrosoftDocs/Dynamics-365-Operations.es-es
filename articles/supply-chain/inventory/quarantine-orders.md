---
title: Órdenes de cuarentena
description: Este tema describe cómo se usan los pedidos de cuarentena para bloquear inventario.
author: perlynne
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocation, InventModelGroup, InventQuarantineOrder, InventQuarantineParmEnd, InventQuarantineParmReportFinished, InventQuarantineParmStartUp, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30021
ms.assetid: d5047727-653c-49da-b489-6fd3fe50445e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5e1eed14b7d38cf569af7192dec9580e771f06df
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956191"
---
# <a name="quarantine-orders"></a>Órdenes de cuarentena

[!include [banner](../includes/banner.md)]

Este tema describe cómo se usan los pedidos de cuarentena para bloquear inventario.

Los pedidos de cuarentena le permiten bloquear inventario. Por ejemplo, puede que desee poner en cuarentena los artículos por motivos de control de calidad. El inventario que se ha puesto en cuarentena se transfiere a un almacén de cuarentena.

> [!NOTE]
> Si utiliza procesos avanzados de administración de almacenes (en Administración de almacenes), el procesamiento de pedidos en cuarentena solo se usa para los pedidos de ventas de devolución.

## <a name="quarantine-on-hand-inventory-items"></a>Poner en cuarentena artículos de inventario disponibles

Cuando ponga los artículos en cuarentena, puede crear órdenes de cuarentena manualmente o configurar el sistema para crearlas automáticamente durante el proceso de entrada.

Para configurar el sistema para que genere automáticamente pedidos de cuarentena, siga estos pasos.

1. Vaya a **Gestión del inventario \> Configurar \> Inventario \> Grupos de modelos de inventario**.
1. Seleccione un grupo de modelos relevantes en el pane de lista o cree un nuevo grupo de modelos.
1. En la ficha desplegable **Directivas de inventario**, seleccione la casilla **Gestión de cuarentenas**.
1. Cierre la página.
1. En el campo **Almacén de cuarentena** de los almacenes de recepción, especifique un almacén de cuarentena predeterminado.

Cuando un artículo registrado como recibido en el almacén pertenece a un grupo de modelos donde está seleccionada la casilla **Gestión de cuarentena**, el sistema genera una orden de cuarentena para él. El pedido de cuarentena indica a los trabajadores que muevan el artículo al almacén de cuarentena.

Al crear pedidos de cuarentena manualmente en la página **Pedidos de cuarentena**, el artículo no se tiene que configurar para gestión de cuarentena en el grupo de modelos del artículo asociado. Para este proceso, debe especificar el inventario disponible que se debe poner en cuarentena y el almacén de cuarentena que se debe utilizar. Puede usar los estados de orden de cuarentena para ayudar a planear el proceso.

## <a name="quarantine-order-statuses"></a>Estados de la orden de cuarentena

Las órdenes de cuarentena pueden tener los siguientes estados:

- Creado
- Iniciado
- Notificado como terminado
- Finalizado

### <a name="created"></a>Creado

Cuando la orden de cuarentena se ha creado manualmente, pero el artículo aún no se ha colocado en un almacén de cuarentena, la orden de cuarentena recibe el estado de **Creado**. Se crean dos transacciones de inventario. Una transacción es una transacción de emisión que puede tener un estado de **En pedido**, **Reservado físicamente** o **Seleccionado**. La otra transacción es una transacción de recepción que puede tener un estado de **Pedido** o **Registrado** en el almacén de cuarentena. Puede reservar, seleccionar y registrar actualizaciones en el inventario mediante los procesos habituales.

### <a name="started"></a>Iniciado

Una vez que el pedido de cuarentena tenga un estado **Iniciado**, el inventario se transfiere del almacén habitual al almacén de cuarentena y se generan dos transacciones de inventario. Una transacción tiene el estado de **Descontada** y otra tiene un estado de **Recibida**. Al mismo tiempo, se crean dos transacciones de inventario para gestionar la transferencia de devolución. Estas transacciones no se fechan. Una transacción tiene el estado de **Reservado físicamente** y otra tiene un estado de **Pedida**.

### <a name="reported-as-finished"></a>Notificado como terminado

Para informar de un pedido de cuarentena iniciado como finalizado, abra el pedido y seleccione **Informar como terminado** en el panel de acciones. El artículo se libera desde la cuarentena, aunque aún no se ha devuelto al almacén habitual. El movimiento de vuelta al almacén habitual se puede procesar mediante un diario de recepción de artículos que se pueda inicializar durante el informe como proceso terminado.

### <a name="ended"></a>Finalizado

Cuando se finaliza una orden de cuarentena, el artículo se traslada desde el almacén de cuarentena de nuevo al almacén habitual. El estado de la transacción de artículos se establece en *Vendido* en el almacén de cuarentena y en *Comprado* en el almacén de cuarentena.

## <a name="quarantine-order-scrap"></a>Eliminación de órdenes de cuarentena

Como parte del proceso de la orden de cuarentena, puede eliminar inventario. Al procesar la eliminación, el estado del inventario se establecerá en *Vendido* mediante una transacción de emisión del almacén de cuarentena.

## <a name="additional-resources"></a>Recursos adicionales

- [Bloqueo del inventario](inventory-blocking.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
