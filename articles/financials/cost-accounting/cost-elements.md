---
title: Dimensiones de elemento de coste
description: "Como uno de los pilares básicos de la Contabilidad de costes, las dimensiones del elemento de coste se utilizan para clasificar y realizar un seguimiento de a dónde fluyen los costes."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMDimension
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 223204
ms.assetid: 1eda0e62-760b-4737-9dfd-3c3c38d80c1a
ms.search.region: global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 0f47c75b6f6f4533501070f78698de82cf70f9bd
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="cost-element-dimensions"></a>Dimensiones de elemento de coste

[!include[banner](../includes/banner.md)]


Como uno de los pilares básicos de la Contabilidad de costes, las dimensiones del elemento de coste se utilizan para clasificar y realizar un seguimiento de a dónde fluyen los costes. 

Un elemento de coste corresponde a un artículo de coste relevante del plan contable. Básicamente, puede ser cualquier tipo de elemento del nivel más bajo de un negocio a donde los costes pueden fluir. Los elementos de coste como concepto oscilan entre cuentas contables a todos los recursos de coste relevantes. Actualmente, la Contabilidad de costes admite cuentas contables.

## <a name="two-types-of-cost-elements"></a>Dos tipos de elementos de coste
Existen dos tipos de elementos de coste: elementos de coste principales y elementos de coste secundarios. En la tabla siguiente se describe la diferencia entre los dos tipos.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Elementos de coste principales</strong></td>
<td><strong>Elementos de costes secundarios</strong></td>
</tr>
<tr class="even">
<td>Los elementos de coste principales representan el flujo de costes de la contabilidad financiera a la contabilidad de costes. La estructura del elemento de coste corresponde a la estructura de la cuenta de pérdidas y ganancias en la contabilidad general, donde un elemento de costes puede corresponder a una cuenta principal. No todas las cuentas principales pueden ser representadas necesariamente como elementos de coste en función de las necesidades del negocio. Ejemplos de elementos de coste principales incluyen:
<ul>
<li>Costes de mercancías vendidas (COG)</li>
<li>Costes indirectos de material</li>
<li>Costes de personal</li>
<li>Costes de energía</li>
</ul></td>
<td>Los elementos de coste secundarios representan el flujo de costes internamente, ya que estos costes se crean y se usan solo en la Contabilidad de costes. Se utilizan para garantizar que el origen de costes se pueda seguir. Dichos elementos de costes se utilizan en asignaciones de costes y cálculos de gastos generales. Ejemplos de elementos de coste secundarios incluyen:
<ul>
<li>Costes de producción</li>
<li>Gastos generales de producción, materiales y marketing</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="cost-element-dimensions-and-cost-element-dimension-members"></a>Dimensiones del elemento de coste y miembros de la dimensión del elemento de coste
Se hace referencia a los elementos de coste como *dimensiones del elemento de coste* . Los valores de dimensión individuales se denominan *miembros de dimensión de elemento de coste*. Por ejemplo, si tiene una estructura del plan contable de Estados Unidos. (COA) que es la base de sus informes estatutarios. Este COA se usa como la dimensión del elemento de coste. Las cuentas, que son elementos de coste principales, se representan como miembros de dimensión del elemento de coste en la Contabilidad de costes. El captura de pantalla siguiente muestra un ejemplo de Cuentas principales como dimensión de elemento de coste con sus cuentas principales como miembros de dimensión de elemento de coste. 

[![cost-element-dimensions](./media/cost-element-dimensions.png)](./media/cost-element-dimensions.png)

## <a name="import-cost-element-dimension-members-through-data-connectors"></a>Importar miembros de dimensión de elemento de coste mediante conectores de datos
Para facilitar la configuración de los miembros de la dimensión del elemento de coste en la Contabilidad de costes, puede usar los conectores de datos que se han generado previamente o los que ha personalizado para recuperar los elementos de coste principales de uno o más sistemas de origen.

## <a name="implementation-considerations"></a>Consideraciones sobre la implementación
Ya que los elementos de coste representan el valor mínimo de los detalles de coste, deberá asegurarse de que todos los elementos de coste requeridos para hacer el informe de gestión se incluirán cuando implemente la estructura de elementos de coste. Encontrar el número adecuado de elementos de coste puede suponer un desafío para el control de costes. Disponer de miles de elementos de costes puede dificultar el control de cada elemento de coste. Como alternativa, puede agrupar elementos de coste y gestionar el control de coste a nivel agregado.




