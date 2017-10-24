---
title: "Configuración de la previsión de la demanda"
description: "En este tema se describen las tareas de configuración que debe realizar antes de poder usar la previsión de la demanda."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqDemPlanDefaultAlgorithmParameters, ReqDemPlanForecastParameters
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 72653
ms.assetid: c5fa4b09-512d-4349-ac51-cc13da69a160
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 905794e39933c9788a7ff5247807baf0ebb807d8
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="demand-forecasting-setup"></a>Configuración de la previsión de la demanda

[!include[banner](../includes/banner.md)]


En este tema se describen las tareas de configuración que debe realizar antes de poder usar la previsión de la demanda.  

Las tareas de configuración incluyen la configuración de los datos y parámetros siguientes.

## <a name="item-allocation-key"></a>Clave de asignación de artículos
Una previsión de la demanda se calcula para un artículo y sus dimensiones únicamente si el artículo es parte de una clave de asignación de artículos. Esta regla se aplica para agrupar un gran número de artículos, para poder crear previsiones de demanda más rápidamente. Se omite el porcentaje de la clave de asignación de artículos cuando se generan previsiones de demanda. Las previsiones se crean únicamente en base a los datos históricos. 

Un artículo y sus dimensiones deben formar parte de una sola clave de asignación de artículos si la clave de asignación de artículos se utiliza durante la creación de la previsión. 

Para agregar una referencia de almacén (SKU) a una clave de asignación de artículos, vaya a **Planificación maestra** &gt; **Configuración** &gt; **Previsión de demanda** &gt; **Claves de asignación de artículos**. Use la página **Asignar artículos** para asignar un artículo a una clave de asignación.

## <a name="intercompany-planning-groups"></a>Grupos de planificación de empresas vinculadas
La previsión de demanda genera previsiones entre empresas. En Microsoft Dynamics 365 for Finance and Operations, se agrupa a las empresas que se planifican conjuntamente en un grupo de planificación de empresas vinculadas. Para especificar, según la empresa, las claves de asignación de artículos que se deben tener en cuenta para la previsión de demanda, asocie una clave de asignación de artículos con el miembro de planificación de empresas vinculadas del grupo yendo a **Planificación maestra** &gt; **Configuración** &gt; **Grupos de planificación de empresas vinculadas**. 

De forma predeterminada, si no se ha asignado ninguna clave de asignación de artículos a los miembros del grupo de planificación de empresas vinculadas, se calcula una previsión de la demanda para todos los artículos asignados a todas las claves de asignación de artículos de todas las empresas de Dynamics 365 for Finance and Operations. Las opciones de filtrado adicionales para las empresas y las claves de asignación de artículos están disponibles en la página **Generar la previsión estadística de línea base**. 

Revisión del número de artículos que están previstos. Los artículos innecesarios podrían incrementar los costes cuando se usa el aprendizaje automático de Microsoft Azure.

## <a name="demand-forecasting-parameters"></a>Parámetros de previsión de la demanda
Para configurar los parámetros de previsión de la demanda, vaya a **Planificación maestra** &gt; **Configuración** &gt; **Parámetros de previsión de la demanda**. Dado que la previsión de demanda se realiza entre empresas, la configuración es global. Es decir, la configuración se aplica a todas las empresas. 

La previsión de demanda genera la previsión en cantidades. Por lo tanto, la unidad de medida en la que la cantidad debe ser expresada se debe especificar en el campo **Unidad de previsión de la demanda**. La unidad de medida debe ser única, para ayudar a garantizar que la agregación y la distribución del porcentaje tienen sentido. Para obtener más información sobre la agregación y la distribución de porcentaje, consulte [Realizar ajustes manuales en la previsión de línea base](manual-adjustments-baseline-forecast.md). Para cada unidad de medida que se usa para los SKU que se incluyen en la previsión de demanda, asegúrese de que haya una regla de conversión para la unidad de medida y la unidad de medida de previsión general. Cuando se ejecute la generación de la previsión, se registra la lista de artículos que no tienen una conversión de unidad de medida, de manera que podrá corregir fácilmente la configuración. 

La previsión de demanda se puede usar para hacer una previsión de la demanda dependiente y la demanda independiente. Por ejemplo, si solo se activa la casilla **Pedido de ventas** y si todos los artículos que se consideran para la previsión de demanda son los artículos vendidos, el sistema calculará demanda independiente. Sin embargo, se pueden agregas subcomponentes importantes a las claves de asignación de artículos e incluirlos en la previsión de demanda. En este caso, si se activa la casilla **Línea de producción**, se calcula una previsión dependiente. 

