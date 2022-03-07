---
title: Muestreo de artículos de gestión de calidad
description: Este tema describe cómo configurar el muestreo de artículos.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventItemSampling
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ae8bfd329ca0d7c30adcd93a759ee6bea7b76278
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022237"
---
# <a name="quality-management-item-sampling"></a>Muestreo de artículos de gestión de calidad

El muestreo de elementos se utiliza como parte de una asociación de calidad. Define la cantidad de inventario físico actual que debe inspeccionarse. El muestreo puede basarse en cantidades fijas, en un porcentaje o en una matrícula completa.

## <a name="set-up-item-sampling"></a>Configurar el muestreo de artículos

Siga estos pasos para configurar el muestreo de artícuos.

1. Vaya a **Gestión del inventario \> Configurar \> Control de calidad \> Muestreo de artículos**.
1. Seleccione **Nuevo**.
1. En el campo **Muestreo de artículos,** introduzca un valor.
1. En el campo **Descripción**, especifique un valor.
1. En el campo **Valor,** especifique un número. Este valor está relacionado con el valor de especificación de cantidad seleccionado en el campo adyacente.
1. En la sección **Proceso**, seleccione la casilla **Bloqueo completo** si se debe bloquear todo el lote o la cantidad de la línea de pedido si no se supera una prueba. Si esta casilla está desactivada, solo se bloquearán los artículos del pedido de calidad si no se supera una prueba.
1. Seleccione **Guardar**.
1. Cierre la página.

> [!NOTE]
> La característica *Gestión de calidad para procesos de almacén* proporciona capacidades de muestreo de elementos adicionales. Agrega un concepto de *ámbito de muestreo del artículo* y lle ofrece la capacidad de definir una matrícula completa como especificación de cantidad. Si ha activado esta función, vea [Gestión de calidad para procesos de almacén](quality-management-for-warehouses-processes.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
