---
title: Grupos de coste
description: "Los grupos de costes proporcionan la base para la segmentación y el análisis de contribuciones de coste en el coste calculado de un artículo fabricado como, por ejemplo, las contribuciones de coste de material, mano de obra y gastos generales. La segmentación de grupos de costes tiene varios sinónimos dentro de los entornos de fabricación como, por ejemplo, desglose de costes, descomposición de costes o clasificación de costes."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BOMCostGroup
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 50871
ms.assetid: 1855f744-f73f-4fa8-8290-a7ee126d368b
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 3592f3c076681c5b755b62383212bbe6d158f62d
ms.contentlocale: es-es
ms.lasthandoff: 04/25/2017


---

# <a name="cost-groups"></a>Grupos de coste

[!include[banner](../includes/banner.md)]


Los grupos de costes proporcionan la base para la segmentación y el análisis de contribuciones de coste en el coste calculado de un artículo fabricado como, por ejemplo, las contribuciones de coste de material, mano de obra y gastos generales. La segmentación de grupos de costes tiene varios sinónimos dentro de los entornos de fabricación como, por ejemplo, desglose de costes, descomposición de costes o clasificación de costes. 

La segmentación de grupos de costes tiene varios sinónimos dentro de los entornos de fabricación como, por ejemplo, desglose de costes, descomposición de costes o clasificación de costes. La segmentación de grupos de costes puede servir varios propósitos. A continuación se incluyen algunos ejemplos:

-   Puede segmentar los costes para diferentes tipos de materiales como, por ejemplo, ingredientes y material de embalaje para un producto de conserva, en función de los grupos de costes asignados a los artículos.
-   Puede segmentar los costes para diferentes tipos de recursos de operaciones como, por ejemplo, distintos tipos de mano de obra o máquinas, según los grupos de costes asignados a las categorías de coste relacionadas con los recursos de operaciones y las operaciones de ruta.
-   Puede segmentar los costes para el tiempo de configuración y ejecución en las operaciones de ruta, según los grupos de costes asignados a las categorías de coste relacionadas con las operaciones de ruta.
-   Puede segmentar los costes para distintos tipos de gastos generales como, por ejemplo, los relacionados con la mano de obra o las máquinas, según los grupos de costes asignados a los costes indirectos de la configuración de la hoja de gestión de costes.
-   Puede actuar como la base del cálculo de los distintos tipos de gastos generales de fabricación en la configuración de hoja de gestión de costes. Estos gastos generales pueden ser de varios tipos que están relacionados con la información de ruta acerca de recursos de operaciones o acerca del tiempo de configuración y ejecución. Los gastos generales de fabricación también pueden estar relacionados con las contribuciones de coste de material componente, lo que refleja una filosofía de lean manufacturing (producción ajustada) que elimina la necesidad de información de ruta.

La segmentación de grupos de costes se aplica al coste calculado de un artículo fabricado, independientemente de si ese coste se basa en costes estándar o en costes planificados. La página **Resumen** muestra esta segmentación por grupo de costes, ya sea por nivel o por grupo de costes y nivel. 

La capacidad de conservar la segmentación de grupos de costes entre varios niveles en una estructura de productos se conoce como *división*. La división solo se aplica a los artículos fabricados que usan un modelo de inventario de coste estándar. Si no se usa la división, el coste de un componente fabricado se tratará como una contribución de coste de material. El parámetro de inventario para el desglose de costes según el sublibro de contabilidad indica que la segmentación de grupos de costes se conservará entre varios niveles en los cálculos de coste estándar. Por contra, si una directiva no consta de niveles, la segmentación de grupos de costes solo se aplica a un cálculo de nivel único. Por ejemplo, la página **Acumulación de costes por grupo de costes** muestra la segmentación de grupos de costes entre varios niveles para los artículos de coste estándar. 

La segmentación de grupos de costes también se puede aplicar a las desviaciones de un artículo de coste estándar. Un segundo parámetro de inventario define si las desviaciones se identificarán por grupo de costes o si simplemente se resumirán. 

A un grupo de costes se le puede asignar un tipo de grupo de costes y un comportamiento por motivos de segmentación adicional.

-   **Tipo de grupo de costes**: cada grupo de costes se debe asignar a un tipo de grupo de costes para indicar que el grupo de costes se aplica a material directo, a fabricación directa o a subcontratación, o para designarlo como indirecto o sin definir. Un grupo de costes designado como material directo se puede asignar a los artículos. Un grupo de costes designado como fabricación directa se puede asignar a categorías de costes. Un grupo de costes de subcontratación directa se puede asignar a un tipo de producto de servicio, lo que le permite clasificar los costes que están asociados a una compra de servicios para actividades de subcontratación. Un grupo de costes indirecto se puede asignar a costes indirectos para suplementos o tasas. Un grupo de costes que está designado como sin definir se puede asignar a artículos, categorías de coste o costes indirectos. La asignación de un tipo de grupo de costes tiene varios propósitos. En primer lugar, limita la capacidad de asignar un grupo de costes y de ver una lista de grupos de costes aplicables. En segundo lugar, proporciona segmentación adicional para fines de generación de informes. En tercer lugar, se puede usar para asignar cuentas de contabilidad para las desviaciones.
-   **Comportamiento**: a cada grupo de costes se le puede asignar opcionalmente un comportamiento para indicar que el grupo de costes se aplica a costes fijos o a costes variables. Un grupo de costes con un valor nulo para el comportamiento se trata como coste variable. La asignación de un comportamiento solo sirve para la generación de informes. Por ejemplo, los costes se pueden mostrar con la segmentación de costes fijos y variables en la hoja de gestión de costes y en la página**Acumulación de costes por grupo de costes**. Si asigna un porcentaje que establece las ganancias para cada grupo de costes, el cálculo de la lista de materiales (L. MAT.) proporciona un precio de ventas sugerido en función de un enfoque de marcado según coste más margen.





