---
title: Nuevo cálculo de los costes de sustitución y los valores asegurados para grupos de activos fijos
description: Este artículo explica el proceso de la actualización de los costes de sustitución y los valores asegurados de los activos fijos.
author: ShylaThompson
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 3261
ms.assetid: b8876f83-8772-4f2a-b277-12724e2a0c44
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0756287406ad12237632ffbd455dbc6ba15d9915
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1563374"
---
# <a name="recalculate-replacement-costs-and-insured-values-for-fixed-asset-groups"></a>Nuevo cálculo de los costes de sustitución y los valores asegurados para grupos de activos fijos

[!include [banner](../includes/banner.md)]

Este artículo explica el proceso de la actualización de los costes de sustitución y los valores asegurados de los activos fijos.

Es posible que, periódicamente, se reciba un aviso de que ha cambiado el coste para sustituir o asegurar activos fijos específicos. Por ejemplo, el gerente podría notificar al usuario de que la tasa de inflación del año pasado fue del 3%, de modo que se debe aumentar el coste de sustitución de todos los activos fijos en un 3%. 

Aunque es posible editar el coste de sustitución y el valor asegurado de activos fijos individuales en la página **Activos fijos**, puede usar la página **Actualizar costes de sustitución y valores asegurados** para actualizar estos valores de un grupo de activos simultáneamente. Esta información describe cómo actualizar los valores para los grupos de activos fijos o para activos específicos en los grupos.

## <a name="how-values-are-updated"></a>Actualización de los valores
Para volver a calcular los costes de sustitución y los valores asegurados de los grupos de activos fijos, en primer lugar debe especificar el porcentaje por el cual se deben cambiar los costes y valores actuales y, a continuación, deberá realizar la actualización periódica para volver a calcular los valores. El porcentaje se especifica en los campos **Factor de coste de sustitución** y **Factor de valor asegurado** del formulario **Grupos de activos fijos**. Aunque estos factores se especifican para el grupo de activos fijos, cuando se usa la página **Actualizar costes de sustitución y valores asegurados**, se puede seleccionar la opción para volver a calcular el coste de sustitución y el valor asegurado únicamente para los activos fijos específicos de un grupo. 

Cuando se usa la página **Actualizar costes de sustitución y valores asegurados** para volver a calcular el coste de sustitución y el valor asegurado para los activos, se usan las fórmulas siguientes:

-   \[(Factor del coste de sustitución del grupo de activos / 100) + 1\] \* Coste de sustitución existente del activo
-   \[(Factor del valor asegurado del grupo de activos / 100) + 1\] \* Valor asegurado existente del activo

> [!NOTE] 
> Cuando se usa la página **Actualizar costes de sustitución y valores asegurados**, se actualiza tanto el coste de sustitución como el valor asegurado de los activos seleccionados; no se puede especificar que se actualice un único valor. Para dejar un valor igual y actualizar el otro valor, especifique 0 (cero) como factor en la página **Grupos de activos fijos**. Un factor cero o en blanco hace que se omita el cálculo en la actualización. La actualización periódica no afectará al valor neto ni al valor neto en los libros de los activos fijos. 

## <a name="how-to-use-a-date-to-select-which-items-to-update"></a>Uso de una fecha para seleccionar los artículos que se deben actualizar
De manera predeterminada, el proceso de actualización actualiza los activos seleccionados que no se han actualizado en el día actual pero que podrían haberse actualizado en días anteriores. Por ejemplo, &lt; fecha actual significa "antes del día de hoy". Puede cambiar la fecha en la página **Actualizar costes de sustitución y valores asegurados** al hacer clic en el botón **Seleccionar**. Los criterios de fecha que se especifican se comparan con la fecha de la última actualización periódica del activo (el campo **Última actualización periódica de valor/coste** en la página **Activos fijos**). Cada vez que se actualice correctamente el coste de sustitución o el valor asegurado de un activo fijo, se actualizará automáticamente el campo **Última actualización periódica de valor/coste** con la fecha actual. 

Ejemplo 

Ayer se actualizó el coste de sustitución de los grupos Vehículos, Mobiliario de oficina y Edificios en un 5% y ahora se considera que los activos se han actualizado correctamente. Para excluir estos activos de la actualización de hoy de los demás activos fijos se escribe una fecha en el campo **Última actualización periódica de valor/coste** correspondiente a antes de ayer (&lt; fecha de ayer), ya que la última actualización de **Vehículos**, **Mobiliario de oficina** y **Edificios** se produjo fuera de los criterios de fecha especificados.

## <a name="cumulative-effect-of-each-update"></a>Efecto acumulativo de cada actualización
Cada actualización tiene un efecto acumulativo. Por lo tanto, debe planificar las actualizaciones con cuidado. Por ejemplo, si aumenta todos los activos en un 3% el martes y, a continuación, actualiza el mobiliario de oficina en un 4% el viernes, se aumentará el mobiliario de oficina un 7,12% en total.

## <a name="scenario"></a>Escenario
El gerente notifica al usuario los siguientes cambios en los activos fijos:
-   Aumento del coste de sustitución de todos los activos fijos, excepto los equipos informáticos, de un 3,25%.
-   Aumento del coste de sustitución de todo el mobiliario de oficina de un 1% adicional.
-   Reducción del coste de sustitución y del valor asegurado de todos los equipos informáticos de un 10%.

Realiza los siguientes cambios:
1.  En la página **Grupos de activos fijos**, para todos los grupos de activos fijos excepto el grupo **Mobiliario de oficina** y **Equipos informáticos**, escriba 3,25 en el campo **Factor de coste de sustitución** y 0 en el campo **Factor de valor asegurado**.
2.  Para el grupo **Mobiliario de oficina**, escriba 4,25 en el campo **Factor de coste de sustitución** y 0 en el campo **Factor de valor asegurado**.
3.  Para el grupo **Equipos informáticos**, escriba 10- en el campo **Factor de coste de sustitución** y -10 en el campo **Factor de valor asegurado**.
4.  En la página **Actualizar costes de sustitución y valores asegurados**, hace clic en **Aceptar** para volver a calcular todos los activos fijos.

El día siguiente, el gerente indica que los equipos informáticos disminuyeron en un 8% en lugar de en un 10%, de modo que se deben corregir los costes de sustitución y valores asegurados. Para ello, se puede usar uno de estos dos métodos:
-   Cambie manualmente los campos **Valor asegurado** y **Coste de sustitución** en la página **Activos fijos** para cada activo fijo del grupo de activos fijos **Equipos informáticos**. Calcule y especifique manualmente los valores como si hubiera reducido el importe original en un 8%. Mediante este método, no utiliza la página **Actualizar costes de sustitución y valores asegurados**.
-   Especifique los factores de coste de sustitución y valor asegurado para el grupo **Equipos informáticos** en los campos **Factor de coste de sustitución** y **Factor de valor asegurado** en la página **Grupos de activos fijos**. De este modo, se restablecerán los activos a su valor original (antes de la reducción del 10%) y se aplicará la reducción del 8% al valor original. Después, use la página **Actualizar costes de sustitución y valores asegurados** para volver a calcular los valores en función de los factores especificados.

> [!NOTE]  
> No es posible invertir el factor de -10 al especificar un factor de 10 positivo (ni un factor de 2, que es la diferencia entre -10 y -8), ya que los importes no se calcularán según se espera. 





