---
title: Movimiento de inventario con trabajo asociado en Gestión de almacenes
description: Este tema describe cómo configurar y aplicar la confirmación el picking de pieza desde un dispositivo móvil.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorker
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2aee3af8da6610c16fc2d98091bfa3f01f1bd0f5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436817"
---
# <a name="movement-of-inventory-with-associated-work-in-warehouse-management"></a>Movimiento de inventario con trabajo asociado en Gestión de almacenes

[!include [banner](../includes/banner.md)]

Si usa el movimiento de inventario, puede decidir que trabajadores de almacén podrán mover el inventario reservado. Este formulario proporciona una flexibilidad en los almacenes regulados donde puede decidir no permitir que un trabajador elija una nueva ubicación de picking para seleccionar trabajo que ya se creó. También permite que un administrador de almacén controle qué capacidades deben algunos trabajadores menos experimentados.

La flexibilidad para administrar las operaciones diarias de trabajadores de almacén puede ser útil en escenarios como estos:

## <a name="scenario-1"></a>Escenario 1
Una empresa tiene un área de recepción relativamente pequeña y está congestionada con pallets y cajas que deben colocarse. Un envío grande se espera en este día, por lo que el vendedor receptor decide desalojar el área de recepción moviendo algunos pallets a una área provisional de entrada secundaria.

## <a name="scenario-2"></a>Escenario 2
Un trabajador experimentado de almacén ve una oportunidad en un almacén de consolidar artículos en una ubicación en lugar de dividirlos tenerlos en 3 ubicaciones próximas con menor cantidad en cada una. El trabajador desea consolidar la cantidad moviendo artículos desde cada una de las ubicaciones a la misma ubicación y en la misma matrícula.

## <a name="scenario-3"></a>Escenario 3
Un pallet está en espera de envío en una ubicación provisional, como STAGE01, que está cerca de BAYDOOR01. Sin embargo, debido a un cambio de planes el camión se programa para su llegada a BAYDOOR04. El encargado de los envíos lo sabe y necesita garantizar que el camión no tenga que esperar para cargarse en STAGE01. El encargado de los envíos decide mover los artículos en este envío desde STAGE01 a STAGE04, que está más cerca del nuevo destino.

### <a name="current-limitations"></a>Limitaciones actuales

Las reservas de trabajo que puede mover se limitan al pedido de ventas, emisión de pedidos de transferencia, recibo de pedidos de transferencia, pedido de compra y trabajo de reabastecimiento.

Los artículos móviles se limitan para evitar la división de las líneas de trabajo. Esto significa que si tiene una línea de trabajo para 100 piezas de artículos A en la ubicación Loc1, no podrá mover sólo 30 piezas de artículos A de ahí a otra ubicación. Esto conduciría a una división de la línea de trabajo existente a 30 y 70, ya que las ubicaciones son ahora diferentes.

Para las situaciones provisionales, donde la matrícula desde la que mueve la mercancía o la matrícula a la que mueve la mercancías se establecen como Destino LP para un pedido de trabajo, solo se perite el movimiento de LP completo para no interrumpir el Destino LP.
Solo el movimiento ad hoc se admite actualmente. Esto significa que no podrá mover el inventario reservado a través del movimiento por los elementos de menú del dispositivo móvil de la plantilla.

### <a name="set-up-permission-to-move-reserved-inventory-for-individual-workers"></a>Configure el permiso para mover el inventario reservado para trabajadores individuales

Para el trabajador tenga permitido mover el inventario reservado, seleccione la casilla de verificación **Permitir el movimiento de inventario con trabajo asociado** en **Gestión de almacenes** > **Configuración** > **Trabajador**.  

### <a name="backported"></a>Transporte de paquetes entre versiones

Esta función también permite el transporte de paquetes entre versiones a Microsoft Dynamics AX 2012 R3 y estará disponible como parte de CU12.
También puede descargase de forma individual con el KB número 3192548. 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]