---
title: Reabastecimiento
description: "En este tema se describen las estrategias de reabastecimiento que están disponibles para los almacenes que utilizan la funcionalidad disponible en Gestión de almacenes."
author: Mirzaab
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSReplenishmentTemplates
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 90043
ms.assetid: 49fa97eb-8e10-49a5-9261-1e393159f178
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 67e361aedf77166e01d9e7a5b9dcb19d08ea26bd
ms.openlocfilehash: 872fbe41ed8137c1e7bec24656d4f132e170ae7f
ms.contentlocale: es-es
ms.lasthandoff: 10/05/2017

---

# <a name="replenishment"></a>Reabastecimiento

[!include[banner](../includes/banner.md)]

En este tema se describen las estrategias de reabastecimiento que están disponibles para los almacenes que utilizan la funcionalidad disponible en Gestión de almacenes. La información de este tema no se aplica a la solución de almacenamiento que está disponible en Gestión de inventarios.

Las siguientes estrategias de reabastecimiento están disponibles:

- **Reabastecimiento de demanda de oleada**: esta estrategia crea el trabajo de reabastecimiento para los pedidos o las cargas de salida si el inventario no está disponible cuando la oleada crea el trabajo. Por ejemplo, el trabajo de reabastecimiento se puede crear si la cantidad necesaria para un pedido de ventas no está disponible cuando se procesa una oleada.
- **Reabastecimiento mínimo/máximo**: esta estrategia usa los límites de existencias mínimos y máximos para determinar cuándo se deben reabastecer las ubicaciones. Los criterios de artículo y ubicación definen el inventario que se evalúa para el reabastecimiento. Las plantillas de reabastecimiento mínimo/máximo son el mecanismo principal para mantener niveles óptimos en ubicaciones de picking. Con el fin de garantizar que hay suficiente inventario de frente de recogida disponible para satisfacer la demanda de oleada, puede utilizar el reabastecimiento de demanda como suplemento entre los ciclos de reabastecimiento mínimo o máximo.
- **Reabastecimiento de demanda de carga**: esta estrategia suma la demanda para varias cargas y crea el trabajo de reabastecimiento que es necesario para almacenar las ubicaciones de picking pertinentes. Esta estrategia ayuda a garantizar que las cargas que se crean se pueden seleccionar en el almacén tras su emisión.
- **Reabastecimiento inmediato**: esta estrategia reaprovisiona el inventario antes de que ejecutar una oleada si falla la asignación de una línea de directiva de ubicación que tenga una plantilla de reabastecimiento. 

Las cuatro estrategias crean trabajo de reabastecimiento, en función de una plantilla de reabastecimiento.

## <a name="wave-demand-replenishment"></a>Reabastecimiento de la demanda de oleada
El reabastecimiento de demanda de oleada crea el trabajo de reabastecimiento, basado en demanda, si la cantidad necesaria para los pedidos de producción, kanbans, pedidos o cargas de salida no está disponible cuando la oleada crea el trabajo. La plantilla de reabastecimiento contiene información sobre los criterios del artículo, la unidad de medida, el incremento de la demanda y la ubicación. 

Las directivas de ubicación se utilizan para determinar qué ubicación se debe reabastecer. Vincula estas directivas de ubicación a la plantilla de reabastecimiento mediante el campo **Código de directiva**. Si el campo **Código de directiva** no está establecido, las consultas se utilizan para determinar qué directiva de ubicación se debe utilizar. Tenga en cuenta que si no se especifica un código de directiva en la plantilla de reabastecimiento y la directiva de ubicación tiene un código de directiva, se omitirá la directiva de ubicación, incluso si la consulta sobre la directiva de ubicación es correcta. Las directivas de ubicación de picking se utilizan para determinar dónde obtener inventario para el reabastecimiento. 

Además de crear una plantilla, debe especificar algunos valores de reabastecimiento en la plantilla de oleada. La plantilla de oleada debe contener un paso de oleada para el reabastecimiento que solo se ejecuta si la asignación de un artículo no es correcta. Este paso de oleada de reabastecimiento utiliza un código de paso de oleada para determinar qué plantilla de reabastecimiento debe utilizarse. Además de tener un paso de oleada para el reabastecimiento, debe asegurarse de que la opción **Reabastecer** está seleccionada en la sección **Métodos** de la plantilla de oleada. 

La página **Plantilla de reabastecimiento** incluye una casilla **Permitir una demanda de oleadas para usar las cantidades que no estén reservadas**. Seleccione esta casilla si desea permitir que el reabastecimiento de la demanda deduzca cantidades sin reservas del trabajo que se genera a partir de la plantilla de reabastecimiento seleccionada. Para que las plantillas de reabastecimiento de la demanda puedan usar esta lógica, seleccione esta casilla para cada plantilla de reabastecimiento existente. Cuando el reabastecimiento de la demanda se active en el almacén, deducirá la demanda del trabajo de reabastecimiento existente con cantidades sin reservas, si el trabajo se origina a partir de plantillas de reabastecimiento donde la casilla **Permitir que la demanda de oleada use cantidades sin reservas** está activada.

