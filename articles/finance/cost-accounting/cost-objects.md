---
title: Dimensiones de objeto de coste
description: Al analizar costes, se usan las dimensiones del elemento de coste para determinar a dónde fluyen los costes. Las dimensiones del objeto de coste se usan para determinar dónde se deben asignar los costes. Este tema proporciona información sobre las dimensiones de objeto de coste.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMDimensionMember, CAMCostObject
audience: Application User
ms.reviewer: roschlom
ms.custom: 223174
ms.assetid: 2a1cdd35-30cb-41e7-9506-67fd04a537c5
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 20ae6295389fa3cbaa7c90844d2a90f1e38387c4
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818788"
---
# <a name="cost-object-dimensions"></a>Dimensiones de objeto de coste

[!include [banner](../includes/banner.md)]

Al analizar costes, se usan las dimensiones del elemento de coste para determinar a dónde fluyen los costes. Las dimensiones del objeto de coste se usan para determinar dónde se deben asignar los costes. Este tema proporciona información sobre las dimensiones de objeto de coste.

Un objeto de coste puede ser cualquier tipo de objeto para el que desea realizar una estimación, asignar costes o medir directamente. Los objetos típicos de coste incluyen productos, proyectos, recursos, departamentos, centros de coste, y regiones geográficas. La administración utiliza objetos de coste para cuantificar costes y también para realizar un análisis de la rentabilidad.

## <a name="cost-object-dimensions-and-cost-object-dimension-members"></a>Dimensiones del objeto de coste y miembros de la dimensión del objeto de coste
Los objetos de coste se conocen como *dimensiones de objeto de coste*. Una vez haya decidido a qué entidad debe hacer referencia la dimensión de objeto de coste, debe especificar los valores de dimensión individuales o importarlos en la contabilidad de costes desde otros sistemas de origen. Estos valores de dimensión individuales se conocen como *miembros de dimensión de objeto de coste*. Por ejemplo, si desea usar la dimensión financiera que se denomina Centro de coste como dimensión de objeto de coste. Para ver cómo fluyen los costes a los centros de coste individuales, debe importar a los miembros de dimensión de objeto de coste. En este caso, los miembros de dimensión de objeto de coste son los centros de coste real, como Ventas, Producción, Administración y ubicaciones geográficas. El captura de pantalla siguiente muestra un ejemplo de Centros de coste como la dimensión de objeto de coste con sus centros de coste real como miembros de dimensión de objeto de coste. 

[![Captura de pantalla que muestra centros de coste como dimensión de objeto de coste](./media/cost-object-dimensions.png)](./media/cost-object-dimensions.png)

## <a name="import-cost-object-dimension-members-through-data-connectors"></a>Importar miembros de dimensión de objeto de coste mediante conectores de datos
Para realizar la importación de miembros de dimensión de objeto de coste, se usan los conectores de datos para recuperar los valores de las entidades que desea usar como dimensiones de objeto de coste. Puede utilizar los conectores de datos generados previamente o conectores de datos personalizados que genere usted.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]