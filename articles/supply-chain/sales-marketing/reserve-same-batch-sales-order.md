---
title: Reserva del mismo lote para un pedido de ventas
description: Este artículo explica cómo configurar un producto para permitir la reserva de inventario con un único lote de inventario.
author: omulvad
manager: tfehr
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, EcoResStorageDimensionGroup, EcoResTrackingDimensionGroup, InventBatch, InventModelGroup, PdsAskSameLotForm, PdsCustSellableDays, WHSReservationHierarchy, WHSInventTableReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 28911
ms.assetid: 5823d75e-f839-46dd-beb3-e09b79fc8aa4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ce750745d6f094a296b43827568ee1745179de2d
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "4017285"
---
# <a name="reserve-the-same-batch-for-a-sales-order"></a>Reserva del mismo lote para un pedido de ventas

[!include [banner](../includes/banner.md)]

Este artículo explica cómo configurar un producto para permitir la reserva de inventario con un único lote de inventario.

La reserva del mismo lote le permite reservar inventario de una línea del pedido de ventas de un único lote del inventario. Por ejemplo, un cliente que realiza un pedido de papel pintado puede solicitar que todo el pedido se abastezca desde el mismo lote para evitar incoherencias entre los rollos de papel. Para configurar un producto para usar la reserva del mismo lote, deben haberse activado los siguientes ajustes en el grupo de modelos de artículos, el grupo de dimensiones de seguimiento y el grupo de dimensiones de almacenamiento que se asigne al producto:

- **Grupos de modelos de artículo** : el grupo de modelos de artículo debe tener los campos **Selección del mismo lote** y **Consolidar requisito** seleccionados en el grupo de campos **Reserva** para las directivas de inventario.
- **Grupo de dimensiones de seguimiento** : este grupo debe tener el campo **Plan de cobertura por dimensión** seleccionado para el número de lote.
- **Grupo de dimensiones de almacenamiento** : este grupo debe tener el campo **Plan de cobertura por dimensión** seleccionado para **Sitio** y **Almacén**.

Al reservar inventario para un producto en una línea de pedido de ventas configurada para la selección del mismo lote, el sistema intenta reservar la cantidad pedida desde un único lote de inventario. También se tienen en cuenta los requisitos de atributo de lote específicos. Si la cantidad no se puede rellenar desde un único lote, aparecerá la página **Conflicto de reserva del mismo lote**. Esta página describe las emisiones y también las acciones que puede realizar para continuar con la reserva. Las siguientes condiciones podrían impedir la reserva del lote:

- El código de disposición del lote tiene **Bloquear reserva** para las ventas marcado como **Bloqueado**.
- El lote ha caducado según la fecha de vencimiento y los días para ventas al cliente aplicables. El artículo aún se podrá reservar si el grupo de modelos de artículo está controlado por fecha FEFO y se selecciona la fecha de consumo preferente como criterio de selección.
- El lote no tiene suficientes días de vida útil restantes según la fecha de caducidad/consumo preferente y los días para ventas al cliente.

Para los elementos asociados con un grupo de dimensiones de almacenamiento que tiene **Utilizar procesos de gestión de almacenes** habilitado, puede reservar números de lote específicos utilizando una jerarquía de reserva con la dimensión de inventario de número de lote definida arriba de la dimensión de ubicación. La página **Reserva de lotes** de ventas y líneas de pedido de transferencia también le permite seleccionar y reservar varias líneas en función de los números de lote disponibles. Para obtener más información sobre qué hacer si está utilizando una jerarquía de reservas que tiene la dimensión del número de lote debajo de la ubicación, vea [Política de reserva de dimensión de nivel de almacén flexible](../warehousing/flexible-warehouse-level-dimension-reservation.md).
