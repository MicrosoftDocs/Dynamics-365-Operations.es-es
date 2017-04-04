---
title: "Visión general de previsión de demanda"
description: "La previsión de demanda se usa para predecir demanda independiente de pedidos de ventas y demanda dependiente en cualquier momento de desemparejamiento para los pedidos del cliente. Las reglas ampliadas de la reducción de previsión de la demanda proporcionan una solución ideal para personalización total."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 72004
ms.assetid: 916707c9-1333-460f-a0fa-4e95f6fda2ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 9152616b81e7873426f296376b5e57c94439379d
ms.lasthandoff: 03/31/2017


---

# <a name="demand-forecasting-overview"></a>Visión general de previsión de demanda

La previsión de demanda se usa para predecir demanda independiente de pedidos de ventas y demanda dependiente en cualquier momento de desemparejamiento para los pedidos del cliente. Las reglas ampliadas de la reducción de previsión de la demanda proporcionan una solución ideal para personalización total.

Para generar la previsión de línea base, un resumen de transacciones históricas se transfiere a un servicio de aprendizaje automático de Microsoft Azure que está hospedado en Azure. Dado que este servicio no se comparte entre usuarios, puede ser personalizado fácilmente para cumplir los requisitos específicos del sector. Puede usar Dynamics 365 para que las operaciones visualicen la previsión, ajusten la previsión, y vean los indicadores clave de rendimiento (KPIs) sobre precisión de previsión.

## <a name="key-features-of-demand-forecasting"></a>Características clave de previsión de demanda
Estas son algunas de las características principales de la previsión de demanda:

-   Generación de una previsión estadística de línea base basada en datos históricos.
-   Uso de un sistema dinámico de dimensiones de previsión.
-   Visualización de tendencias de demanda, intervalos de confianza y ajustes de la previsión.
-   Autorización de la previsión ajustada para usar en procesos de planificación.
-   Eliminación de valores atípicos.
-   Crear medidas de precisión de la previsión.

## <a name="major-themes-in-demand-forecasting"></a>Temas principales en la previsión de demanda
Se implementan tres temas principales en la previsión de demanda:

