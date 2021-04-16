---
title: Crear dimensiones e importar miembros de dimensión
description: La contabilidad de costes es un módulo independiente que requiere datos maestros de otros módulos.
author: ShylaThompson
ms.date: 09/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMDimension
audience: Application User
ms.reviewer: roschlom
ms.custom: 256254
ms.assetid: e1b0a6e3-0c72-4a7d-90e1-20f870c6dbad
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: a9634612bcffbcf71b77dbb184e71367c67bac10
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5822936"
---
# <a name="create-dimensions-and-import-dimension-members"></a>Crear dimensiones e importar miembros de dimensión

[!include [banner](../includes/banner.md)]

La contabilidad de costes es un módulo independiente que requiere datos de otros módulos. Estos datos se categorizan en lo siguiente:

-  Elementos de coste
-  Objetos de coste
-  Dimensiones estadísticas

Un **elemento de coste** corresponde a un artículo de coste relevante del plan de cuentas. Un **objeto de coste** corresponde a cualquier tipo de dimensión financiera, como productos, centros de coste y proyectos de los que quiera realizar una estimación, asignar costes o medir directamente. Una **dimensión estadística** y sus miembros se usan para registrar entradas no monetarias. Los miembros de dimensión estadística se pueden usar como base de asignación en la distribución y asignación de costes. 

En el diagrama siguiente se muestran las dimensiones que se usan en la contabilidad de costes.

[![Dimensiones en contabilidad de costes](./media/cost-eos-dimensions.png)](./media/cost-eos-dimensions.png)

Una vez se importan los datos en la contabilidad de costes, puede usarlos para crear las diferentes perspectivas que proporcionarán información detallada a los gerentes de todos los niveles de la organización. En los temas siguientes se ofrece información acerca de la creación de dimensiones y la importación de los miembros de esas dimensiones. 

-  [Dimensiones de elemento de coste](cost-elements.md)
-  [Crear elementos de coste](./tasks/create-cost-elements.md)
-  [Dimensiones de objeto de coste](cost-objects.md)
-  [Asignar miembros de dimensión de elemento de coste a un conjunto común de miembros de dimensión](map-cost-elements-dimension-members.md)
-  [Asignar una dimensión de elemento de coste](./tasks/map-cost-element-dimension.md)
-  [Miembros de dimensiones estadísticas y plantillas de proveedor de medidas estadísticas](statistical-measure-provider-template.md)








[!INCLUDE[footer-include](../../includes/footer-banner.md)]