---
title: Reserva del mismo lote para un pedido de ventas
description: Este artículo explica cómo configurar un producto para permitir la reserva de inventario con un único lote de inventario.
author: omulvad
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, EcoResStorageDimensionGroup, EcoResTrackingDimensionGroup, InventBatch, InventModelGroup, PdsAskSameLotForm, PdsCustSellableDays
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 28911
ms.assetid: 5823d75e-f839-46dd-beb3-e09b79fc8aa4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2d6089d07b0f8bc1a36703b5b1c2f24af72770d5
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "309550"
---
# <a name="reserve-the-same-batch-for-a-sales-order"></a>Reserva del mismo lote para un pedido de ventas

[!include [banner](../includes/banner.md)]

Este artículo explica cómo configurar un producto para permitir la reserva de inventario con un único lote de inventario.

La reserva del mismo lote le permite reservar inventario de una línea del pedido de ventas de un único lote del inventario. Por ejemplo, un cliente que realiza un pedido de papel pintado puede solicitar que todo el pedido se abastezca desde el mismo lote para evitar incoherencias entre los rollos de papel. Para configurar un producto para usar la reserva del mismo lote, deben haberse activado los siguientes ajustes en el grupo de modelos de artículos, el grupo de dimensiones de seguimiento y el grupo de dimensiones de almacenamiento que se asigne al producto:

-   **Grupos de modelos de artículo**: el grupo de modelos de artículo debe tener los campos **Selección del mismo lote** y **Consolidar requisito** seleccionados en el grupo de campos **Reserva** para las directivas de inventario.
-   **Grupo de dimensiones de seguimiento**: este grupo debe tener el campo **Plan de cobertura por dimensión** seleccionado para el número de lote.
-   **Grupo de dimensiones de almacenamiento**: este grupo debe tener el campo **Plan de cobertura por dimensión** seleccionado para **Sitio** y **Almacén**.

Al reservar inventario para un producto en una línea de pedido de ventas configurada para la selección del mismo lote, Microsoft Dynamics 365 for Finance and Operations intenta reservar la cantidad pedida desde un único lote de inventario. También se tienen en cuenta los requisitos de atributo de lote específicos. Si la cantidad no se puede rellenar desde un único lote, aparecerá la página **Conflicto de reserva del mismo lote**. Esta página describe las emisiones y también las acciones que puede realizar para continuar con la reserva. Las siguientes condiciones podrían impedir la reserva del lote:

-   El código de disposición del lote tiene **Bloquear reserva** para las ventas marcado como **Bloqueado**.
-   El lote ha caducado según la fecha de vencimiento y los días para ventas al cliente aplicables. El artículo aún se podrá reservar si el grupo de modelos de artículo está controlado por fecha FEFO y se selecciona la fecha de consumo preferente como criterio de selección.
-   El lote no tiene suficientes días de vida útil restantes según la fecha de caducidad/consumo preferente y los días para ventas al cliente.




