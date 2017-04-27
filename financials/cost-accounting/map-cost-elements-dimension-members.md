---
title: "Asignar diferentes miembros de dimensión de elemento de coste a un conjunto común de miembros de dimensión"
description: "Asignando diferentes miembros de la dimensión del elemento de coste a un conjunto común de miembros de la dimensión del elemento de coste, los datos se combinan en un formato común para los análisis."
author: YuyuScheller
manager: AnnBe
ms.date: 2016-11-01 13 - 45 - 07
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CAMDimension, CAMDimensionMember
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 223234
ms.assetid: 4c66a231-aed2-48b5-9727-b3eb4fe6e6aa
ms.search.region: global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: a1e9817b6ee596ad516531d7597a2a39e115749c
ms.lasthandoff: 03/31/2017


---

# <a name="map-different-cost-element-dimension-members-to-a-common-set-of-dimension-members"></a>Asignar diferentes miembros de dimensión de elemento de coste a un conjunto común de miembros de dimensión

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


