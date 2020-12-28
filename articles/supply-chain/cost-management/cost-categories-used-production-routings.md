---
title: Categorías de costes utilizadas en las rutas de producción
description: Este artículo proporciona información acerca de las categorías de coste que se aplican a los entornos de fabricación que usan ruta.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjCategory, RouteCostCategoryPrice
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 78153
ms.assetid: a3fdc76c-0a27-4723-b1c7-4322f707d89e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 20697fd557fd81a0eec5a033c2c397f3918e6477
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437000"
---
# <a name="cost-categories-used-in-production-routing"></a>Categorías de costes utilizadas en las rutas de producción

[!include [banner](../includes/banner.md)]

Este artículo proporciona información acerca de las categorías de coste que se aplican a los entornos de fabricación que usan ruta.

Las categorías de costes se aplican en los entornos de fabricación en los que se utiliza información de rutas. Se asignan a los recursos de operaciones y a las operaciones de rutas para definir los costes por hora y para la contribución de los costes de segmentos a los costes calculados de los artículos fabricados. Los grupos de costes asignados a categorías de costes permiten clasificar las contribuciones de los costes de fabricación en función de los recursos de operaciones y del tipo de actividad, como el tiempo de configuración y de ejecución. El nivel de detalle de las asignaciones de grupos de coste permite que se calculen los gastos generales de fabricación en base a la información de rutas. 

**Nota:** En los entornos de fabricación, las categorías de costes se conocen por varios otros nombres, como los códigos de índice de mano de obra o los códigos de índice de máquina. 

Cada categoría de costes tiene registros de costes asociados y un grupo de costes asignado. Se requieren diferentes categorías de costes en función de los objetivos de producción.

-   Asigne diferentes costes por hora, en función del recurso de operaciones. Por ejemplo, los costes pueden variar para distintos tipos de capacidades de mano de obra, máquinas o celdas de fabricación.
-   Asigne diferentes costes por hora según el tiempo de configuración o el tiempo de ejecución asociado a la operación de rutas.
-   Asigne costes de recursos de operaciones en función de la cantidad de salida en lugar de costes por hora, por ejemplo, precios unitarios por mano de obra asalariada.
-   Proporcione la segmentación del grupo de costes de las contribuciones de costes al coste calculado de un artículo fabricado. Por ejemplo, puede segmentar los costes de máquinas y mano de obra.
-   Indique qué base del grupo de costes se utilizará para las fórmulas de cálculo de gastos generales, por ejemplo, las fórmulas para gastos generales asociados a los costes de mano de obra y los gastos generales asociados a los costes de máquina en relación con el tiempo de configuración y de ejecución.

Puede asignarse una categoría de costes al tiempo de preparación, al tiempo de proceso y a la cantidad de una operación de rutas. Cuando, por ejemplo, la segmentación de costes o los grupos de costes difieren entre el tiempo de preparación y el tiempo de procesamiento, deben definirse y asignarse distintas categorías de costes al tiempo de preparación y al tiempo de proceso. El uso selectivo de categorías de costes por tiempo de preparación, tiempo de proceso y cantidad se determina en función del grupo de rutas asignado a una operación. La asignación de categorías de costes en función del tiempo y la cantidad puede ser obligatorio por las directivas de la empresa que se definen en la página **Parámetros de control de producción**. 

Cada categoría de costes tiene los costes asociados basados en la definición de los registros de costes dentro de una versión de gestión de costes. Use la página **Precio de categoría de coste** para definir los registros de costes de una versión y un sitio de gestión de costes especificados. Cuando el registro de costes de una categoría de costes se especifica por primera vez, tiene un estado **Pendiente** y una fecha de vigencia esperada. Al activar el registro de costes, se actualiza el estado a **Actualmente activo** y la fecha de vigencia a la fecha de activación. Diferentes registros de costes pueden reflejar sitios, fechas de vigencia o estados diferentes. Los cálculos de las listas de materiales (L. MAT) para una fecha futura o histórica utilizan los registros de costes con la fecha de vigencia pertinente. El registro de coste activo actual se usará para estimar costes de pedidos de producción y para valorar la hora notificada contra un pedido de producción. 

El registro de costes para una categoría de costes puede ser específico o empresarial. Para que un registro de costes sea específico de un sitio, asígnele un sitio. Por el contrario, un valor en blanco indica que el registro de costes se aplica a todos los sitios de la empresa. Debido a que los costes pueden diferir entre los sitios, por ejemplo, los registros de costes deberán definirse en función de cada sitio. 

Normalmente, la operación de rutas hereda las categorías de costes asignadas a los recursos de operaciones o a la operación maestra. Cuando se crea un pedido de producción, las operaciones de rutas de la ruta de producción reflejan la versión de ruta seleccionada. Puede anular las categorías de costes asignadas a las operaciones de rutas de producción. 

Algunos tipos de trabajo de producción se pueden aplicar a estimaciones del tiempo del proyecto y a los informes. En este caso, se requiere una categoría de coste para fines de proyecto y producción. Debe definirse la información adicional relacionada con el proyecto cuando se marque una categoría de costes para su uso en los proyectos.



