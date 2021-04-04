---
title: Estados de inventario
description: Este artículo describe cómo puede usar los estados de inventario para clasificar y realizar un seguimiento del inventario.
author: MarkusFogelberg
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, WHSInventStatus, WHSWarehouseStatusChange
audience: Application User
ms.reviewer: kamaybac
ms.custom: 21331
ms.assetid: b35f495f-de4f-48a0-9d09-4d06781d7650
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0b5e693bc1c9f4b822543d812f722bc8ea9f7025
ms.sourcegitcommit: ee7a890e3e4ed6436898e5ab6eff309082a073f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "5476708"
---
# <a name="inventory-statuses"></a>Estados de inventario

[!include [banner](../includes/banner.md)]

Este artículo describe cómo puede usar los estados de inventario para clasificar y realizar un seguimiento del inventario.

## <a name="set-up-and-use-inventory-statuses"></a>Configurar y usar estados de inventario

Puede usar los estados de inventario para clasificar el inventario. A continuación, puede iniciar acciones adecuadas, como el reabastecimiento o el trabajo de ubicación.

A continuación, se muestran algunos ejemplos de las maneras en que puede usar estados de inventario:

- Crear estados de inventario para el inventario disponible, las transacciones de entrada y las transacciones de salida.
- Especificar un estado de inventario predeterminado para transacciones de almacén.
- Cambiar el estado de inventario de los artículos antes de su llegada, durante la llegada o cuando los artículos se ubican durante el movimiento de inventario.
- Usar un estado de inventario para artículos de precios que se devuelven y planificar la cobertura de artículos durante la planificación maestra.

El estado de inventario es una de las dimensiones del grupo de dimensiones de almacenamiento. Los estados de inventario se pueden clasificar como disponibles o no disponibles, y puede usar el parámetro **Bloqueo del inventario** para bloquear los artículos que tienen un estado de inventario no disponible. Los artículos que tienen un estado bloqueado se consideran inventario físico y no se pueden usar en un pedido de producción, un pedido de ventas, un pedido de transferencia o una transacción de salida.

Puede usar artículos de almacén que tengan estados de inventario disponible o no disponible para el trabajo de entrada. Por ejemplo, crea un estado disponible con el nombre *Listo*, un estado no disponible con el nombre *Dañado* y un estado bloqueado con el nombre *Bloqueado*. Cuando crea un pedido de compra para artículos recibidos o devueltos, si cualquier artículo está dañado o roto, puede cambiar el estado de inventario de esos artículos a *Dañado* en la línea de pedido de compra. Después de recibir estos artículos, el estado se establece automáticamente en *Bloqueado*. Si escanea los artículos dañados con un dispositivo móvil, Supply Chain Management puede usar los directorios de ubicación y las plantillas de trabajo para mostrar información acerca una ubicación apropiada o el intervalo de ubicaciones en las que puede ubicar esos artículos. Para los artículos devueltos, se crea un tipo de asunto de *Reserva* en la página **Transacciones de inventario**.

> [!NOTE]
> No puede cambiar el estado del inventario en ubicaciones donde existe trabajo abierto. Por ejemplo, si realizó una recepción de compra para un artículo, pero no realizó el paso de almacenamiento, existirá trabajo abierto para la ubicación de recepción y obtendrá un error si intenta cambiar el estado del inventario en esa ubicación. Completar o cancelar el trabajo relacionado le permitiría cambiar el estado.
 
Para el trabajo de salida, use artículos que tengan un estado de inventario de disponible. Si tiene artículos que tiene un estado de *Roto*, y la planificación maestra se ejecuta en estos artículos, se considera que faltan los artículos y el inventario se reabastece automáticamente.

Una vez que configure estados de inventario, puede establecer el estado de inventario predeterminado para un sitio, artículo y almacén. También puede establecer un estado predeterminado para ventas, transferencia y pedidos de compra. El estado predeterminado para pedidos de ventas y el pedido de transferencia saliente no pueden tener la opción **Bloqueo del inventario** establecida en *Sí*. El estado de inventario que se hereda de la configuración predeterminada en un sitio, almacén, artículo, pedido de compra, pedido de transferencia o pedido de ventas se puede cambiarse mediante el dispositivo móvil, o en el pedido de compra, el pedido de ventas o la línea de pedido de transferencia.

Para planificar la cobertura para artículos que tienen un estado de inventario disponible, seleccione la opción **Plan de cobertura por dimensión** para una dimensión de almacenamiento en la página **Grupos de dimensiones de almacenamiento**. Cuando abre el **Asistente para la cobertura de artículos**, los artículos que tienen un estado disponible aparecerán en la página **Estado**. Para crear una configuración de cobertura para estos artículos, seleccione el Id. de estado de inventario para los estados de inventario de disponible. Basándose en la configuración de cobertura, puede calcular los requisitos de artículo y la previsión de oferta y demanda de artículos disponibles durante la planificación maestra. No puede crear una configuración de cobertura para artículos que tenga un estado de inventario de bloqueado. Como alternativa, use la página **Cobertura de artículos** para crear o modificar los parámetros de cobertura de artículos.

## <a name="change-inventory-statuses"></a>Cambiar estados de inventario

Puede cambiar los estados del inventario utilizando la página **Disponibles por ubicación** o utilizando la tarea periódica *Cambio de estado de inventario*.

- Al usar la tarea periódica *Cambio de estado de inventario*, puede seleccionar qué registros incluir y configurar la tarea para que se ejecute en el lote en el intervalo deseado.
- Para cambiar el estado del inventario como un proceso ad-hoc, vaya a la página **Disponibles por ubicación**, seleccione los registros relevantes y luego seleccione el botón **Cambio de estado de inventario**.

> [!NOTE]
> La función *Cambiar el estado del inventario de los artículos controlados por las dimensiones de seguimiento* le permite cambiar el estado del inventario de los artículos controlados por las dimensiones de seguimiento, incluida la capacidad de actualizar solo los registros seleccionados. Utilizar la [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para habilitar la función según sea necesario. Cuando la función esté habilitada, podrá hacer lo siguiente:
>
> - Sobre la página **Disponibles por ubicación**, puede agrupar líneas según las dimensiones mostradas mediante **Dimensiones de la pantalla** y cambie el estado de las líneas seleccionadas.
> - Sobre la paǵina **Disponibles por ubicación**, puede seleccionar varios registros y luego usar el botón **Cambio de estado de inventario** para cambiarlos todos a la vez.
> - En la tarea periódica **Cambio de estado de inventario** podrá filtrar siguiendo las dimensiones.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