Existen dos métodos para crear una previsión de línea base en Dynamics 365 for Finance and Operations. Puede usar modelos de previsión por encima de datos históricos, o simplemente copiar sobre los datos históricos en la previsión. El campo **Estrategia de la generación de previsión** permite seleccionar entre estos dos métodos. Para usar los modelos de previsión, seleccione **Aprendizaje automático de Azure**. 

Si hace clic en **Dimensiones de previsión** en el panel izquierdo de la página **Parámetros de previsión de demanda**, también podrá seleccionar el conjunto de dimensiones de previsión que desea usar cuando se genera la previsión de la demanda. Una dimensión de la previsión indica el nivel de detalle para el que se define la previsión. Empresa, sitio y la clave de asignación de artículos son dimensiones obligatorias de previsión, pero también puede generar previsiones en el almacén, estado de inventario, grupo de clientes, cuenta de cliente, país o región, comunidad autónoma y artículo además de todos los niveles de la dimensión de artículo. 

En cualquier momento puede agregar dimensiones de previsión a la lista de dimensiones que se usan para la previsión de demanda. También puede eliminar dimensiones de previsión de la lista. Sin embargo, se perderán los ajustes manuales si agrega o elimina una dimensión de la previsión. 

No todos los artículos se comportan de manera semejante desde una perspectiva de previsión de demanda. Los artículos similares se pueden agrupar en una clave de asignación de artículos, y los parámetros como los tipos de transacción y la configuración del método de previsión se pueden definir por clave de asignación de artículos. Haga clic en **Claves de asignación de artículos** en el panel izquierdo de la página **Parámetros de previsión de demanda**. 

Para generar la previsión, Dynamics 365 for Finance and Operations usa un servicio web de Aprendizaje automático. Para conectarse con el servicio, debe proporcionar a Dynamics 365 for Finance and Operations la siguiente información si inicia sesión en Estudio de aprendizaje automático de Microsoft Azure.

-   Configurar la clave de la interfaz de programación de aplicaciones (API) de servicio
-   URL del extremo del servicio web
-   Nombre de cuenta de almacenamiento de Azure
-   Clave de cuenta de almacenamiento de Azure

**Nota:** solo se requiere el nombre de la cuenta y la clave de almacenamiento de Azure si usa una cuenta personalizada de almacenamiento. Si se implementa la versión local, debe tener una cuenta personalizada de almacenamiento en Azure, de modo que el servicio de aprendizaje automático pueda tener acceso a los datos históricos. 

Para crear predicciones de demanda, puede implementar su propio servicio mediante el Estudio de aprendizaje automático o los experimentos de previsión de demanda de Finance and Operations. Las instrucciones para implementar los experimentos de la previsión de demanda de Finance and Operations como un servicio web están disponible en Finance and Operations. En la página **Parámetros de previsión de demanda**, haga clic en la pestaña **Aprendizaje automático de Azure**.

## <a name="settings-for-the-finance-and-operations-demand-forecasting-machine-learning-service"></a>Configuración del servicio de aprendizaje automático de previsión de demanda de Finance and Operations
Para ver los parámetros que se pueden configurar para el servicio de previsión de demanda de Finance and Operations, vaya a **Planificación maestra** &gt; **Configuración** &gt; **Previsión de demanda** &gt; **Parámetros de algoritmo de previsión**. La página **Parámetros de algoritmo de previsión** muestra los valores predeterminados para los parámetros. Puede sobrescribir estos parámetros en la página **Parámetros de previsión de demanda**. Use la pestaña **General** para sobrescribir los parámetros globalmente, o use la pestaña **Claves de asignación de artículos** para sobrescribir los parámetros por clave de asignación de artículo. Los parámetros que se sobrescriben para una clave de asignación de artículos afectan solo a la previsión de los artículos que están asociados con esa clave de asignación de artículos.

<a name="see-also"></a>Consulte también
--------

[Introducción a la previsión de demanda](introduction-demand-forecasting.md)

[Generación de una previsión estadística de línea base](generate-statistical-baseline-forecast.md)

[Realización de ajustes manuales realizados en la previsión de línea base](manual-adjustments-baseline-forecast.md)




