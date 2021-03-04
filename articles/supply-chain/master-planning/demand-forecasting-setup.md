---
title: Configuración de la previsión de la demanda
description: En este tema se describen las tareas de configuración que debe realizar antes de poder usar la previsión de la demanda.
author: roxanadiaconu
manager: tfehr
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanDefaultAlgorithmParameters, ReqDemPlanForecastParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 72653
ms.assetid: c5fa4b09-512d-4349-ac51-cc13da69a160
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6d0de588d54948d89f636cadeb66c3d9e6878015
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437097"
---
# <a name="demand-forecasting-setup"></a>Configuración de la previsión de la demanda

[!include [banner](../includes/banner.md)]

En este tema se describen las tareas de configuración que debe realizar antes de poder usar la previsión de la demanda.  

Las tareas de configuración incluyen la configuración de los datos y parámetros siguientes.

## <a name="item-allocation-key"></a>Clave de asignación de artículos
Una previsión de la demanda se calcula para un artículo y sus dimensiones únicamente si el artículo es parte de una clave de asignación de artículos. Esta regla se aplica para agrupar un gran número de artículos, para poder crear previsiones de demanda más rápidamente. Se omite el porcentaje de la clave de asignación de artículos cuando se generan previsiones de demanda. Las previsiones se crean únicamente en base a los datos históricos. 

Un artículo y sus dimensiones deben formar parte de una sola clave de asignación de artículos si la clave de asignación de artículos se utiliza durante la creación de la previsión. 

Para agregar una referencia de almacén (SKU) a una clave de asignación de artículos, vaya a **Planificación maestra** &gt; **Configuración** &gt; **Previsión de demanda** &gt; **Claves de asignación de artículos**. Use la página **Asignar artículos** para asignar un artículo a una clave de asignación.

## <a name="intercompany-planning-groups"></a>Grupos de planificación de empresas vinculadas
La previsión de demanda genera previsiones entre empresas. En Dynamics 365 Supply Chain Management, se agrupa a las empresas que se planifican conjuntamente en un grupo de planificación de empresas vinculadas. Para especificar, según la empresa, las claves de asignación de artículos que se deben tener en cuenta para la previsión de demanda, asocie una clave de asignación de artículos con el miembro de planificación de empresas vinculadas del grupo yendo a **Planificación maestra** &gt; **Configuración** &gt; **Grupos de planificación de empresas vinculadas**. 

De forma predeterminada, si no se ha asignado ninguna clave de asignación de artículos a los miembros del grupo de planificación de empresas vinculadas, se calcula una previsión de la demanda para todos los artículos asignados a todas las claves de asignación de artículos de todas las empresas. Las opciones de filtrado adicionales para las empresas y las claves de asignación de artículos están disponibles en la página **Generar la previsión estadística de línea base**. 

Revisión del número de artículos que están previstos. Los artículos innecesarios podrían incrementar los costes cuando se usa el aprendizaje automático de Microsoft Azure.

## <a name="demand-forecasting-parameters"></a>Parámetros de previsión de la demanda
Para configurar los parámetros de previsión de la demanda, vaya a **Planificación maestra** &gt; **Configuración** &gt; **Parámetros de previsión de la demanda**. Dado que la previsión de demanda se realiza entre empresas, la configuración es global. Es decir, la configuración se aplica a todas las empresas. 

La previsión de demanda genera la previsión en cantidades. Por lo tanto, la unidad de medida en la que la cantidad debe ser expresada se debe especificar en el campo **Unidad de previsión de la demanda**. La unidad de medida debe ser única, para ayudar a garantizar que la agregación y la distribución del porcentaje tienen sentido. Para obtener más información sobre la agregación y la distribución de porcentaje, consulte [Realizar ajustes manuales en la previsión de línea base](manual-adjustments-baseline-forecast.md). Para cada unidad de medida que se usa para los SKU que se incluyen en la previsión de demanda, asegúrese de que haya una regla de conversión para la unidad de medida y la unidad de medida de previsión general. Cuando se ejecute la generación de la previsión, se registra la lista de artículos que no tienen una conversión de unidad de medida, de manera que podrá corregir fácilmente la configuración. 

La previsión de demanda se puede usar para hacer una previsión de la demanda dependiente y la demanda independiente. Por ejemplo, si solo se activa la casilla **Pedido de ventas** y si todos los artículos que se consideran para la previsión de demanda son los artículos vendidos, el sistema calculará demanda independiente. Sin embargo, se pueden agregas subcomponentes importantes a las claves de asignación de artículos e incluirlos en la previsión de demanda. En este caso, si se activa la casilla **Línea de producción**, se calcula una previsión dependiente. 

Existen dos métodos para crear una previsión de línea base. Puede usar modelos de previsión por encima de datos históricos, o simplemente copiar sobre los datos históricos en la previsión. El campo **Estrategia de la generación de previsión** permite seleccionar entre estos dos métodos. Para usar los modelos de previsión, seleccione **Aprendizaje automático de Azure**. 

Si hace clic en **Dimensiones de previsión** en el panel izquierdo de la página **Parámetros de previsión de demanda**, también podrá seleccionar el conjunto de dimensiones de previsión que desea usar cuando se genera la previsión de la demanda. Una dimensión de la previsión indica el nivel de detalle para el que se define la previsión. Empresa, sitio y la clave de asignación de artículos son dimensiones obligatorias de previsión, pero también puede generar previsiones en el almacén, estado de inventario, grupo de clientes, cuenta de cliente, país o región, comunidad autónoma y artículo además de todos los niveles de la dimensión de artículo. 

