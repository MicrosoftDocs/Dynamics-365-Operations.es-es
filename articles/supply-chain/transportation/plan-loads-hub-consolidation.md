---
title: Visión general del plan de cargas mediante la consolidación de concentrador
description: En este artículo se describe la característica de consolidación de envíos en un concentrador al entregar mercancías desde almacenes diferentes al mismo cliente, o cuando recibe mercancías de varios proveedores en el mismo almacén.
author: Weijiesa
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, WHSHistory, WHSLoadTable, WHSLoadPlanningListPage, TMSParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "92273"
- intro-internal
ms.assetid: d27b0926-a534-4caf-a2a3-acbc7c440bca
ms.search.region: Global
ms.search.industry: Distribution
ms.author: weijiesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 055d7c53b771e09002c84c643c45d3da9f71aca0
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "8676562"
---
# <a name="plan-loads-using-hub-consolidation-overview"></a>Visión general del plan de cargas mediante la consolidación de concentrador

[!include [banner](../includes/banner.md)]

En este artículo se describe la característica de consolidación de envíos en un concentrador al entregar mercancías desde almacenes diferentes al mismo cliente, o cuando recibe mercancías de varios proveedores en el mismo almacén.

Puede ser útil consolidar envíos en un concentrador al entregar mercancías desde almacenes diferentes al mismo cliente, o cuando se entregan mercancías de varios proveedores al mismo almacén.

## <a name="building-loads"></a>Creación de cargas
Para poder usar la consolidación de concentrador, debe habilitar la opción **Planificación de elementos en tránsito** en la página **Parámetros de administración de transporte**. También debe crear los concentradores donde se producirá la consolidación. El siguiente diagrama muestra un ejemplo de consolidación de concentrador. En este caso, los pedidos de ventas de diferentes almacenes van al mismo cliente. Las cargas básicas se crean en función de los pedidos de ventas de la forma habitual, usando la página **Área de trabajo de planificación de la carga**. Para consolidar las dos cargas en un concentrador antes de entregarse al cliente, en la página **Área de trabajo de planificación de la carga**, en el campo **Transporte**, seleccione **Consolidación de centros**. Cuando selecciona el concentrador correcto para cada carga, las cargas tendrán el concentrador como el destino de "entrega". También tendrá dos "líneas de solicitud de transporte" en la sección **Oferta y demanda** de la página **Área de trabajo de planificación de la carga**. A continuación, puede agregar estas dos líneas a una nueva carga. Esta nueva carga tendrá ambas líneas de pedido de ventas y también tendrá el concentrador como la dirección de "recogida" y el cliente A como el destino de "entrega". Las tres cargas estarán listas entonces para clasificarse y enrutarse como cualquier otra carga. Puede seleccionar cualquier transportista de envío que el sistema sugiera para cada carga. [![Consolidación de centros.](./media/hubconsol.jpg)](./media/hubconsol.jpg) También puede utilizar el mismo método para consolidar cargas para varios pedidos de transferencia. En este caso, el cliente A del diagrama anterior es un almacén. De forma alternativa, puede consolidar cargas para varios pedidos de compra, donde se entregan las cargas de diferentes proveedores al mismo almacén. Puede tener más de un concentrador de consolidación y consolidar en varios concentradores para más cargas que procedan de diferentes almacenes. Tras crear las cargas básicas y utilizar la opción de consolidación de concentrador, crea las cargas nuevas mediante las líneas de solicitud de transporte consolidadas. A continuación, clasifica y enruta las cargas.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]