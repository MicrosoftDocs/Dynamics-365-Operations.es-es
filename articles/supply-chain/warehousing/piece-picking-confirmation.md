---
title: "Confirmación de picking de pieza"
description: "Este tema describe cómo configurar y aplicar la confirmación el picking de pieza desde un dispositivo móvil."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSRFAutoConfirm, WHSRFMenuItem
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 5ef9ab68c20ae095de03b0a0e05aa15ef5bf8a5d
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="piece-picking-confirmation"></a>Confirmación de picking de pieza

[!include [banner](../includes/banner.md)]

El picking de pieza le permite confirmar cada pieza de inventario con picking o trabajo de recuento en un dispositivo móvil. Para las selecciones, puede confirmar la cantidad de trabajo que se procesará hasta la cantidad especificada en el trabajo que desea seleccionar. Para el trabajo de recuento, puede digitalizar el inventario que está contando y hacer un seguimiento de la cantidad total.

Si habilita el piece picking, la confirmación del producto se selecciona automáticamente. Para las selecciones de tipo de trabajo, se habilita un número máximo de piezas. Esto le permite establecer un máximo número de elementos que se deben confirmar durante el proceso de trabajo. La cantidad máxima se basa en la unidad de trabajo actual que se está procesando. El tipo de trabajo de recuento no permite un máximo.

También puede utilizar la cantidad y la unidad de medida (UdM) asociada a un código de barras digitalizado. Esto funcionará para recibir flujos de entrada con matrículas mezcladas, artículos de pedidos de compra, artículos de pedidos de transferencia y artículos de flete. También funciona para el picking de pieza cuando la digitalización del código de barras agregará la cantidad al número total de piezas confirmados que se convierten entre la UdM en el código de barras y la unidad de trabajo. Si, al realizar el recuento la UdM en el código de barras, se confirma que la cantidad está permitida para el recuento en el grupo de la secuencia, la cantidad se agregará al recuento total.

## <a name="where-it-applies"></a>Dónde se aplica

El picking de piezas funciona para todos los trabajos de recuento y para la selección inicial en cualquier tipo de trabajo. El picking de piezas no se aplica si el artículo se controla mediante números de serie o si es una selección de producción o kanban de una ubicación de matrícula (LP) y el artículo se configura por etapas.

## <a name="set-up-piece-picking"></a>Configurar picking de piezas

1.  En un elemento de menú del dispositivo móvil, abra el formulario de configuración para la confirmación del trabajo: Gestión de almacenes > **Gestión de almacenes** > **Configuración** > **Dispositivo móvil** > **Elementos de menú del dispositivo móvil**. 
2. En el elemento de menú del dispositivo móvil, abra Configuración de la confirmación de trabajo.

Las siguientes opciones están disponibles para la selección cuando el tipo de trabajo es selección o el recuento.


|           Opción           |                                                                            Descripción                                                                            |
|----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Confirmación de picking de pieza | Disponible para los tipos de trabajo selección y recuento. La confirmación de producto se selecciona automáticamente. Permite confirmar cada pieza de inventario desde el dispositivo móvil. |
|  Número máximo de piezas  |                   Disponible para el trabajo de selección si la confirmación de picking de piezas está habilitada. Establece un límite en el número de piezas que debe confirmar.                   |