En cualquier momento puede agregar dimensiones de previsión a la lista de dimensiones que se usan para la previsión de demanda. También puede eliminar dimensiones de previsión de la lista. Sin embargo, se perderán los ajustes manuales si agrega o elimina una dimensión de la previsión. 

No todos los artículos se comportan de manera semejante desde una perspectiva de previsión de demanda. Los artículos similares se pueden agrupar en una clave de asignación de artículos, y los parámetros como los tipos de transacción y la configuración del método de previsión se pueden definir por clave de asignación de artículos. Haga clic en **Claves de asignación de artículos** en el panel izquierdo de la página **Parámetros de previsión de demanda**. 

Para generar la previsión, Supply Chain Management usa un servicio web de Aprendizaje automático. Para conectarse con el servicio, debe proporcionar la siguiente información si inicia sesión en Microsoft Azure Machine Learning Studio (clásico):

-   Configurar la clave de la interfaz de programación de aplicaciones (API) de servicio
-   URL del extremo del servicio web
-   Nombre de cuenta de almacenamiento de Azure
-   Clave de cuenta de almacenamiento de Azure

> [!NOTE]
> Solo se requiere el nombre de la cuenta y la clave de almacenamiento de Azure si usa una cuenta personalizada de almacenamiento. Si se implementa la versión local, debe tener una cuenta personalizada de almacenamiento en Azure, de modo que el aprendizaje automático pueda tener acceso a los datos históricos. 

Para crear predicciones de demanda, puede implementar su propio servicio mediante el Estudio de aprendizaje automático o los experimentos de previsión de demanda de Supply Chain Management. Las instrucciones para implementar los experimentos de la previsión de demanda como un servicio web están disponible en Supply Chain Management. En la página **Parámetros de previsión de demanda**, haga clic en la pestaña **Aprendizaje automático de Azure**.

## <a name="settings-for-the-demand-forecasting-machine-learning-service"></a>Configuración del servicio de aprendizaje automático de previsión de demanda
Para ver los parámetros que se pueden configurar para el servicio de previsión de demanda, vaya a **Planificación maestra** &gt; **Configuración** &gt; **Previsión de demanda** &gt; **Parámetros de algoritmo de previsión**. La página **Parámetros de algoritmo de previsión** muestra los valores predeterminados para los parámetros. Puede sobrescribir estos parámetros en la página **Parámetros de previsión de demanda**. Use la pestaña **General** para sobrescribir los parámetros globalmente, o use la pestaña **Claves de asignación de artículos** para sobrescribir los parámetros por clave de asignación de artículo. Los parámetros que se sobrescriben para una clave de asignación de artículos afectan solo a la previsión de los artículos que están asociados con esa clave de asignación de artículos.

### <a name="forecast-algorithm-parameters"></a>Parámetros de algoritmo de previsión

En la pestaña **Claves de asignación** puede establecer los **Parámetros de algoritmo de previsión** para cada clave de asignación de artículos. Están disponibles las siguientes opciones.
- **Porcentaje de nivel de confianza**: Un intervalo de confianza consta de un intervalo de valores que actúan como estimaciones para la previsión de la demanda. Un porcentaje de nivel de confianza del 95 por ciento indica que hay un 5 por ciento de riesgo de que la demanda futura se encuentre fuera del intervalo de confianza.
- **Estacionalidad de la fuerza**: Especifica si desea forzar el modelo para utilizar un tipo determinado de estacionalidad. Sólo es aplicable a ARIMA y ETS. Opciones: AUTO (predeterminado), NINGUNO, ADITIVO, MULTIPLICATIVO.
- **Modelo de previsión**: opciones: ARIMA, ETS, STL, ETS+ARIMA, ETS+STL, ALL. Para seleccionar el modelo que mejor se ajusta, use **ALL**.
- **Valor máximo previsto**: Especifica el valor máximo para utilizar para las predicciones. Formato: +1E[n] o constante numérica.
- **Valor mínimo previsto**: Especifica el valor mínimo para utilizar para las predicciones. Formato: -1E[n] o constante numérica.
- **Sin sustitución de valores**: Especifica cómo los espacios en datos históricos se rellenan. Opciones: valor numérico, MEDIO, ANTERIOR, INTERPOLACIÓN LINEAL, INTERPOLACIÓN POLINOMIAL.
- **Ámbito que falta de la sustitución de valores**: Especifica si la sustitución de valores solo se aplica al intervalo de datos de cada atributo de granularidad individual, o al conjunto de datos completo. Opciones: GRANULARITY_ATTRIBUTE (predeterminado), GLOBAL.
- **Sugerencia de estacionalidad**: Para datos estacionales, proporcione una sugerencia al modelo de previsión para mejorar la precisión de previsión. Formato: número entero, que representa el número de cubos que un patrón de demanda se repite. Por ejemplo, especifique "6 "para los datos que se repiten cada 6 meses.
- **Porcentaje de tamaño de conjunto de pruebas**: porcentaje de datos históricos que se usará como conjunto de prueba para el cálculo de la precisión de la previsión. 

<a name="additional-resources"></a>Recursos adicionales
--------

[Visión general de la previsión de la demanda](introduction-demand-forecasting.md)

[Generar previsión estadística de línea base](generate-statistical-baseline-forecast.md)

[Realización de ajustes manuales en la previsión de línea base](manual-adjustments-baseline-forecast.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]