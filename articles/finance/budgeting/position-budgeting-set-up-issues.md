---
title: Solución de problemas de presupuesto
description: Este artículo proporciona respuestas a preguntas que puede que tenga cuando configure el presupuesto de puesto. Responde a preguntas frecuentes acerca de cómo crear elementos de costes presupuestarios, grupos de compensación y cuadrículas de compensación.
author: panolte
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmBudgetPurposeType, HcmPositionForecast
audience: Application User
ms.reviewer: roschlom
ms.custom: 88253
ms.assetid: c44df01b-8700-4022-b4c6-c4b1cb84d31d
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 492a0798d1934b0fe1adf4f0546013f394beab06948f02f92358bae408e7748f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6726071"
---
# <a name="position-budgeting-troubleshooting"></a>Solución de problemas de presupuesto

[!include [banner](../includes/banner.md)]

Este artículo proporciona respuestas a preguntas que puede que tenga cuando configure el presupuesto de puesto. Responde a preguntas frecuentes acerca de cómo crear elementos de costes presupuestarios, grupos de compensación y cuadrículas de compensación. 

## <a name="why-cant-i-find-the-forecast-position-page-in-human-resources"></a>¿Por qué no encuentro la página de puesto de previsión en Recursos humanos?

Los puestos de previsión se han movido a Gestión presupuestaria.

## <a name="why-cant-i-delete-a-budget-cost-element"></a>¿Por qué no puedo eliminar un elemento de coste presupuestario?
No puede eliminar un elemento de coste presupuestario asignado a un puesto de previsión. Para poder eliminar un elemento de coste presupuestario, debe quitarlo de todas las posiciones de previsión. **Sugerencia:** Para encontrar todos los puestos a los que está asignado un elemento de coste presupuestario, seleccione el elemento de coste en la página **Elementos de coste presupuestario** y, a continuación, haga clic en **Actualizar puestos**. Los puestos que usan el elemento de coste se muestran en la cuadrícula superior.

## <a name="how-can-i-remove-a-cost-element-from-multiple-forecast-positions-without-opening-each-one"></a>¿Cómo puedo quitar un elemento de coste de varios puestos de previsión sin abrirlos todos?
No es posible eliminar un elemento de coste. Sin embargo, si cambia la fecha de inicio y final de modo que se encuentren fuera de las fechas del ciclo de planificación presupuestaria, el elemento de coste ya no se asignará a los puestos de previsión de dicho ciclo de planificación presupuestaria. Para realizar este cambio, abra el elemento de coste presupuestario y, a continuación, en la ficha desplegable **Cálculo de costes**, haga clic en **Modificar fechas** y cambiar la fecha de vigencia o la fecha de vencimiento. Haga clic en **Aceptar** para actualizar automáticamente todos los puestos de previsión a los que está asignado el elemento de costes. **Sugerencia:** Si usa este método, tenga en cuenta que quita el elemento de coste presupuestario de **todos** los puestos de previsión en los que la fecha inicial y final ya no esté dentro del intervalo adecuado. Si esto no es lo que quiere hacer, debe abrir cada puesto de previsión del que desee quitar el elemento de coste presupuestario y realizar manualmente el cambio.

## <a name="why-cant-i-enter-an-annual-amount-on-the-cost-calculation-fasttab-for-the-budget-cost-element"></a>¿Por qué no puedo especificar un importe anual en la ficha desplegable de cálculo de costes para el elemento de coste presupuestario?
No se puede especificar un importe anual si hay elementos de coste presupuestario en la ficha desplegable **Base de cálculo** porque el sistema requiere un porcentaje para calcular el valor. Para cambiar el valor, elimine todos los elementos de coste presupuestario de la ficha **Base de cálculo**.

## <a name="why-cant-i-change-the-budget-cost-type-from-earning-to-another-budget-cost-type"></a>¿Por qué no puedo cambiar el tipo de coste presupuestario de ganancia a otro tipo?
Algunos elementos de coste presupuestario usan el elemento de coste ganancia como base de cálculo. Para cambiar el campo **Tipo de coste presupuestario**, elimine el elemento de coste de ganancias de la ficha desplegable **Base de cálculo** de todos los elementos de coste presupuestario.

## <a name="why-cant-i-change-the-date-on-budget-cost-element-lines-for-a-budget-cost-element"></a>¿Por qué no puedo cambiar la fecha de las líneas del elemento de coste presupuestario para un elemento de coste presupuestario?
No puede cambiar la fecha en la línea de elemento de coste presupuestario cuando se usa un elemento de coste presupuestario para un puesto de previsión. Esta limitación ayuda a garantizar que los puestos de previsión están siempre dentro de las directrices del elemento de coste presupuestario. Para cambiar la fecha, en la ficha desplegable **Cálculo de costes**, haga clic en **Modificar fechas** y especifique las nuevas fechas. A continuación, haga clic en **Aceptar** para actualizar los puestos a los que está asignado el elemento de costes.

## <a name="why-cant-i-change-the-costs-for-a-budget-cost-element-on-the-compensation-group-page"></a>¿Por qué no puedo cambiar los costes de un elemento de coste presupuestario en la página Grupo de compensación?
Solo puede crear y modificar elementos de coste presupuestario en la página **Elementos de coste presupuestario**.

## <a name="why-do-i-receive-an-error-message-when-i-change-the-dates-for-a-cost-element-on-a-forecast-position"></a>¿Por qué recibo un mensaje de error cuando cambio las fechas para un elemento de coste en un puesto de previsión?
Las fechas de la línea del elemento de coste de puesto de previsión deben estar dentro de los intervalos siguientes:

-   Las fechas de activación y jubilación del puesto.
-   Las fechas de activación y vencimiento del elemento de coste presupuestario.
-   Las fechas de inicio y fin del ciclo presupuestario asociado al proceso de planificación presupuestaria del puesto de previsión.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]