---
title: Cree y actualizar el horario comercial
description: En este tema se describe cómo crear y actualizar el horario comercial en Commerce Headquarters.
author: josaw1
ms.date: 7/30/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: Retail 10.0.1 update
ms.openlocfilehash: 703087f5311205e18b6b8f99b847b539770160b91574b12d505822c8e16ca96c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6770103"
---
# <a name="create-and-update-store-hours"></a>Cree y actualizar el horario comercial

[!include [banner](../../includes/banner.md)]

## <a name="overview"></a>Visión general

De un único lugar, los minoristas pueden crear, mantener y administrar el horario comercial para diferentes tiendas en regiones geográficas. El horario comercial se puede mostrar en los terminales de punto de venta (PDV). De esta manera, los cajeros pueden compartir el horario comercial con los clientes y ayudar mejor a los compradores que están interesados en el inventario de otras tiendas. El horario comercial también se puede imprimir en recibos, en caso de que los clientes deseen volver a la tienda más adelante.

Se pueden configurar varios horarios comerciales en distintos canales. Estos canales incluyen tiendas físicas, centros de llamadas, dispositivos móviles y sitios de comercio electrónico.

Si un cliente tiene un pedido de recogida en una tienda diferente, el cajero puede seleccionar las fechas en las que la recogida estará disponible en dicha tienda. La búsqueda de la tienda proporcionará una referencia a las fechas y horarios de la tienda. El cajero puede seleccionar una fecha y una ubicación, y también puede imprimir un recibo de recogida que incluya el horario comercial.

Esta función está disponible en las versiones 8.1.2 y posteriores de Microsoft Dynamics 365 Retail.

## <a name="configure-store-hours"></a>Configurar horario comercial

Siga estos pasos para configurar un horario comercial.

1. Vaya a **Retail y Commerce** \> **Configuración de canal** \> **Horario comercial**.
2. Seleccione **Nueva** para crear una nueva plantilla de horario comercial. Para usar una plantilla existente, seleccione la plantilla en el panel izquierdo.
3. En el cuadro de diálogo **Agregar intervalo**, defina el intervalo de fechas, el horario comercial y cualquier festivo que sea necesario.

    - Si el horario comercial no cambia, seleccione **Nunca termina** en el campo **Fecha de finalización**.
    - Si el horario comercial es para un mes, semana o día determinado, establezca las fechas adecuadas en los campos **Fecha de inicio** y **Fecha de finalización**.

    > [!NOTE]
    > Puede crear varias plantillas que tengan fechas de inicio y de finalización solapadas. De este modo, puede, por ejemplo, definir el horario comercial para las tiendas en distintas zonas horarias.

    ![Cuadro de diálogo Agregar rango.](../dev-itpro/media/Storehours1.png "Cuadro de diálogo Agregar rango")

4. Asocie la plantilla de horario comercial a las tiendas en la que se usará. En el cuadro de diálogo **Elegir nodos organizativos**, seleccione las tiendas, regiones y organizaciones a las que debe asociarse la plantilla.

    - Solo se puede asociar una plantilla de horario comercial a cada tienda.
    - Use los botones de flecha para seleccionar tiendas, regiones u organizaciones. El calendario estará disponible para las tiendas o grupos de tiendas, y será visible en el PDV como referencia.

    ![Cuadro de diálogo Elegir nodos organizativos.](../dev-itpro/media/Storehours2.png "Cuadro de diálogo Elegir nodos organizativos")

5. En la página **Programación de distribución**, ejecute los trabajos **1070** y **1090** para hacer que el horario comercial esté disponible en el PDV.

## <a name="add-store-hours-to-printed-receipts"></a>Agregar horario comercial a recibos impresos

Siga estos pasos para agregar un horario comercial a las recepciones de PDV impresos.

1. Abra el diseñador de recibos.
2. Seleccione **Pie de página** en la esquina inferior izquierda.
3. Arrastre el elemento **Horario comercial** desde el panel izquierdo al pie de página en la parte inferior de la plantilla de recibo.
4. Puede editar la etiqueta predeterminada en el elemento **Horario comercial** según necesite.
5. Guarde el recibo y cierre el diseñador de recibos.
6. En la página **Programación de distribución**, ejecute los trabajos **1070** y **1090**.
7. Inicie sesión en el PDV.
8. Complete una venta y seleccione imprimir un recibo.

Los recibos de PDV incluyen ahora el horario comercial. Si se incluyeron algunos festivos en la plantilla, estos se muestran en el recibo.

![Ejemplo de recibo.](../dev-itpro/media/Storehours3.png "Ejemplo de recibo")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]