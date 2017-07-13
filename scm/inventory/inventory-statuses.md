---
title: Estados de inventario
description: "Este artículo describe cómo puede usar los estados de inventario para clasificar y realizar un seguimiento del inventario."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResStorageDimensionGroup, WHSInventStatus
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 21331
ms.assetid: b35f495f-de4f-48a0-9d09-4d06781d7650
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: b3ec66c805d028c20f3d3f95e7af9d78252828c7
ms.contentlocale: es-es
ms.lasthandoff: 06/13/2017


---

# Estados de inventario
<a id="inventory-statuses" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Este artículo describe cómo puede usar los estados de inventario para clasificar y realizar un seguimiento del inventario.

Puede usar los estados de inventario para clasificar el inventario. A continuación, puede iniciar acciones adecuadas, como el reabastecimiento o el trabajo de ubicación. 

A continuación, se muestran algunos ejemplos de las maneras en que puede usar estados de inventario:

-   Crear estados de inventario para el inventario disponible, las transacciones de entrada y las transacciones de salida.
-   Especificar un estado de inventario predeterminado para transacciones de almacén.
-   Cambiar el estado de inventario de los artículos antes de su llegada, durante la llegada o cuando los artículos se ubican durante el movimiento de inventario.
-   Usar un estado de inventario para artículos de precios que se devuelven y planificar la cobertura de artículos durante la planificación maestra.

El estado de inventario es una de las dimensiones del grupo de dimensiones de almacenamiento. Los estados de inventario se pueden clasificar como disponibles o no disponibles, y puede usar el parámetro **Bloqueo del inventario** para bloquear los artículos que tienen un estado de inventario no disponible. Los artículos que tienen un estado bloqueado se consideran inventario físico y no se pueden usar en un pedido de producción, un pedido de ventas, un pedido de transferencia o una transacción de salida. 

Puede usar artículos de almacén que tengan estados de inventario disponible o no disponible para el trabajo de entrada. Por ejemplo, crea un estado disponible con el nombre **Listo**, un estado no disponible con el nombre **Dañado** y un estado bloqueado con el nombre **Bloqueado**. Cuando crea un pedido de compra para artículos recibidos o devueltos, si cualquier artículo está dañado o roto, puede cambiar el estado de inventario de esos artículos a **Dañado** en la línea de pedido de compra. Después de recibir estos artículos, el estado se establece automáticamente en **Bloqueado**. Si escanea los artículos dañados con un dispositivo móvil, Microsoft Dynamics 365 for Finance and Operations puede usar las directrices de ubicación y las plantillas de trabajo para mostrar información acerca de una ubicación apropiada o el intervalo de ubicaciones en las que puede ubicar esos artículos. Para los artículos devueltos, se crea un tipo de asunto de **Reserva** en la página **Transacciones de inventario**. 

Para el trabajo de salida, use artículos que tengan un estado de inventario de disponible. Si tiene artículos que tiene un estado de **Roto**, y la planificación maestra se ejecuta en estos artículos, se considera que faltan los artículos y el inventario se reabastece automáticamente. 

Una vez que configure estados de inventario, puede establecer el estado de inventario predeterminado para un sitio, artículo y almacén. También puede establecer un estado predeterminado para ventas, transferencia y pedidos de compra. El estado predeterminado para pedidos de ventas y el pedido de transferencia saliente no pueden tener la opción **Bloqueo del inventario** establecida en **Sí**. El estado de inventario que se hereda de la configuración predeterminada en un sitio, almacén, artículo, pedido de compra, pedido de transferencia o pedido de ventas se puede cambiarse mediante el dispositivo móvil, o en el pedido de compra, el pedido de ventas o la línea de pedido de transferencia. 

Para planificar la cobertura para artículos que tienen un estado de inventario disponible, seleccione la opción **Plan de cobertura por dimensión** para una dimensión de almacenamiento en la página **Grupos de dimensiones de almacenamiento**. Cuando abre el **Asistente para la cobertura de artículos**, los artículos que tienen un estado disponible aparecerán en la página **Estado**. Para crear una configuración de cobertura para estos artículos, seleccione el Id. de estado de inventario para los estados de inventario de disponible. Basándose en la configuración de cobertura, puede calcular los requisitos de artículo y la previsión de oferta y demanda de artículos disponibles durante la planificación maestra. No puede crear una configuración de cobertura para artículos que tenga un estado de inventario de bloqueado. Como alternativa, use la página **Cobertura de artículos** para crear o modificar los parámetros de cobertura de artículos.




