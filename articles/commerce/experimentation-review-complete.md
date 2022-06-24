---
title: Promover una variación y completar un experimento
description: Este artículo describe cómo promover una variación exitosa y completar un experimento en Dynamics 365 Commerce.
author: sushma-rao
ms.date: 06/07/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.openlocfilehash: 3e9a978551622bbb14d9213f607d9dfabe42672a
ms.sourcegitcommit: ddcb62bb5fbf26a1178c2bb1aec45a3d2362339e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2022
ms.locfileid: "8942752"
---
# <a name="promote-a-variation-and-complete-an-experiment"></a>Promover una variación y completar un experimento

Este artículo describe cómo promover la variación que produjo los mejores resultados en su experimento y cómo completar el experimento. El siguiente diagrama muestra todos los pasos necesarios para configurar y ejecutar un experimento en un sitio web de comercio electrónico en Dynamics 365 Commerce. Los pasos adicionales se tratan en artículos separados.

[ ![Recorrido del usuario de experimentación: revisar y completar.](./media/experimentation_review_complete.svg) ](./media/experimentation_review_complete.svg#lightbox)

Después de que haya [ejecutado su experimento](experimentation-run-monitor.md) y recopilado datos suficientes para determinar qué variación desea utilizar en su sitio en vivo, promoverá la variación y finalizará el experimento.

## <a name="promote-a-variation"></a>Promocionar una variación
Utilice los datos y análisis relacionados con el experimento en el servicio de terceros para decidir qué variación produjo los mejores resultados. Puede promocionarlo reemplazando el contenido actual en el sitio en vivo con la variación ganadora para que esté disponible para todos los usuarios de su sitio web.

Para promocionar la variación ganadora, siga estos pasos. 

1. En el generador de sitios de Commerce, vaya a la pestaña **Experimentos** del panel de navegación izquierdo y seleccione el experimento.
1. En la barra de comandos, seleccione **Experimento completo**.
1. En el cuadro de diálogo **Completar el experimento**, seleccione **Revisar los datos del experimento**. Se abre el servicio de terceros donde puede validar las métricas y determinar qué variación se desempeñó mejor.
1. En el menú del cuadro de diálogo **Completar el experimento**, seleccione la variación ganadora y, a continuación, seleccione **Siguiente**.
1. Abra el servicio de terceros y detenga el experimento.
1. En el creador de sitios, seleccione **Completar** para sobrescribir la página en vivo original y publicar la variación ganadora para que esté disponible para todos los usuarios de su sitio web. 

> [!NOTE]
> Si elige mantener la página activa actual y no publicar una variación, seleccione **Volver a publicar la página original**.

## <a name="delete-your-experiment"></a>Eliminar el experimento
Si bien no es necesario que elimine un experimento completado en Commerce, puede optar por eliminarlo para ahorrar espacio o limpiar su espacio de trabajo. 

Para eliminar un experimento completado en el generador de sitios de Commerce, siga estos pasos.

1. Seleccione **Experimentos** en el panel de navegación izquierdo y seleccione el experimento. 
    > [!NOTE]
    > Si el experimento aún está activo, detenga el experimento en el servicio de terceros antes de continuar.
1. En la barra de comandos, seleccione **Anular publicación** en la barra de comandos para eliminar el contenido de la variación del sitio en vivo.
1. Seleccione **Eliminar** para eliminar el experimento.

## <a name="previous-step"></a>Paso anterior
[Ejecutar y supervisar un experimento](experimentation-run-monitor.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
