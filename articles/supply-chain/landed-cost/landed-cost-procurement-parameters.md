---
title: Parámetros de adquisición y abastecimiento para el coste descargado
description: Este tema describe cómo configurar los parámetros de Adquisición y abastecimiento relevantes cuando utiliza el módulo Costo de entrega.
author: sherry-zheng
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SrmParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-09
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: cb41fc6477acb005912c735a691de6d1a659c020
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7569850"
---
# <a name="procurement-and-sourcing-parameters-for-landed-cost"></a>Parámetros de adquisición y abastecimiento para el coste descargado

[!include [banner](../../includes/banner.md)]

La página **Parámetros de adquisición y abastecimiento** tiene algunas configuraciones que son especialmente relevantes cuando usa el módulo **Coste de aterrizaje**. Utilice el cuadro de diálogo **Actualizar líneas de pedido** que se abre desde la página **Parámetros de adquisición y abastecimiento** para especificar si las líneas de la orden de compra deben actualizarse automáticamente cuando se realizan cambios en el encabezado de la orden de compra.

Para completar esta configuración de almacén, siga estos pasos.

1. Vaya a **Adquisición y abastecimiento \> Configuración \> Parámetros de adquisición y abastecimiento**.
1. Sobre la pestaña **General**, seleccione el enlace **Actualizar líneas de pedido**.
1. El cuadro de diálogo **Actualizar líneas de pedido** enumera los campos en el encabezado del pedido que también pueden aplicar actualizaciones automáticas a los campos relacionados en las líneas del pedido. Establezca cada campo de la lista en uno de los siguientes valores:

    - **Siempre** - Las líneas del pedido se actualizan automáticamente cuando se actualiza el encabezado del pedido.
    - **Nunca** - Las líneas del pedido nunca se actualizan automáticamente cuando se actualiza el encabezado del pedido.
    - **Inmediato** - Se le pedirá al usuario que seleccione si las líneas de pedido deben actualizarse.
