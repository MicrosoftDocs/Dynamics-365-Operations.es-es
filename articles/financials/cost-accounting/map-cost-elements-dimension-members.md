---
title: "Asignar miembros de dimensión de elemento de coste a un conjunto común de miembros de dimensión"
description: "Asignando diferentes miembros de la dimensión del elemento de coste a un conjunto común de miembros de la dimensión del elemento de coste, los datos se combinan en un formato común para los análisis."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMDimension, CAMDimensionMember
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 223234
ms.assetid: 4c66a231-aed2-48b5-9727-b3eb4fe6e6aa
ms.search.region: global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b15e251410937ff4f85ecdfaa55ca1a998d1d1ac
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="map-cost-element-dimension-members-to-a-common-set-of-dimension-members"></a>Asignar miembros de dimensión de elemento de coste a un conjunto común de miembros de dimensión

[!include[banner](../includes/banner.md)]


Asignando diferentes miembros de la dimensión del elemento de coste a un conjunto común de miembros de la dimensión del elemento de coste, los datos se combinan en un formato común para los análisis.

Si es una empresa global y cumple con los requisitos estatutarios de contabilidad, puede usar múltiples planes contables. Al importar los miembros de dimensión de elemento de coste desde diferentes planes contables, puede terminar con una mezcla de cuentas. Sin embargo, estas cuentas podrían tener la misma naturaleza y es posible que desee analizar y asignar costes para ellas mediante un formato común.

## <a name="map-cost-element-dimension-members-to-a-common-format"></a>Asigne miembros de dimensión de elemento de coste a un formato común
El siguiente ejemplo le muestra cómo siendo controlador de coste, puede crear una nueva dimensión de elemento de coste en Contabilidad de costes que asigne a los miembros de la dimensión del elemento de coste desde la estructura del plan contable de Estados Unidos y la estructura francesa a un conjunto común de miembros de dimensión de elemento de coste. Puede utilizar el conjunto de común de miembros de la dimensión del elemento de coste para analizar datos de coste de las dos entidades jurídicas en un libro mayor de costes.

| Origen: plan contable de Estados Unidos                                          | Origen: plan contable francés                                          | Nuevo conjunto común de miembros de la dimensión del elemento de coste                        |
|-----------------------------------------------------------------------|---------------------------------------------------------------------------|-------------------------------------------------------------------------|
| Miembros de dimensión del elemento de coste importados del plan contable de Estados Unidos. | Miembros de dimensión del elemento de coste importados del plan contable francés. | Asignación de miembros de dimensión de elemento de coste de Estados Unidos y francés a un conjunto común |
| 5001: Ventas                                                           | 5001: Ventas y publicidad                                               | 5000: Ventas y publicidad                                             |
| 5030: Publicidad                                                     | 6390: Compra de existencias\*                                                    | 7000: Gastos de limpieza                                                 |
| 7001: Gastos de limpieza                                               | 7001: Gastos de viaje                                                      | 7001: Gastos de viaje                                                   |

\*No se ha asignado el miembro de la dimensión del elemento de coste francés de la Compra de existencias.

## <a name="currency-conversion"></a>Conversión de divisas
Los distintos planes contables que use se pueden configurar para utilizar distintas divisas. En este caso, asegúrese de especificar una conversión de divisa, para procesar los datos de coste en la divisa correcta, como se define en el libro mayor de la contabilidad de costes donde se usan los miembros de la dimensión del elemento de coste. En el ejemplo anterior, si se utilizan dólares estadounidenses (USD) en la contabilidad de la contabilidad de costes, debe crear una conversión de divisa de USD a euros (EUR) para procesar transacciones para los miembros de dimensión del elemento de coste asignados.

## <a name="update-mappings-at-any-time"></a>Actualizar las asignaciones en cualquier momento
Puede actualizar las definiciones de asignación para una dimensión de elemnto de coste en cualquier momento. Dado que las asignaciones no son fechas efectivas, los cambios se aplican la próxima vez que procesa transacciones de coste o ejecuta cálculos de coste.