El reabastecimiento de la demanda se admite para los pedidos de ventas, pedidos de transferencia, pedidos de producción y kanbans. 

## <a name="minmax-replenishment"></a>Reabastecimiento mínimo/máximo
En el reabastecimiento mínimo/máximo, las existencias se reabastecen para que se encuentren entre los límites mínimo y máximo que se han establecido. Normalmente, este proceso se produce una vez al día para ayudar a garantizar que todas las ubicaciones de selección se rellenan hasta el nivel máximo antes de que se inicie la selección. 

Los importes mínimo y máximo se establecen en una plantilla de reabastecimiento. Muchos de los demás valores de la plantilla son similares a la configuración de las plantillas que se utilizan en el reabastecimiento de la demanda de oleada. La plantilla debe contener una línea para cada artículo y ubicación. Cuando ejecute el reabastecimiento mediante el trabajo por lotes, Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, evalúa si el reabastecimiento es necesario mediante la secuencia en la que se organizan las líneas. 

Tenga en cuenta que la estrategia de reabastecimiento mínima/máxima no puede reabastecer una ubicación vacía a menos que la ubicación se establezca como la ubicación fija para el artículo. Si la ubicación que debe reabastecerse no es una ubicación fija, el sistema no puede determinar qué artículo debe reabastecerse. Por tanto, se requiere al menos alguna cantidad disponible para que se produzca el reabastecimiento.

## <a name="load-demand-replenishment"></a>Reabastecimiento de la demanda de la carga
El reabastecimiento de demanda de carga suma la demanda para varias cargas y crea el trabajo de reabastecimiento que es necesario para almacenar las ubicaciones de picking pertinentes. El reabastecimiento de demanda de carga es similar de muchas maneras al reabastecimiento de demanda de oleada. La diferencia principal es cómo y cuándo se ejecutan el reabastecimiento de la demanda de la carga y el reabastecimiento de la demanda de oleada. Como el reabastecimiento mínimo/máximo, el reabastecimiento de la demanda de carga se ejecuta mediante un trabajo por lotes. Para configurar el trabajo por lotes, en la página **Reabastecimiento de la demanda de la carga**, seleccione la plantilla de reabastecimiento que se va a usar y establezca una consulta de filtro para especificar qué cargas se usan para determinar la demanda. La consulta de ubicación define las ubicaciones de las que se restará cualquier cantidad disponible para satisfacer la demanda agregada de las cargas.

## <a name="immediate-replenishment"></a>Reabastecimiento inmediato
En lugar de tener que aumentar la demanda al final del proceso de asignación y realizar un reabastecimiento según la cantidad añadida, puede aplicar la estrategia de reabastecimiento inmediato. Al usar esta estrategia, el inventario puede reabastecerse inmediatamente después que se produzca un error en una línea de directiva de la ubicación. Por lo tanto, puede configurar el reabastecimiento de modo que esté limitado a unidades específicas y para que así utilice las cantidades que se establecieron en ubicaciones específicas.

## <a name="replenishment-prerequisites"></a>Requisitos previos de reabastecimiento
| Requisito previo            | Descripción |
|-------------------------|-------------|
| Artículo                    | El artículo se debe habilitar para procesos de administración de almacenes. |
| Almacén               | El almacén se debe habilitar para procesos de administración de almacenes. Para habilitar un almacén para procesos de administración de almacenes, en la página **Almacenes**, seleccione el almacén y, a continuación, seleccione la opción **Usar procesos de gestión de almacenes**. |
| Plantillas de reabastecimiento | Se debe configurar al menos una plantilla de reabastecimiento para el reabastecimiento mínimo/máximo, el reabastecimiento de la demanda de oleada o el reabastecimiento de la demanda de la carga. |
| Ubicaciones               | Se deben crear ubicaciones y conectarse a un perfil de ubicación. |
| Perfiles de ubicación       | Se requieren perfiles de ubicación para crear ubicaciones. |
| Directivas de ubicación     | Las directivas de ubicación son necesarias para guiar el trabajo a las ubicaciones donde se requiere reabastecimiento y a las ubicaciones desde donde se suministra el inventario. |
| Plantillas de trabajo          | Las plantillas de trabajo del tipo **Reabastecimiento** son necesarias para crear el trabajo de reabastecimiento para que el inventario se pueda mover a las ubicaciones deseadas. |

