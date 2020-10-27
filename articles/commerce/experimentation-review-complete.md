---
title: Promover una variación y completar un experimento
description: Este tema describe cómo promover una variación exitosa y completar un experimento en Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 2e011f10e908d6a2efe2e928fc5e0abc7659cb8b
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "3930280"
---
# <a name="promote-a-variation-and-complete-an-experiment"></a>Promover una variación y completar un experimento

Este tema describe cómo promover la variación que produjo los mejores resultados en su experimento y cómo completar el experimento. El siguiente diagrama muestra todos los pasos necesarios para configurar y ejecutar un experimento en un sitio web de comercio electrónico en Dynamics 365 Commerce. Los pasos adicionales se tratan en temas separados.

[ ![Recorrido del usuario de experimentación: revisar y completar](./media/experimentation_review_complete.svg) ](./media/experimentation_review_complete.svg#lightbox)

Después de que haya [ejecutado su experimento](experimentation-run-monitor.md) y recopilado datos suficientes para determinar qué variación desea utilizar en su sitio en vivo, promoverá la variación y finalizará el experimento.

## <a name="promote-a-variation"></a>Promocionar una variación
Utilice los datos y análisis relacionados con el experimento en el servicio de terceros para decidir qué variación produjo los mejores resultados. Para reemplazar el contenido actual en el sitio en vivo con la variación ganadora para que esté disponible para todos los usuarios de su sitio web, haga lo siguiente. 

1. Vaya a la pestaña **Experimentos** en el Creador de sitios y seleccione el experimento.
1. Seleccione **Experimento completo** en la barra superior.
1. En el menú del cuadro de diálogo **Completar el experimento**, seleccione **Revisar los datos del experimento**. Se abre el servicio de terceros donde puede validar las métricas y determinar qué variación se desempeñó mejor.
1. En el menú del cuadro de diálogo **Completar el experimento** en el creador de sitios, seleccione la variación ganadora y luego seleccione **Siguiente**.
1. Abra el servicio de terceros y detenga el experimento.
1. En el creador de sitios, seleccione **Completar** para sobrescribir la página en vivo original y publicar la variación ganadora para que esté disponible para todos los usuarios de su sitio web. 

> [!NOTE]
> Si elige mantener la página activa actual y no publicar una variación, seleccione **Volver a publicar la página original**.

## <a name="delete-your-experiment"></a>Eliminar el experimento
Si bien no es necesario que elimine un experimento completado en Commerce, puede optar por eliminarlo para ahorrar espacio o limpiar su espacio de trabajo. Para eliminar un experimento, haga lo siguiente.

1. Vaya a la pestaña **Experimentos** en el Creador de sitios y seleccione el experimento. 
    > [!NOTE]
    > Si el experimento aún está activo, detenga el experimento en el servicio de terceros antes de continuar.
1. Seleccione **Anular publicación** en la barra de comandos para eliminar el contenido de la variación del sitio en vivo.
1. Seleccione **Eliminar** en la barra de comandos para eliminar el experimento.

## <a name="previous-step"></a>Paso anterior
[Ejecutar y supervisar un experimento](experimentation-run-monitor.md)
