---
title: Simular cambios de coste mediante una versión de gestión de costes para costes planificados
description: Este artículo explica cómo puede simular los efectos de los cambios de coste en los costes calculados de un artículo fabricado con una versión de gestión de costes independiente para los costes planificados.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostingVersion
audience: Application User
ms.reviewer: kamaybac
ms.custom: 78183
ms.assetid: 1e41953f-cdb9-4598-b776-46e49383a773
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 627c45a6cd7b647c0cb11ad4a4470bf143fff6cd
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5821474"
---
# <a name="simulate-cost-changes-by-using-a-costing-version-for-planned-costs"></a>Simular cambios de coste mediante una versión de gestión de costes para costes planificados

[!include [banner](../includes/banner.md)]

Este artículo explica cómo puede simular los efectos de los cambios de coste en los costes calculados de un artículo fabricado con una versión de gestión de costes independiente para los costes planificados.

Puede simular los efectos de los cambios de coste en los costes calculados de un artículo fabricado con una versión de gestión de costes independiente para los costes planificados. Use esta versión de gestión de costes independiente para especificar los registros de coste pendientes que reflejen los cambios de coste incrementales y para calcular el impacto del coste en los artículos fabricados. Debido a que el principio de reserva de costes activos se usará en los cálculos de lista de materiales (L. MAT), solo será necesario especificar los cambios de coste incrementales.

## <a name="guidelines-for-defining-the-simulation-costing-version"></a>Directrices para definir la versión de gestión de costes de simulación
Use las directrices siguientes al definir la versión de gestión de costes para simulaciones:

-   Asigne un tipo de gestión de costes de **Costes planificados**.
-   Asigne un identificador significativo para la versión de gestión de costes, como, por ejemplo, **Simulación**.
-   Asegúrese de que el contenido incluya registros de costes.
-   Permitir la entrada de registros de costes. No bloquee la entrada de costes pendientes.
-   Permita la entrada de registros de costes para todos los sitios. Si se especifica un sitio, limitará la entrada de registros de coste a dicho sitio.
-   Impedir la activación de los costes pendientes. Sólo se deben especificar costes pendientes para los registros de coste dentro de la versión de gestión de costes de simulación.
-   No especifique ninguna fecha de inicio. Se especificará una fecha de cálculo para cada cálculo de L. MAT que use la versión de gestión de costes de simulación.
-   Especifique un principio de reserva de **Actualmente activo**. El principio de reserva permite la especificación de cambios de coste incrementales para la simulación, pero usa los costes actualmente activos como origen para todos los demás registros de coste. Se presupone que todos los costes actualmente activos existen para todos los demás registros.
-   Especifique un modelo de precio de coste del **Precio de coste de versión**, pero no restrinja los cálculos. Por ejemplo, las simulaciones pueden también emplear el modelo de precio de costes de un **grupo de cálculos de L. MAT** para indicar el origen de los datos de contribución de coste para artículos comprados.
-   Especifique un modo de expansión **Multinivel**, pero no restrinja los cálculos. Las simulaciones puede usar otros modos de expansión.

## <a name="costing-versions"></a>Versiones de gestión de costes
En los casos siguientes se muestra cómo se usa la versión de gestión de costes de simulación para simular el impacto de los cambios de coste. Antes de especificar un cambio de coste simulado, elimine los registros de coste pendientes dentro de la versión de gestión de costes de simulación para poder empezar de cero. Utilice la página **Precio de artículo** para ver y eliminar los registros de coste pendientes relacionados con los precios de artículo y los precios de categoría de coste.

-   Simule el cambio de coste para un artículo comprado. Por ejemplo, el cambio de coste podría reflejar un aumento o disminución esperados en el coste de material adquirido crítico. Si desea definir el coste diferente de un artículo comprado, use la página **Precio de artículo** para especificar un registro de coste pendiente dentro de la versión de gestión de costes de simulación.
-   Simule el cambio de coste para una categoría de coste. Por ejemplo, el cambio de coste podría reflejar un aumento o disminución esperados de las tarifas de mano de obra o en las tarifas por hora de los recursos de operaciones. Si desea definir el coste diferente de una categoría de coste, use la página **Precio de categoría de coste** para especificar un registro de coste pendiente dentro de la versión de gestión de costes de simulación.
-   Simule el cambio de coste de una fórmula de cálculo de coste indirecto. Por ejemplo, el cambio de coste podría reflejar un aumento o disminución esperados de los gastos generales de fabricación. Si desea definir el cambio en una fórmula de cálculo de coste indirecto, use la página **Configuración de la hoja de gestión de costes** para especificar un registro de coste pendiente en la versión de gestión de costes de simulación, y validar y guardar el cambio.

Tras especificar los cambios de coste simulados, calcule los costes de los artículos fabricados que se verán afectados por dichos cambios. Use la página **Cálculo** para la versión de gestión de costes de simulación e identifique los artículos fabricados seleccionados que se verán afectados por los cambios de coste. Los cálculos de L. MAT se aplicarán a todos los artículos fabricados, salvo que seleccione artículos seleccionados. Como alternativa, puede usar la opción de cálculo de L. MAT para las actualizaciones de tipo "Utilizado en". Visualice los registros de coste de artículo dentro de la versión de gestión de costes de simulación para analizar cómo los cambios de coste simulados afectaron a los costes de los artículos fabricados seleccionados. Use las páginas **Precio de artículo** y **Calcular coste del artículo** para ver y analizar los costes.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]