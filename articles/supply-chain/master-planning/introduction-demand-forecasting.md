---
title: Visión general de previsión de la demanda
description: La previsión de demanda se usa para predecir demanda independiente de pedidos de ventas y demanda dependiente en cualquier momento de desemparejamiento para los pedidos del cliente. Las reglas mejoradas de reducción de la previsión de demanda proporcionan una solución ideal para una personalización global.
author: t-benebo
ms.date: 07/07/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "72004"
- intro-internal
ms.assetid: 916707c9-1333-460f-a0fa-4e95f6fda2ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5c764cc186b5c8742ccfd90b5928f6625f3360c8
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9065625"
---
# <a name="demand-forecasting-overview"></a>Visión general de previsión de la demanda

[!include [banner](../includes/banner.md)]

La previsión de demanda se usa para predecir demanda independiente de pedidos de ventas y demanda dependiente en cualquier momento de desemparejamiento para los pedidos del cliente. Las reglas mejoradas de reducción de la previsión de demanda proporcionan una solución ideal para una personalización global.

Para generar la previsión de línea base, un resumen de transacciones históricas se transfiere a un servicio de aprendizaje automático de Microsoft Azure que está hospedado en Azure. Dado que este servicio no se comparte entre usuarios, puede ser personalizado fácilmente para cumplir los requisitos específicos del sector. Puede usar Supply Chain Management para visualizar la previsión, ajustar la previsión y visualizar los indicadores claves de rendimiento (KPI) acerca de la precisión de la previsión.

