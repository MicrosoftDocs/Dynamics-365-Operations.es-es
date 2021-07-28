---
title: Estrategia de solucionador para la configuración de productos
description: Este tema describe cómo puede usar la estrategia de solucionador para mejorar el rendimiento de la configuración de productos.
author: cvocph
ms.date: 02/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PCCreateProductConfigurationModel, PCProductConfigurationModelListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d351066b0092318275491d933b7b90089c6855b4
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "6359942"
---
# <a name="solver-strategy-for-product-configuration"></a>Estrategia de solucionador para la configuración de productos

[!include [banner](../includes/banner.md)]

Este tema describe cómo puede usar la estrategia de solucionador para mejorar el rendimiento de la configuración de productos.

El concepto de estrategias de solucionador se introdujo primero en la actualización acumulativa 7 (CU7) para Microsoft Dynamics AX 2012 R2. Fue ampliado en la actualización acumulativa 8 (CU8) para Microsoft Dynamics AX 2012 R3 y Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition 7.3.

El concepto de la estrategia de solucionador consta ahora de las siguientes estrategias:

- Valor predeterminado
- Dominios mínimos primero
- De arriba a abajo
- Z3

## <a name="solver-strategy"></a>Estrategia de solucionador 

Se puede formular un modelo de configuración de productos como un [problema de satisfacción de restricción (CSP)](http://aima.cs.berkeley.edu/2nd-ed/newchap05.pdf) Microsoft Solver Foundation (MSF) ofrece dos tipos de estrategias de solucionador para resolver los CSP que se pueden utilizar de los modelos de configuración de productos. Estas estrategias de solucionador confían en la [heurística](https://techterms.com/definition/heuristic), que se emplea para determinar el orden en que se consideran las variables de los CSP cuando se está solucionando el problema. La heurística puede afectar considerablemente al rendimiento cuando se está solucionando un problema o una clase de problemas.

La estrategia de solucionador para modelos de configuración de productos determina qué solucionador se emplea con la heurística. Las estrategias **Predeterminado**, **Dominios mínimos primero** y **De arriba a abajo** utilizan dos solucionadores de MSF, mientras que la estrategia **Z3** emplea el solucionador Z3. 

Los estudios reales de implementación de clientes han mostrado que un cambio en la estrategia de solucionador de un modelo de configuración de productos puede reducir el tiempo de respuesta de minutos a milisegundos. Por lo tanto, vale la pena intentar diferentes estrategias de solucionador para encontrar la estrategia más eficiente para su modelo de configuración de productos.

## <a name="change-the-settings-for-the-solver-strategy"></a>Cambie los valores para la estrategia de solucionador

Para cambiar la estrategia de solucionador, en la página **Modelos de configuración de productos** , en el Panel de acciones, seleccione **Propiedades del modelo**. A continuación, en el cuadro de diálogo **Editar los detalles del modelo**, seleccione una estrategia de solucionador.

[![Cambiar la estrategia de solucionador.](./media/solver-strategy.png)](./media/solver-strategy.png)

Actualmente, no existe una lógica que detecte automáticamente qué estrategia de solucionador será la estrategia más eficiente para la configuración de productos basada en restricciones. Por lo tanto, debe probar las estrategias de solucionador una por una.

La siguiente tabla proporciona recomendaciones acerca de la estrategia de solucionador que se va a usar en distintos escenarios.

| Estrategia de solucionador      | Use la estrategia en este escenario |
|----------------------|-----------------------------------|
| Valor predeterminado              | La estrategia **Predeterminada** se ha optimizado para solucionar los modelos que se basan en restricciones de tabla. Los estudios de implementación de cliente han mostrado que esta estrategia es la estrategia más eficiente en escenarios donde las restricciones de tabla se utilizan extensivamente. |
| Dominios mínimos primero | Las estrategias **Dominios mínimos primero** y **De arriba abajo** se encuentran íntimamente relacionadas. Los estudios de implementación de cliente han mostrado que la estrategia **De arriba abajo**, supera la estrategia **Dominios mínimos primero**. Sin embargo, la estrategia **Dominios mínimos primero** se mantiene en el producto para una compatibilidad con versiones anteriores. Ambas estas estrategias de solucionador han demostrado ser más eficientes a la hora de resolver modelos que contienen varias expresiones aritméticas en las que no se utilizan restricciones de tabla. Sin embargo, en algunos casos, la estrategia **Predeterminada** supera estas dos estrategias. Por lo tanto, no olvide probar cada estrategia. |
| De arriba a abajo             | Las estrategias **Dominios mínimos primero** y **De arriba abajo** se encuentran íntimamente relacionadas. Los estudios de implementación de cliente han mostrado que la estrategia **De arriba abajo**, supera la estrategia **Dominios mínimos primero**. Sin embargo, la estrategia **Dominios mínimos primero** se mantiene en el producto para una compatibilidad con versiones anteriores. Ambas estas estrategias de solucionador han demostrado ser más eficientes a la hora de resolver modelos que contienen varias expresiones aritméticas en las que no se utilizan restricciones de tabla. Sin embargo, en algunos casos, la estrategia **Predeterminada** supera estas dos estrategias. Por lo tanto, no olvide probar cada estrategia. |
| Z3                   | Le recomendamos que utilice la estrategia **Z3** como la estrategia de solucionador predeterminada. Si le preocupa el rendimiento y la escalabilidad, puede evaluar las otras estrategias. |

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de la configuración del producto](build-product-configuration-model.md)

[Heurística](https://techterms.com/definition/heuristic)

[Problema de satisfacción de restricción](http://aima.cs.berkeley.edu/2nd-ed/newchap05.pdf)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]