-   **Modularidad:** la previsión de demanda es modular y fácil de configurar. Puede rotar la funcionalidad a intervalos cambiando la clave de configuración en ** comercio ** &gt; ** previsión de inventario ** &gt; ** previsión de demanda **.
-   ** La reutilización de la pila de Microsoft ** – Microsoft arrancó la plataforma de aprendizaje de equipo en febrero de 2015. El lugar de equipo, que ahora forma parte de la habitación de Análisis de Microsoft Cortana, permite de forma rápida y sencilla crear unidad proféticos de análisis, como la estimación de la demanda experimenta, mediante lenguajes de programación de la r de los algoritmos o de Python y una interfaz arrastrar y colocar simple.
    -   Puede descargar Dynamics 365 para los unidad de previsión de demanda de operaciones, cambiarlos en función de las necesidades empresariales, como publicarlos servicio Web en azul, y utilizarlos para generar las previsiones de demanda. Los unidad están disponibles para descarga si se adquirió una Dynamics 365 para la suscripción de operaciones para un planificador de producción como usuario de nivel de empresa.
    -   Puede descargar cualquiera de los experimentos de previsión de demanda actualmente disponibles en [Galería de análisis de Cortana](https://gallery.cortanaanalytics.com/). Por contra las que Dynamics 365 para los unidad de previsión de demanda de las operaciones automáticamente se integran con Dynamics 365 para las operaciones, los clientes y socios debe tratar la integración de los que descargar unidad de galería [] de Análisis de Cortana (https://gallery.cortanaanalytics.com/). Por lo tanto, unidad de galería [de Análisis de Cortana] (https://gallery.cortanaanalytics.com/) no es tan directo utilizarlo como experimenta Dynamics 365 para la previsión de demanda de las operaciones. Debe modificar el código de los unidad de modo que utilicen Dynamics 365 de la interfaz de programación de aplicaciones de las operaciones (API).
    -   Puede crear sus propios experimentos en es Estudio de aprendizaje automático de Microsoft Azure, publicarlos como servicios en Azure, y utilizarlos para generar las previsiones de demanda.
    -   Si no necesita alto rendimiento, o si no necesita procesar grandes cantidades de datos, puede usar el nivel libre de aprendizaje automático. Recomendamos que comience siempre desde este nivel, especialmente durante las fases de implementación y de pruebas. Si necesita un rendimiento más alto y almacenamiento adicional, puede usar el nivel estándar de aprendizaje automático. Este nivel requiere una suscripción a Azure e implica costes adicionales. Para obtener más información sobre los precios de Aprendizaje automático, consulte <http://aka.ms/machine-learning-price-info>.
-   ** Reducción de previsión en cualquier punto de desemparejamiento ** – previsión de demanda en Dynamics 365 para los contratar de las operaciones esta funcionalidad, que le permiten pronosticar el dependiente y la demanda independiente en cualquier punto de desemparejamiento.

## <a name="basic-flow-in-demand-forecasting"></a>Flujo básico en la previsión de demanda
En el siguiente diagrama se muestra el flujo de básico en la previsión de la demanda. 

[gráfico de la introducción de previsión![demanda![] (. /media/demand-forecasting-introduction.png])(. /media/demand-forecasting-introduction.png)

La generación de previsión de la demanda comienza en Dynamics 365 para las operaciones. El datos transaccionales histórico de Dynamics 365 para la base de datos transaccionales de las operaciones se recopilan y rellena una tabla de ensayo. Esta tabla de ensayo se alimenta más tarde a un servicio de aprendizaje de equipo. Al realizar la personalización mínima, puede tapar diferentes orígenes de datos en la tabla de ensayo. Los orígenes de datos pueden incluir los archivos de Microsoft Excel, los archivos de (CSV) de valores separados por comas, y los datos de Microsoft Dynamics AX 2009 y Microsoft Dynamics AX 2012. Por lo tanto, puede generar las previsiones de demanda consideran que los datos histórico que se amplía entre sistemas operaciones. Sin embargo, los datos maestros, como los nombres de artículo y unidades de medida, deben ser iguales en todas las fuentes de datos.

Si usa Dynamics 365 para los unidad de aprendizaje de equipo de previsión de demanda de las operaciones ella, busca un mejor ajuste entre cinco serie temporal qué previsiones métodos para calcular una previsión de línea base. Los parámetros para estos métodos de previsión se administran en Dynamics 365 para las operaciones. 

Las previsiones, los datos históricos, y cualquier modificación que se haya realizado a las previsiones de demanda en iteraciones son anteriores entonces disponible en Dynamics 365 para las operaciones. 

Puede usar Dynamics 365 para que las operaciones y modificadas visualicen las previsiones de línea base. Los ajustes manuales deben estar autorizados antes de que las previsiones se puedan utilizar para la planificación.

## <a name="limitations"></a>Limitaciones
La previsión de demanda en Dynamics 365 para las operaciones es una herramienta que ayuda a clientes en el sector fabril a crear procesos de previsión. Proporciona la funcionalidad básica de una solución de previsión de demanda y está diseñado para que se pueda fácilmente mejorar. La previsión de demanda no podría ser el mejor ajuste para clientes en sectores como ventas al por menor, ventas al por mayor, almacenamiento de datos, transporte, u otros servicios profesionales.

<a name="see-also"></a>Consulte también
--------

[Demand forecasting setup](demand-forecasting-setup.md)

[Generating a statistical baseline forecast](generate-statistical-baseline-forecast.md)

[Making manual adjustments to the baseline forecast](manual-adjustments-baseline-forecast.md)

[Authorizing the adjusted forecast](authorize-adjusted-forecast.md)

[Monitoring forecast accuracy](monitor-forecast-accuracy.md)

[Remove outliers from historical transaction data when calculating a demand forecast](remove-historical-outliers-calculating-demand-forecast.md)


