---
title: Planificación de empresas vinculadas
description: Este tema describe la planificación de empresas vinculadas y explica cómo configurar la planificación de empresas vinculadas con Planning Optimization en Microsoft Dynamics 365 Supply Chain Management.
author: t-benebo
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: de9f9679bfaf9491c6b69c11448306627c8a42f9
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2022
ms.locfileid: "8468507"
---
# <a name="intercompany-planning"></a>Planificación de empresas vinculadas

[!include [banner](../../includes/banner.md)]

Para algunas organizaciones, las operaciones de logística dependen de otras entidades legales (empresas) en la organización. Estas operaciones se manejan mediante compras y ventas entre empresas, porque cada entidad jurídica tiene un plan de cuentas independiente.

Este tema describe la planificación de empresas vinculadas y explica cómo configurar la planificación de empresas vinculadas con Planning Optimization en Microsoft Dynamics 365 Supply Chain Management.

Este tema utiliza los siguientes términos importantes de empresas vinculadas:

- **Río arriba** - Una referencia relativa en una empresa o cadena de suministro. Indica movimiento en la dirección del proveedor de materia prima.
- **Flujo descendente** - Una referencia relativa en una empresa o cadena de suministro. Indica movimiento en la dirección del cliente.
- **Demanda intercompañía planificada** - Demanda planificada de un producto en una empresa, basada en la demanda planificada del producto de una empresa downstream.

En la planificación maestra, un plan en una empresa puede incluir la demanda intercompañía planificada que está relacionada con los pedidos planificados de un plan en otra empresa. Esta capacidad es útil porque proporciona una visibilidad completa de los pedidos planificados en todas las empresas. También garantiza que se creen todas las órdenes de suministro planificadas necesarias, pero sin requerir que las órdenes planificadas se firmen para la demanda de empresas vinculadas.

Si ejecuta la planificación maestra desde un plan maestro que incluye la demanda posterior planificada, las órdenes de compra planificadas de los proveedores de empresas vinculadas relacionados se incluirán en el plan como demanda.

## <a name="required-setup"></a>Configuración necesaria

Para utilizar la planificación de empresas vinculadas, debe preparar su sistema de la siguiente manera:

1. Los productos relevantes deben ser lanzados en todas las empresas relevantes. Para obtener más información, consulte [Configurar y usar el comercio de empresas vinculadas en Dynamics 365 Supply Chain Management](/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/) en Microsoft Learn.
1. La demanda aguas abajo debe cubrirse mediante compras a un proveedor que tenga una relación intercompañía con la compañía aguas arriba y dimensiones de inventario predeterminadas relevantes (sitio y almacén) en el cliente. Para obtener más información, consulte [Configurar y usar el comercio de empresas vinculadas en Dynamics 365 Supply Chain Management](/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/) en Microsoft Learn.
1. El plan maestro en la empresa aguas arriba debe incluir la demanda aguas abajo planificada, y la compañía relevante y el plan maestro deben especificarse en los planes aguas abajo.

## <a name="include-planned-downstream-demand"></a>Incluir demanda planificada descendente

Siga estos pasos para configurar su plan maestro de modo que incluya la demanda descendente planificada.

1. Vaya a **Planificación maestra \> Configurar \> Planes \> Planes maestros**.
1. Seleccionar o crear un plan maestro.
1. En la ficha desplegable **Planificación de empresas vinculadas**, establezca los siguientes campos:

    - **Incluya la demanda aguas abajo planificada** - Establezca esta opción en *Sí* para habilitar la planificación entre empresas para el plan maestro.
    - **Planes descendentes** - Si configura la opción **Incluya la demanda aguas abajo planificada** en *Sí*, use la barra de herramientas y la cuadrícula para agregar los planes maestros deseados de otras empresas.

## <a name="peg-across-companies-by-using-multilevel-pegging"></a>Vinculación entre empresas mediante vinculación multinivel

En la vinculación multinivel, puede ver la vinculación entre empresas para ver la fuente inicial de demanda que está siendo cubierta por una oferta.

Para ver información de trazabilidad multinivel, siga estos pasos.

1. Vaya a **Planificación maestra \> Planificación maestra \> Pedidos planificados**.
1. Seleccione o abra un pedido planificado.
1. En el panel de acciones, en la ficha **Ver**, en el grupo **Requisitos**, seleccione **Diagrama de árbol multinivel**.

### <a name="intercompany-example-that-involves-two-companies"></a>Ejemplo de intercompañía que involucra a dos empresas

Para este ejemplo, se crea una orden de producción planificada en la empresa USMF para cubrir una orden de venta en la empresa DEMF. En USMF, la demanda directa es la demanda intercompañía planificada. Para que esta demanda aparezca en USMF, la planificación maestra se ejecuta primero en DEMF y luego en USMF.

La siguiente ilustración muestra cómo podría aparecer este ejemplo en la página **Vinculación multinivel** de la orden de producción planificada.

![Ejemplo de intercompañía que involucra a dos empresas.](media/IntercompanyPlanning1.png)

### <a name="intercompany-example-that-involves-three-companies"></a>Ejemplo de intercompañía que involucra a tres empresas

Para este ejemplo, se crea una orden de compra planificada en la empresa USMF para cubrir una orden de venta en la empresa FRRT. En las empresas DEMF y USMF, la demanda directa es la demanda intercompañía planificada. Para que esta demanda aparezca en USMF, la planificación maestra se ejecuta primero en FRRT y finalmente en DEMF.

La siguiente ilustración muestra cómo podría aparecer este ejemplo en la página **Vinculación multinivel** de la orden de producción planificada.

![Ejemplo de intercompañía que involucra a tres empresas.](media/IntercompanyPlanning2.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]