---
title: Ejecutar y supervisar un experimento
description: Este tema describe cómo ejecutar y supervisar un experimento en un servicio de terceros. También describe cómo realizar cambios en las variaciones después de que comenzó el experimento.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 956a9168ed7bf9282d9eeec39587d8e1f2d1856c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5224891"
---
# <a name="run-and-monitor-an-experiment"></a>Ejecutar y supervisar un experimento

Este tema describe cómo ejecutar y supervisar su experimento en una aplicación de terceros y cómo cambiar las variaciones si es necesario. Antes de completar los pasos de este tema, deberá [publicar](experimentation-preview-publish.md) su experimento en Commerce. 

El siguiente diagrama muestra todos los pasos necesarios para configurar y ejecutar un experimento en un sitio web de comercio electrónico en Dynamics 365 Commerce. Los pasos adicionales se tratan en temas separados.

[ ![Recorrido del usuario de experimentación: ejecutar y supervisar](./media/experimentation_run_monitor.svg) ](./media/experimentation_run_monitor.svg#lightbox)

Después de publicar sus variaciones, habrá completado todos los pasos que debe seguir en Commerce para ejecutar su experimento. El siguiente paso es determinar qué variación mostrar a cada usuario cuando solicita una página. El servicio de terceros toma esa determinación, pero primero debe activar el experimento dentro del servicio. Dado que los pasos para activar un experimento varían de un servicio a otro, deberá seguir las instrucciones incluidas con su servicio o proveedor. Si el experimento no está activado, los usuarios solo verán la versión predeterminada de la página; no se mostrarán variaciones.

Deberá mantener el experimento en ejecución el tiempo suficiente para recopilar datos y obtener resultados estadísticamente válidos. Utilice el servicio de terceros para supervisar los datos y análisis relacionados con el experimento mientras se ejecuta el experimento.

## <a name="adjust-your-variations"></a>Ajustar sus variaciones
Si por alguna razón necesita modificar sus variaciones, siga los pasos a continuación.

> [!IMPORTANT]
> Si realiza cambios en un experimento en vivo en Commerce o en el servicio de terceros, sus resultados pueden verse afectados significativamente. Considere dejar que el experimento siga su curso y luego crear un nuevo experimento para cambios importantes.

1. En el generador de sitios de Commerce, vaya a la pestaña **Experimentos** del panel de navegación izquierdo y seleccione el experimento. 
1. Seleccione la variación que desea actualizar en el menú desplegable.
1. Realice los cambios necesarios y después obtenga una vista previa y publique las variaciones. Para más información, vea [Obtener la vista previa y publicar un experimento](experimentation-preview-publish.md).
1. Vaya al servicio de terceros para realizar cambios relacionados con la configuración del experimento.
    
## <a name="previous-step"></a>Paso anterior
[Obtener una vista previa y publicar un experimento](experimentation-preview-publish.md)

## <a name="next-step"></a>Paso siguiente
[Promover una variación y completar un experimento](experimentation-review-complete.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]