> [!NOTE]
> Se requiere Microsoft Azure Machine Learning Studio (clásico) para la generación de pronósticos con aprendizaje automático. A partir del 1 de diciembre de 2021, no podrá crear nuevos recursos de Machine Learning Studio (clásico). Sin embargo, podrá seguir utilizando sus recursos de Machine Learning Studio (clásicos) existentes hasta el 31 de agosto de 2024. Para obtener información actualizada, consulte [Azure Machine Learning Studio](/azure/machine-learning/overview-what-is-machine-learning-studio#ml-studio-classic-vs-azure-machine-learning-studio).
> 
> Dynamics 365 Supply Chain Management, versión 10.0.23 y posteriores, es compatible con el nuevo Azure Machine Learning Studio.

## <a name="key-features-of-demand-forecasting"></a>Características clave de previsión de demanda

Estas son algunas de las características principales de la previsión de demanda:

- Generación de una previsión estadística de línea base basada en datos históricos.
- Uso de un sistema dinámico de dimensiones de previsión.
- Visualización de tendencias de demanda, intervalos de confianza y ajustes de la previsión.
- Autorización de la previsión ajustada para usar en procesos de planificación.
- Eliminación de valores atípicos.
- Crear medidas de precisión de la previsión.

## <a name="major-themes-in-demand-forecasting"></a>Temas principales en la previsión de demanda

Se implementan tres temas principales en la previsión de demanda:

- **Modularidad:** la previsión de demanda es modular y fácil de configurar. Puede activar y desactivar la funcionalidad cambiando la clave de configuración en **Comercio** &gt; **Previsión de inventario** &gt; **Previsión de demanda**.
- **Reutilizar Microsoft Stack**: el aprendizaje automático, que ahora es parte de Microsoft Cortana Analytics Suite, le permite crear rápida y fácilmente experimentos de análisis de previsión, como experimentos de estimación de demanda, mediante los algoritmos R o los lenguajes de programación de Python y una interfaz simple de arrastrar y soltar.
  - Puede descargar los experimentos de previsión de demanda, modificarlos para satisfacer sus requisitos empresariales, publicarlos como un servicio web en Azure y utilizarlos para generar las previsiones de demanda. Los experimentos están disponibles para descargar si ha comprado una suscripción a Supply Chain Management para un planificador de producción como usuario de nivel empresarial.
  - Puede descargar cualquiera de los experimentos de previsión de demanda actualmente disponibles en [Galería de análisis de Cortana](https://gallery.cortanaanalytics.com/). Mientras que los experimentos de previsión de demanda se integran automáticamente con Supply Chain Management, los clientes y los asociados deben gestionar la integración de los experimentos que descargan en [Galería de análisis de Cortana](https://gallery.cortanaanalytics.com/). Por tanto, los experimentos de la [Galería de análisis de Cortana](https://gallery.cortanaanalytics.com/) no son tan sencillos de usar como los experimentos de la previsión de demanda de finanzas y operaciones. Debe modificar el código de los experimentos de modo que usen la interfaz de programación de aplicaciones (API) de finanzas y operaciones.
  - Puede crear sus propios experimentos en Microsoft Azure Machine Learning Studio (classic), publicarlos como servicios en Azure, y utilizarlos para generar las previsiones de demanda.
  - Si no necesita alto rendimiento, o si no necesita procesar grandes cantidades de datos, puede usar el nivel libre de aprendizaje automático. Recomendamos que comience siempre desde este nivel, especialmente durante las fases de implementación y de pruebas. Si necesita un rendimiento más alto y almacenamiento adicional, puede usar el nivel estándar de aprendizaje automático. Este nivel requiere una suscripción a Azure e implica costes adicionales. Para obtener más información sobre los precios de Aprendizaje automático, consulte [Precios de Machine Learning Studio](https://aka.ms/machine-learning-price-info).
- **Reducción de previsión en cualquier momento de desemparejamiento:** previsión de demanda en esta función, que le permite realizar una previsión de demanda dependiente e independiente en cualquier momento de desemparejamiento.

## <a name="basic-flow-in-demand-forecasting"></a>Flujo básico en la previsión de demanda

En el siguiente diagrama se muestra el flujo de básico en la previsión de la demanda.

[![diagrama de introducción a la previsión de la demanda.](./media/demand-forecasting-introduction.png)](./media/demand-forecasting-introduction.png)

La generación de la previsión de demanda comienza con Supply Chain Management. Los datos históricos de transacción de la base de datos de transacciones de Supply Chain Management se recopilan y rellenan una tabla provisional. Esta tabla provisional se alimenta más tarde a un servicio de aprendizaje automático. Con una personalización mínima, puede conectar varios orígenes de datos a la tabla provisional. Los orígenes de datos pueden incluir los archivos Microsoft Excel , los archivos de (CSV) de valores separados por comas, y los datos Microsoft Dynamics AX 2009 y Microsoft Dynamics AX 2012. Por lo tanto, puede generar las previsiones de demanda que tienen en cuenta los datos históricos que aparecen en varios sistemas. Sin embargo, los datos maestros, como los nombres de artículo y unidades de medida, deben ser iguales en todas las fuentes de datos.

Si usa los experimentos de aprendizaje automático de previsión de demanda, se busca un mejor ajuste entre cinco métodos de previsión de serie de tiempo para calcular una previsión de línea base. Los parámetros para estos métodos de previsión se gestionan en Supply Chain Management.

Las previsiones, los datos históricos y los cambios que se hayan realizado a las previsiones de demanda en iteraciones anteriores estarán disponibles en Supply Chain Management.

Puede usar Supply Chain Management para visualizar y modificar las previsiones de línea base. Los ajustes manuales deben estar autorizados antes de que las previsiones se puedan utilizar para la planificación.

## <a name="limitations"></a>Limitaciones

La previsión de demanda es una herramienta que ayuda a los clientes en el sector de fabricación a crear procesos de previsión. Ofrece la función básica de una solución de previsión de demanda y se diseña de modo que pueda extenderse fácilmente. La previsión de demanda puede que no sea el mejor ajuste para clientes en sectores como Commerce, venta al por mayor, almacenamiento, transporte u otros servicios profesionales.

### <a name="demand-forecast-variant-conversion-limitation"></a>Limitación de conversión de variante de previsión de la demanda

La conversión de unidad de medida (UOM) por variante no es totalmente compatible cuando se genera una previsión de la demanda si el UOM de inventario es diferente del UOM de la previsión de la demanda.

La generación de previsión (**UOM de inventario > UOM de previsión de la demanda**) utiliza la conversión UOM del producto. Al cargar datos históricos para la generación de previsión de la demanda, la conversión de UOM a nivel de producto siempre se usará al convertir de UOM de inventario a UOM de previsión de la demanda, incluso si hay conversiones definidas en el nivel de variante.

La primera parte del pronóstico de autorización (**Previsión de demanda UOM > UOM de inventario**) utiliza la conversión de UOM del producto. La segunda parte del pronóstico de autorización (**UOM de inventario > UOM de ventas**) utiliza la conversión UOM de variante. Cuando se autoriza el pronóstico de demanda generado, la conversión a UOM de inventario desde el UOM de previsión de la demanda se realizará utilizando la conversión de UOM a nivel de producto. Al mismo tiempo, la conversión entre la unidad de inventario y la UOM de ventas respetará las conversiones definidas de nivel de variante.

Tenga en cuenta que el UOM de pronóstico de demanda no tiene que tener ningún significado específico. Se puede definir como “Unidad de previsión de la demanda”. Para cada uno de los productos, puede definir que la conversión sea 1:1 con la UOM de inventario.

## <a name="additional-resources"></a>Recursos adicionales

- [Configuración de previsión de demanda](demand-forecasting-setup.md)
- [Generar previsión estadística de línea base](generate-statistical-baseline-forecast.md)
- [Realización de ajustes manuales en la previsión de línea base](manual-adjustments-baseline-forecast.md)
- [Autorizar previsión de la demanda ajustada](authorize-adjusted-forecast.md)
- [Supervisión de la precisión de previsión](monitor-forecast-accuracy.md)
- [Eliminación de valores atípicos de los datos de transacción históricos al calcular una previsión de la demanda](remove-historical-outliers-calculating-demand-forecast.md)
- [Vídeo: Amplíe la funcionalidad de previsión de demanda](https://www.youtube.com/watch?v=4OIKIXLiNjI&feature=youtu.be)
- [Webinar: Azure Machine Learning Series para previsión de demanda](https://aka.ms/DemandForecastingwithAzureMachineLearningSeries)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

