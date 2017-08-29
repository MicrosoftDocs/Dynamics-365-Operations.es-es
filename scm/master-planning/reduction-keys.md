---
title: "Claves de reducción"
description: "Este artículo proporciona ejemplos que muestran cómo configurar una clave de reducción. Incluye información sobre los distintos ajustes de la clave de reducción y los resultados de cada uno. Puede usar una clave de reducción para definir cómo reducir los requisitos de previsión."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqPlanSched
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19251
ms.assetid: aa9e0dfb-6052-4a2e-9378-89507c02fdf2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: ce3ff2ac0a5bd9bd342baa05425d7d0957ab8a09
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017

---

# <a name="reduction-keys"></a>Claves de reducción

[!include[banner](../includes/banner.md)]


Este artículo proporciona ejemplos que muestran cómo configurar una clave de reducción. Incluye información sobre los distintos ajustes de la clave de reducción y los resultados de cada uno. Puede usar una clave de reducción para definir cómo reducir los requisitos de previsión.

<a name="example-1-percent---reduction-key-forecast-reduction-principle"></a>Ejemplo 1: Porcentaje: principio de reducción de previsión clave de reducción
---------------------------------------------------------------

Este ejemplo muestra cómo reduce una clave de reducción los requisitos de previsión de la demanda en función de los porcentajes y los períodos definidos por la clave de reducción.

1.  En la página **Claves de reducción**, configure las siguientes líneas.
    | Cambio | Unidad  | Porcentaje |
    |--------|-------|---------|
    | 1      | Mes | 100     |
    | 2      | Mes | 75      |
    | 3      | Mes | 50      |
    | 4      | Mes | 25      |

2.  Vincule la clave de reducción al grupo de cobertura del artículo.
3.  En la página **Planes maestros**, en el campo **Principio de reducción**, seleccione **Porcentaje - clave de reducción**.
4.  Cree una previsión de la demanda de 1000 piezas por mes.

Si ejecuta la programación de previsión el 1 de enero, los requisitos de previsión de la demanda se consumen de acuerdo con los porcentajes configurados en la página **Claves de reducción**: las siguientes cantidades de requisitos se transfieren al plan maestro.

| Mes                | Número de piezas requeridas |
|----------------------|---------------------------|
| Enero              | 0                         |
| Febrero             | 250                       |
| Marzo                | 500                       |
| Abril                | 750                       |
| De mayo a diciembre | 1.000                     |

## <a name="example-2-transactions--reduction-key-forecast-reduction-principle"></a>Ejemplo 2: Principio de reducción de previsión clave de reducción de transacciones
Este ejemplo muestra cómo los pedidos reales, que se producen en períodos definidos por la clave de reducción, reducen los requisitos de previsión de la demanda.

-   En la página **Planes maestros**, en el campo **Principio de reducción**, seleccione **Transacciones - clave de reducción**.

Los siguientes pedidos de ventas existen el 1 de enero.

| Mes    | Número de piezas solicitadas |
|----------|--------------------------|
| Enero  | 956                      |
| Febrero | 1.176                    |
| Marzo    | 451                      |
| Abril    | 119                      |

Si utiliza la misma previsión de la demanda de 1000 piezas por mes, se transfieren las siguientes cantidades de requisitos al plan maestro.

| Mes                | Número de piezas requeridas |
|----------------------|---------------------------|
| Enero              | 44                        |
| Febrero             | 0                         |
| Marzo                | 549                       |
| Abril                | 881                       |
| De mayo a diciembre | 1.000                     |

## <a name="example-3-transactions--dynamic-period-forecast-reduction-principle"></a>Ejemplo 3: Principio de reducción de previsión del período dinámico de transacciones
En la mayoría de los casos, se configuran los sistemas de modo que las transacciones reduzcan la previsión de la demanda dentro de períodos específicos de previsión: semanas, meses, y así sucesivamente. Estos períodos se definen en la clave de reducción. No obstante, el tiempo entre dos líneas de previsión de la demanda también puede *implicar* a un período.

1.  Cree una previsión de la demanda para las fechas y las cantidades siguientes.
    | Fecha       | Previsión de la demanda |
    |------------|-----------------|
    | 1 de enero  | 1.000           |
    | 5 de enero  | 500             |
    | 12 de enero | 1.000           |

    En esta previsión, no hay un período claro entre las fechas de previsión: entre la primera y la segunda fecha hay un lapso de cuatro días, y entre la segunda y la tercera fecha hay un lapso de siete días. Estos distintos lapsos son períodos dinámicos.
2.  Cree líneas de pedidos de venta como sigue.
    | Fecha                             | Cantidad de pedido de ventas |
    |----------------------------------|----------------------|
    | 15 de diciembre en el año anterior | 500                  |
    | 3 de enero                        | 100                  |
    | 10 de enero                       | 200                  |

La previsión se reducirá como sigue:

-   El primer pedido de ventas no se encuentra dentro de ningún período, por lo que no se reducirá ninguna previsión.
-   El segundo pedido de ventas es para entre el 1 de enero y el 5 de enero, por lo que se reducirá la previsión para el 1 de enero por 100.
-   El tercer pedido de ventas es para entre el 5 de enero y el 12 de enero, por lo que se reducirá la previsión para el 5 de enero por 200.

Se creará el pedido planificado siguiente para satisfacer la previsión.

| Fecha de previsión de la demanda | Cantidad reducida |
|----------------------|------------------|
| 1 de enero            | 900              |
| 5 de enero            | 300              |
| 12 de enero           | 1.000            |

Este es un resumen de la reducción **Transacciones - período dinámico**:

-   Los requisitos de previsión se reducirán por las transacciones de pedidos reales que se producen durante el período dinámico. El período dinámico cubre las fechas de previsión actuales y finaliza con el inicio de la próxima previsión.
-   Este método no usa ni requiere una clave de reducción.
-   Cuando se utiliza esta opción, el comportamiento es el siguiente:
    -   Si la previsión se reduce por completo, los requisitos de previsión para la previsión actual se convierten en 0 (cero).
    -   Si no hay previsión futura, se reducen los requisitos de previsión de la última previsión que se introdujo.
    -   Se incluyen límites de tiempo en el cálculo de la reducción de previsión.
    -   Se incluyen días positivos en el cálculo de la reducción de previsión.
    -   Si las transacciones de pedidos reales sobrepasan a los requisitos previstos, las transacciones restantes no se reenvían al próximo período de previsión.


<a name="see-also"></a>Consulte también
--------

[Planes maestros](master-plans.md)




