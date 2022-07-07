---
title: Configuración de la previsión de la demanda
description: En este artículo se describen las tareas de configuración que debe realizar antes de poder usar la previsión de la demanda.
author: t-benebo
ms.date: 11/23/2021
ms.topic: article
ms.search.form: ReqDemPlanDefaultAlgorithmParameters, ReqDemPlanForecastParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fae2ac53dec8696075e7506d979c1cf9fb277af5
ms.sourcegitcommit: d98ecbd9457197ec8f8e281f9c2f24dcce7b8269
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2022
ms.locfileid: "8960189"
---
# <a name="demand-forecasting-setup"></a>Configuración de la previsión de la demanda

[!include [banner](../includes/banner.md)]

Este artículo describe cómo configurar previsiones de demanda.  

## <a name="item-allocation-keys"></a>Claves de asignación por artículos

Las claves de asignación de artículos establecen grupos de artículos. Una previsión de la demanda se calcula para un artículo y sus dimensiones únicamente si el artículo es parte de una clave de asignación de artículos. Esta regla se aplica para agrupar un gran número de artículos, para poder crear previsiones de demanda más rápidamente. Las previsiones se crean únicamente en base a los datos históricos.

Un artículo y sus dimensiones deben formar parte de una sola clave de asignación de artículos si la clave de asignación de artículos se utiliza durante la creación de la previsión.

Para crear claves de asignación de artículos y agregarles una referencia de almacén (SKU), siga estos pasos.

1. Vaya a **Planificacion maestra \> Configuración \> Previsión de demanda \> Claves de asignación de artículos**.
1. Seleccione una clave de asignación de artículos en el panel de lista o seleccione **Nuevo** en el Panel de acciones para crear una nueva. En el encabezado de la clave nueva o seleccionada, establezca los siguientes campos:

    - **Clave de asignación de artículos** - Ingrese un nombre único para la clave.
    - **Nombre** - Especifique un nombre descriptivo para la clave.

1. Siga uno de estos pasos para agregar artículos a la clave de asignación de artículos seleccionada o eliminar artículos:

    - En la ficha desplegable **Asignación de artículos**, utilice los botones **Nuevo** y **Eliminar** de la barra de herramientas para agregar y eliminar artículos según sea necesario. Para cada fila, seleccione el número de artículo y luego asigne valores de dimensión en las otras columnas según lo requiera. Seleccione **Mostrar dimensiones** en la barra de herramientas para cambiar el conjunto de columnas de dimensión que se muestra en la cuadrícula. (Se ignora el valor de la columna **Porcentaje** cuando se generan previsiones de demanda.)
    - Si desea agregar una gran cantidad de artículos a la clave, seleccione **Asignar artículos** en el Panel de acciones para abrir una página donde puede buscar y asignar varios elementos a la tecla seleccionada.

> [!IMPORTANT]
> Tenga cuidado de incluir solo artículos relevantes en cada clave de asignación de artículos. Los artículos innecesarios podrían incrementar los costes cuando se usa el aprendizaje automático de Microsoft Azure.

## <a name="intercompany-planning-groups"></a>Grupos de planificación de empresas vinculadas

La previsión de demanda puede generar previsiones entre empresas. En Dynamics 365 Supply Chain Management, se agrupa a las empresas que se planifican conjuntamente en el mismo grupo de planificación de empresas vinculadas. Para especificar, por empresa, qué claves de asignación de artículos se deben considerar para la previsión de la demanda, asocie una clave de asignación de artículos con el miembro del grupo de planificación de empresas vinculadas.

> [!IMPORTANT]
> Actualmente, Optimización de planificación no admite grupos de planificación de empresas vinculadas. Para realizar planificación de empresas vinculadas que utilice Optimización de planificación, configure trabajos por lotes de planificación maestra que incluyan planes maestros para todas las empresas relevantes.

Siga estos pasos para configurar sus grupos de planificación de empresas vinculadas.

1. Vaya a **Planificación maestra \> Configuración \> Grupos de planificación de empresas vinculadas**.
1. Seleccione un grupo de planificación en el panel de lista o seleccione **Nuevo** en el Panel de acciones para crear uno nuevo. En el encabezado del grupo nuevo o seleccionado, establezca los siguientes campos:

    - **Nombre** – Especifique un nombre único para el grupo de planificación.
    - **Descripción**: escriba una breve descripción del grupo de planificación.

1. En la ficha desplegable **Miembros del grupo de planificación de empresas vinculadas**, utilice los botones de la barra de herramientas para agregar una fila para cada empresa (entidad jurídica) que debería formar parte del grupo. Para cada fila, establezca los siguientes campos:

    - **Entidad jurídica** - Seleccione el nombre de una empresa (entidad jurídica) que sea miembro del grupo seleccionado.
    - **Secuencia de programación** - Asigne el orden en el que debe tramitarse la empresa en relación con otras empresas. Los valores bajos se procesan primero. Este orden puede ser importante cuando la demanda de una empresa afecta a otras empresas. En estos casos, la empresa que abastece la demanda debe ser procesada en último lugar.
    - **Plan maestro** - seleccione el plan maestro para desencadenar la empresa actual.
    - **Copia automática a plan estático** - Seleccione esta casilla de verificación para copiar el resultado del plan al plan estático.
    - **Copia automática a plan dinámico** - Seleccione esta casilla de verificación para copiar el resultado del plan al plan dinámico.

1. De forma predeterminada, si no se ha asignado ninguna clave de asignación de artículos a los miembros del grupo de planificación de empresas vinculadas, se calcula una previsión de la demanda para todos los artículos asignados a todas las claves de asignación de artículos de todas las empresas. Las opciones de filtrado adicionales para empresas y claves de asignación de artículos están disponibles en el cuadro de diálogo **Generar previsión estadística de línea base** (**Planificación maestra \> Previsión \> Previsión de demanda \> Generar previsión estadística de línea base**). Para asignar claves de asignación de artículos a una empresa en el grupo de planificación de empresas vinculadas seleccionado, seleccione la empresa y, a continuación, en la ficha desplegable **Miembros del grupo de planificación de empresas vinculadas**, seleccione **Claves de asignación de artículos** en la barra de herramientas.

> [!IMPORTANT]
> Tenga cuidado de incluir solo claves de asignación de artículos relevantes en cada grupo de planificación de empresas vinculadas. Los artículos innecesarios podrían incrementar los costes cuando se usa Azure Machine Learning.

## <a name="set-up-demand-forecasting-parameters"></a><a name="parameters"></a>Configuración de parámetros de previsión de demanda

Utilice la página **Parámetros de previsión de demanda** para configurar varias opciones que controlan cómo funcionará la previsión de la demanda en su sistema.

### <a name="open-the-demand-forecasting-parameters-page"></a>Abra la página Parámetros de previsión de demanda

Para configurar parámetros de previsión de demanda, vaya a **Planificación maestra \> Configuración \> Previsión de la demanda \> Parámetros de previsión de la demanda**. Dado que la previsión de demanda se realiza entre empresas, la configuración es global. Es decir, se aplica a todas las entidades jurídicas (empresas).

### <a name="general-settings"></a>Configuración general

Utilice la página **General** de la página **Parámetros de previsión de demanda** para definir la configuración general para la previsión de demanda.

#### <a name="demand-forecast-unit"></a>Unidad de previsión de la demanda

La previsión de demanda genera la previsión en cantidades. Por lo tanto, la unidad de medida en la que la cantidad debe ser expresada se debe especificar en el campo **Unidad de previsión de la demanda**. Este campo define la unidad que se utilizará para todas las previsiones de demanda, independientemente de las unidades de inventario habituales para cada producto. Si utiliza una unidad de previsión coherente, contribuye a garantizar que la agregación y la distribución del porcentaje tienen sentido. Para obtener más información sobre la agregación y la distribución de porcentaje, consulte [Realizar ajustes manuales en la previsión de línea base](manual-adjustments-baseline-forecast.md).

Para cada unidad de medida que se usa para los SKU que se incluyen en la previsión de demanda, asegúrese de que haya una regla de conversión para la unidad de medida y la unidad de medida de previsión general que seleccione aquí. Cuando genere una previsión, se registra la lista de artículos que no tienen una conversión de unidad de medida. Por lo tanto, puede corregir fácilmente la configuración. Para obtener más información sobre unidades de medida y cómo realizar la conversión entre ellas, consulte [Gestionar unidades de medida](../pim/tasks/manage-unit-measure.md).

#### <a name="transaction-types"></a>Tipos de transacciones

Utilice los campos de la ficha desplegable **Tipos de transacciones** para seleccionar los tipos de transacciones que se utilizan cuando se genera la previsión de referencia estadística.

La previsión de demanda se puede usar para hacer una previsión de la demanda dependiente y la demanda independiente. Por ejemplo, si solo se establece la opción **Pedido de ventas** como *Sí* y todos los artículos que se consideran para la previsión de demanda son los artículos vendidos, el sistema calculará demanda independiente. Sin embargo, se pueden agregas subcomponentes importantes a las claves de asignación de artículos e incluirlos en la previsión de demanda. En este caso, si establece la opción **Línea de producción** en *Sí*, se calcula una previsión dependiente.

Puede reemplazar los tipos de transacciones para una o más claves de asignación de artículos específicos utilizando la pestaña **Claves de asignación de artículos**. Esa pestaña proporciona campos similares.

#### <a name="choose-how-to-create-the-baseline-forecast"></a>Elija cómo crear la previsión de línea base

El campo **Estrategia de generación de previsión** le permite seleccionar el método que se utiliza para crear una previsión de línea base. Hay tres métodos disponibles:

- *Copiar sobre demanda histórica* - Cree pronósticos simplemente copiando datos históricos.
- *Azure Machine Learning Service* - Utilice un modelo de previsión que utilice Azure Machine Learning Service. Azure Machine Learning Service es la solución de aprendizaje automático actual para Azure. Por lo tanto, le recomendamos que lo utilice si desea utilizar un modelo de previsión.
- *Azure Machine Learning* - Utilice un modelo de previsión que utilice Azure Machine Learning Studio (clásico). Azure Machine Learning Studio (clásico) ha quedado obsoleto y pronto se eliminará de Azure. Por lo tanto, le recomendamos que seleccione *Azure Machine Learning Service* si está configurando previsión de demanda por primera vez. Si actualmente usa Azure Machine Learning Studio (clásico), debe planear el cambio a Azure Machine Learning Service lo antes posible.

Puede reemplazar el método de generación de previsión para una o más claves de asignación de artículos específicos utilizando la pestaña **Claves de asignación de artículos**. Esa pestaña proporciona campos similares.

#### <a name="override-default-forecast-algorithm-parameters-globally"></a>Reemplazar los parámetros del algoritmo de previsión predeterminado globalmente

Los parámetros y valores predeterminados del algoritmo de previsión se asignan en la página **Parámetros de previsión de la demanda** (**Planificación maestra \> Configuración \> Previsión de demanda \> Parámetros de previsión de demanda**). Sin embargo, puede reemplazarlos globalmente utilizando la ficha desplegable **Parámetros del algoritmo de previsión** en la pestaña **General** de la página **Parámetros de previsión de demanda**. (También puede reemplazarlos para claves de asignación específicas utilizando la pestaña **Claves de asignación de artículos** en la página **Parámetros de previsión de demanda**.)

Utilice los botones **Agregar** y **Eliminar** en la barra de herramientas para establecer la colección requerida de reemplazos de parámetros. Para cada parámetro de la lista, seleccione un valor en el campo **Nombre** y luego especifique un valor apropiado en el campo **Valor**. Todos los parámetros que no se enumeran aquí tomarán sus valores de la configuración de la página **Parámetros de previsión de demanda**. Para obtener más información sobre cómo utilizar el conjunto estándar de parámetros y seleccionar valores para ellos, consulte la sección [Parámetros y valores predeterminados para modelos de previsión de demanda](#model-parameters).

### <a name="set-forecast-dimensions"></a>Establecer dimensiones de previsión

Una dimensión de la previsión indica el nivel de detalle para el que se define la previsión. Empresa, sitio y clave de asignación de artículos son dimensiones de previsión necesarias. También puede generar previsiones en el almacén, estado de inventario, grupo de clientes, cuenta de cliente, país o región, comunidad autónoma y/o artículo, además de todos los niveles de la dimensión de artículo. Utilice la pestaña **Dimensiones de previsión** de la página **Parámetros de previsión de demanda** para seleccionar el conjunto de dimensiones de previsión que se usa cuando se genera la previsión de la demanda.

En cualquier momento puede agregar dimensiones de previsión a la lista de dimensiones que se usan para la previsión de demanda. También puede eliminar dimensiones de previsión de la lista. Sin embargo, se perderán los ajustes manuales si agrega o elimina una dimensión de la previsión.

### <a name="set-up-overrides-for-specific-item-allocation-keys"></a>Configurar reemplazos para claves de asignación de artículos específicos

No todos los artículos se comportan de la misma manera desde una perspectiva de previsión de demanda. Por lo tanto, puede establecer reemplazos específicos de claves de asignación para la mayoría de las configuraciones que se definen en la pestaña **General**. La excepción es la unidad de previsión de demanda. Para configurar reemplazos para una clave de asignación de artículos específica, siga estos pasos.

1. En la página **Parámetros de previsión de demanda**, en la pestaña **Claves de asignación de artículos**, use los botones de la barra de herramientas para agregar claves de asignación de artículos a la cuadrícula de la izquierda, o elimínelas, según lo requiera. Luego, seleccione la clave de asignación para la que desea configurar reemplazos.
1. En la ficha desplegable **Tipos de transacciones**, habilite los tipos de transacciones que desea utilizar para generar la previsión estadística de línea base para los productos que pertenecen a la clave de asignación seleccionada. Los ajustes funcionan igual que en la pestaña **General**, pero se aplican solo a la clave de asignación de artículos seleccionada. Todos los ajustes aquí (tanto los valores *Sí* como los valores *No*) reemplazan a todos los ajustes de **Tipos de transacciones** en la pestaña **General**.
1. En la ficha desplegable **Parámetros del algoritmo de previsión**, seleccione la estrategia de generación de previsión y los reemplazos de parámetros del algoritmo de previsión para los productos que pertenecen a la clave de asignación seleccionada. Estos ajustes funcionan igual que en la pestaña **General**, pero se aplican solo a la clave de asignación de artículos seleccionada. Utilice los botones **Agregar** y **Eliminar** en la barra de herramientas para definir la colección requerida de reemplazos de parámetros. Para cada parámetro de la lista, seleccione un valor en el campo **Nombre** y luego especifique un valor apropiado en el campo **Valor**. Para obtener más información sobre cómo utilizar el conjunto estándar de parámetros y seleccionar valores para ellos, consulte la sección [Parámetros y valores predeterminados para modelos de previsión de demanda](#model-parameters).

### <a name="set-up-the-connection-to-the-azure-machine-learning-service"></a>Configurar la conexión con Azure Machine Learning Service

Utilice la pestaña **Azure Machine Learning Service** para configurar la conexión con Azure Machine Learning Service. Esta solución es una de las opciones para crear la previsión de línea base. Estos ajustes de esta pestaña tienen efecto solo cuando el campo **Estrategia de generación de previsión** está configurado en *Azure Machine Learning Service*.

Para obtener más información sobre cómo configurar Azure Machine Learning Service y luego usar la configuración aquí para conectarse a él, consulte la sección [Configurar Azure Machine Learning Service](#setup-amls).

### <a name="set-up-the-connection-to-azure-machine-learning-studio-classic"></a>Configurar la conexión con Azure Machine Learning Studio (clásico)

> [!IMPORTANT]
> Azure Machine Learning Studio (clásico) ha quedado obsoleto. Por tanto, ya no puede crear nuevos espacios de trabajo para él en Azure. Ha sido reemplazado por Azure Machine Learning Service, que proporciona una funcionalidad similar y más. Si aún no usa Azure Machine Learning, debe comenzar a usar Azure Machine Learning Service. Si ya tiene un espacio de trabajo que se creó para Azure Machine Learning Studio (clásico), puede continuar usándolo hasta que la característica se elimine por completo de Azure. Sin embargo, le recomendamos que actualice a Azure Machine Learning Service lo antes posible. Aunque la aplicación seguirá advirtiéndole que Azure Machine Learning Studio (clásico) ha quedado obsoleto, el resultado de la previsión no se verá afectado. Para obtener más información el nuevo Azure Machine Learning Service y cómo configurarlo, consulte la sección [Configurar Azure Machine Learning Service](#setup-amls).
>
> Puede cambiar libremente entre el uso de las soluciones de aprendizaje automático nuevas y antiguas con Supply Chain Management mientras su antiguo espacio de trabajo de Azure Machine Learning Studio (clásico) permanezca disponible.

Si ya tiene un espacio de trabajo de Azure Machine Learning Studio (clásico) disponible, puede usarlo para generar previsiones conectándolo a Supply Chain Management. Puede establecer esta conexión utilizando la pestaña **Azure Machine Learning** en la página **Parámetros de previsión de demanda**. (Los ajustes de esta pestaña tienen efecto solo cuando el campo **Estrategia de generación de previsión** está configurado en *Azure Machine Learning* .) Ingrese los siguientes detalles para su área de trabajo de Azure Machine Learning Studio (clásico):

- Configurar la clave de la interfaz de programación de aplicaciones (API) de servicio
- URL del extremo del servicio web
- Nombre de cuenta de almacenamiento de Azure
- Clave de cuenta de almacenamiento de Azure

> [!NOTE]
> Solo se requiere el nombre de la cuenta y la clave de almacenamiento de Azure si usa una cuenta personalizada de almacenamiento. Si se implementa la versión local, debe tener una cuenta personalizada de almacenamiento en Azure, de modo que el aprendizaje automático pueda tener acceso a los datos históricos.

## <a name="default-parameters-and-values-for-demand-forecasting-models"></a><a name="model-parameters"></a>Parámetros y valores predeterminados para modelos de previsión de demanda

Cuando utiliza aprendizaje automático para generar modelos de planificación de previsión, controla las opciones de aprendizaje automático estableciendo valores para *parámetros de algoritmo de previsión*. Estos valores se envían desde Supply Chain Management a Azure Machine Learning. Utilice la página **Parámetros de algoritmo de previsión** para controlar qué tipos de valores deben proporcionarse y qué valores debe tener cada uno.

Para configurar los parámetros y los valores predeterminados utilizados para modelos de previsión de demanda, vaya a **Planificación maestra \> Configuración \> Previsión de demanda \> Parámetros de algoritmo de previsión**. Se proporciona un conjunto estándar de parámetros. Cada parámetro tiene los siguientes campos:

- **Nombre** - El nombre del parámetro, tal como lo usa Azure. Por lo general, no debe cambiar este nombre a menos que haya personalizado el experimento en Azure Machine Learning.
- **Descripción** - Un nombre común para el parámetro. Este nombre se utiliza para identificar el parámetro en otros lugares del sistema (por ejemplo, en la página **Parámetros de previsión de demanda**).
- **Valor** - El valor predeterminado del parámetro. El valor que debe ingresar depende del parámetro que esté editando. 
- **Explicación** - Una breve descripción del parámetro y cómo utilizarlo. Esta descripción normalmente incluye consejos sobre valores válidos para el campo **Valor**.

Los siguientes parámetros se proporcionan de forma predeterminada. (Si alguna vez debe revertir a esta lista estándar, seleccione **Restaurar** en el Panel de acciones.)

- **Porcentaje de nivel de confianza**: Un intervalo de confianza consta de un intervalo de valores que actúan como estimaciones para la previsión de la demanda. Un porcentaje de nivel de confianza del 95 por ciento indica que hay un 5 por ciento de riesgo de que la demanda futura se encuentre fuera del intervalo de confianza.
- **Estacionalidad de la fuerza**: Especifica si desea forzar el modelo para utilizar un tipo específico de estacionalidad. Este parámetro se aplica solo a ARIMA y ETS. Opciones: *AUTO (predeterminado)*, *NINGUNO*, *ADITIVO*, *MULTIPLICATIVO*.
- **Modelo de previsión** - Especifica qué modelo de previsión usar. Opciones: *ARIMA*, *ETS*, *STL*, *ETS+ARIMA*, *ETS+STL*, *ALL*. Para seleccionar el modelo que mejor se ajusta, use *ALL*.
- **Valor máximo previsto**: Especifica el valor máximo para utilizar para las predicciones. Formato: +1E[n] o constante numérica.
- **Valor mínimo previsto**: Especifica el valor mínimo para utilizar para las predicciones. Formato: -1E[n] o constante numérica.
- **Sin sustitución de valores**: Especifica cómo los espacios en datos históricos se rellenan. Opciones: *(valor numérico)*, *MEDIO*, *ANTERIOR*, *INTERPOLACIÓN LINEAL*, *INTERPOLACIÓN POLINOMIAL*.
- **Ámbito que falta de la sustitución de valores**: Especifica si la sustitución de valores solo se aplica al intervalo de fechas de cada atributo de granularidad individual, o al conjunto de datos completo. Las siguientes opciones están disponibles para establecer el rango de fechas que utiliza el sistema al completar los vacíos en los datos históricos:

    - *GLOBAL*: el sistema utiliza el rango completo de fechas de todos los atributos de granularidad.
    - *HISTORY_DATE_RANGE*: el sistema utiliza un rango de fechas específico definido por los campos **Partir de la fecha** y **Hasta la fecha** en la sección **Horizonte histórico** en el cuadro de diálogo **Generar previsión estadística de línea base**.
    - *GRANULARITY_ATTRIBUTE*: el sistema usa el rango de fechas del atributo de granularidad procesado actualmente.

    > [!NOTE]
    > Un atributo de granularidad es una combinación de dimensiones de pronóstico con las que se realiza el pronóstico. Puede definir dimensiones de previsión en la página **Parámetros de previsión de demanda**.

- **Sugerencia de estacionalidad**: Para datos estacionales, proporcione una sugerencia al modelo de previsión para mejorar la precisión de previsión. Formato: número entero que representa el número de cubos para el que un patrón de demanda se repite. Por ejemplo, especifique *6* para los datos que se repiten cada seis meses.
- **Porcentaje de tamaño de conjunto de pruebas**: porcentaje de datos históricos que se usará como conjunto de prueba para el cálculo de la precisión de la previsión.

Puede reemplazar los valores de estos parámetros yendo a **Planificación maestra \> Configuración \> Previsión de la demanda \> Parámetros de previsión de la demanda**. En la página **Parámetros de previsión de demanda** puede reemplazar los parámetros de la forma siguiente:

- Utilice la pestaña **General** para reemplazar los parámetros globalmente.
- Utilice la pestaña **Claves de asignación de artículos** para reemplazar los parámetros para claves de asignación de artículos específicas. Los parámetros que se reemplazan para una clave de asignación de artículos específica afectan solo a la previsión de los artículos que están asociados con esa clave de asignación de artículos.

> [!NOTE]
> En la página **Parámetros del algoritmo de previsión**, puede utilizar los botones del Panel de acciones para agregar parámetros a la lista o eliminar parámetros de la lista. Sin embargo, por lo general no debe cambiar este enfoque a menos que haya personalizado el experimento en Azure Machine Learning.

## <a name="set-up-the-azure-machine-learning-service"></a><a name="setup-amls"></a>Configurar la conexión con Azure Machine Learning Service

Supply Chain Management calcula las previsiones de demanda mediante Azure Machine Learning Service, que debe configurar y ejecutar en su propia suscripción de Azure. En esta sección se describe cómo configurar Azure Machine Learning Service en Azure y luego conectarlo a su entorno de Supply Chain Management.

### <a name="enable-the-azure-machine-learning-service-in-feature-management"></a>Habilite el Azure Machine Learning Service en la administración de características

Antes de poder usar Azure Machine Learning Service para previsión de demanda, debe activar una característica en Supply Chain Management para habilitar la integración. Los administradores pueden usar la configuración de [gestión de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y activarla. En el espacio de trabajo **Administración de características**, la función aparece de la siguiente forma:

- **Módulo:** *Planificación maestra*
- **Nombre de característica:** *Azure Machine Learning Service para previsión de demanda*

### <a name="set-up-machine-learning-in-azure"></a><a name="ml-workspace"></a>Configurar aprendizaje automático en Azure

Para permitir que Azure use el aprendizaje automático para procesar sus previsiones, debe configurar un área de trabajo de aprendizaje automático de Azure para este propósito. Tiene dos opciones:

- Para configurar el espacio de trabajo ejecutando un script proporcionado por Microsoft, siga las instrucciones de la sección [Opción 1: ejecutar un script para configurar automáticamente su espacio de trabajo de aprendizaje automático](#ml-workspace-script) y luego salte a la sección [Configurar los parámetros de conexión del Azure Machine Learning Service en Supply Chain Management](#demand-forecast-parameters).
- Para configurar manualmente el espacio de trabajo, siga las instrucciones de la sección [Opción 2: configurar manualmente su espacio de trabajo de aprendizaje automático](#ml-workspace-manual) y luego salte a la sección [Configurar los parámetros de conexión del Azure Machine Learning Service en Supply Chain Management](#demand-forecast-parameters). Esta opción lleva más tiempo, pero le da más control.

#### <a name="option-1-run-a-script-to-automatically-set-up-your-machine-learning-workspace"></a><a name="ml-workspace-script"></a>Opción 1: ejecutar un script para configurar automáticamente su espacio de trabajo de aprendizaje automático

En esta sección se describe cómo configurar su espacio de trabajo de aprendizaje automático mediante un script automatizado proporcionado por Microsoft. Si lo prefiere, puede configurar manualmente todos los recursos siguiendo las instrucciones de la sección [Opción 2: configurar manualmente el espacio de trabajo de aprendizaje automático](#ml-workspace-manual). No es necesario que complete ambas opciones.

1. En GitHub, abra el repositorio de [Plantillas para previsión de demanda de Dynamics 365 Supply Chain Management con Azure Machine Learning](https://github.com/microsoft/Dynamics-365-Supply-Chain-Management-Demand-Forecasting-With-Azure-Machine-Learning-Service) y descargue los siguientes archivos:

    - quick_setup.ps1
    - sampleInput.csv
    - src/parameters.py
    - src/api_trigger.py
    - src/run.py
    - src/REntryScript/forecast.r

1. Abra una ventana de PowerShell y ejecute el script **quick_setup.ps1** que descargó en el paso anterior. Siga las instrucciones en pantalla. El script configurará el espacio de trabajo, el almacenamiento, el almacén de datos predeterminado y los recursos de proceso necesarios. Sin embargo, aún debe crear las canalizaciones necesarias siguiendo los pasos restantes de este procedimiento. (Las canalizaciones proporcionan una forma de iniciar scripts de previsión desde Supply Chain Management).
1. En Azure Machine Learning Studio, cargue el archivo **sampleInput.csv** que descargó en el paso 1 al contenedor llamado *demplan-azureml*. (El script quick_setup.ps1 creó este contenedor.) Este archivo es necesario para publicar la canalización y generar una previsión de prueba. Para obtener instrucciones, consulte [Cargar un blob en bloques](/azure/storage/blobs/storage-quickstart-blobs-portal#upload-a-block-blob).
1. En Azure Machine Learning Studio, seleccione **Cuadernos de notas** en el navegador.
1. Busque la siguiente ubicación en la estructura **Archivos**: **Usuarios/\[usuario actual\]/src**.
1. Cargue los cuatro archivos restantes que descargó en el paso 1 a la ubicación que encontró en el paso anterior.
1. Seleccione el archivo **api_trigger.py** que acaba de cargar y ejecútelo. Creará una canalización que se puede desencadenar a través de la API.
1. Su espacio de trabajo ahora está configurado. Salte a la sección [Configurar los parámetros de conexión del Azure Machine Learning Service en Supply Chain Management](#demand-forecast-parameters).

#### <a name="option-2-manually-set-up-your-machine-learning-workspace"></a><a name="ml-workspace-manual"></a>Opción 2: configurar manualmente su espacio de trabajo de aprendizaje automático

Esta sección describe cómo configurar manualmente su espacio de trabajo de aprendizaje automático. Debe completar los procedimientos de esta sección solo si decidió no ejecutar el script de configuración automática, como se describe en la sección [Opción 1: ejecutar un script para configurar su espacio de trabajo de aprendizaje automático](#ml-workspace-script).

##### <a name="step-1-create-a-new-workspace"></a><a name="create-workspace"></a>Paso 1: crear un nuevo espacio de trabajo

Utilice el siguiente procedimiento para crear un nuevo espacio de trabajo de aprendizaje automático.

1. Inicie sesión en el portal de Azure.
1. Abre el servicio **Aprendizaje automático**.
1. Seleccione **Crear** en la barra de herramientas para abrir el asistente para **Crear**.
1. Complete el asistente siguiendo las instrucciones en pantalla. Tenga en cuenta los siguientes puntos mientras trabaja:

    - Utilice la configuración predeterminada a menos que otros puntos de esta lista recomienden configuraciones diferentes.
    - Asegúrese de seleccionar la región geográfica que coincida con la región donde se implementa su instancia de Supply Chain Management. De lo contrario, algunos de sus datos podrían atravesar los límites de la región. Para obtener más información, consulte el [Aviso de privacidad](#privacy) más adelante en este artículo.
    - Utilice recursos dedicados, como grupos de recursos, cuentas de almacenamiento, registros de contenedores, almacenes de claves de Azure y recursos de red.
    - En la página **Configurar parámetros de conexión del Azure Machine Learning Service** del asistente, debe proporcionar un nombre de cuenta de almacenamiento. Utilice una cuenta dedicada a la previsión de la demanda. Los datos de entrada y salida de previsión de la demanda se almacenarán en esta cuenta de almacenamiento.

Para obtener más información, consulte [Crear el espacio de trabajo](/azure/machine-learning/quickstart-create-resources#create-the-workspace).

##### <a name="step-2-configure-storage"></a><a name="config-storage"></a>Paso 2: configurar almacenamiento

Use el siguiente procedimiento para configurar su almacenamiento.

1. En GitHub, abra el repositorio de [Plantillas para previsión de demanda de Dynamics 365 Supply Chain Management con Azure Machine Learning](https://github.com/microsoft/Dynamics-365-Supply-Chain-Management-Demand-Forecasting-With-Azure-Machine-Learning-Service) y descargue el archivo **sampleInput.csv**.
1. Abra la cuenta de almacenamiento que creó en la sección [Paso 1: crear un nuevo espacio de trabajo](#create-workspace).
1. Siga las instrucciones de [Crear un contenedor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) para crear un contenedor que se llama *demplan-azureml*.
1. Cargue el archivo **sampleInput.csv** que descargó en el paso 1 al contenedor que acaba de crear. Este archivo es necesario para publicar la canalización y generar una previsión de prueba. Para obtener instrucciones, consulte [Cargar un blob en bloques](/azure/storage/blobs/storage-quickstart-blobs-portal#upload-a-block-blob).

##### <a name="step-3-configure-a-default-datastore"></a>Paso 3: configurar un almacén de datos predeterminado

Use el siguiente procedimiento para configurar su almacén de datos predeterminado.

1. En Azure Machine Learning Studio, seleccione **Almacenes de datos** en el navegador.
1. Cree un nuevo almacén de datos del tipo *Azure Blob Storage* que apunta al contenedor de almacenamiento de blobs *demplan-azureml* que creó en la sección [Paso 2: configurar almacenamiento](#config-storage). (Si el tipo de autenticación del nuevo almacén de datos es *Clave de cuenta*, proporcione una clave de cuenta para la cuenta de almacenamiento creada. Para obtener instrucciones, consulte [Administrar claves de acceso a la cuenta de almacenamiento](/azure/storage/common/storage-account-keys-manage?tabs=azure-portal).)
1. Haga que su nuevo almacén de datos sea el almacén de datos predeterminado abriendo sus detalles y seleccionando **Establecer como almacén de datos predeterminado**.

##### <a name="step-4-configure-compute-resources"></a><a name="config-compute-resources"></a>Paso 4: configurar recursos de proceso

Use el siguiente procedimiento para configurar un recurso de proceso en Azure Machine Learning Studio para ejecutar sus scripts de generación de previsión.

1. Abra la página de detalles del espacio de trabajo de aprendizaje automático que creó en la sección [Paso 1: crear un nuevo espacio de trabajo](#create-workspace). Busque el valor **URL web de Studio** valor y seleccione el enlace para abrirlo.
1. En el panel de navegación, haga clic en **Calcular**.
1. En la pestaña **Instancias de proceso**, seleccione **Nuevo** para abrir un asistente que le ayudará a crear una nueva instancia de proceso. Siga las instrucciones en pantalla. La instancia de proceso se utilizará para crear la canalización de previsión de demanda (se puede eliminar después de que se publique la canalización). Utilice la configuración predeterminada.
1. En la pestaña **Clústeres de proceso**, seleccione **Nuevo** para abrir un asistente que le ayudará a crear un nuevo clúster de proceso. Siga las instrucciones en pantalla. El clúster de proceso se utilizará para generar previsiones de demanda. Su configuración afecta al rendimiento y al nivel máximo de paralelización de la ejecución. Configure los siguientes campos, pero use la configuración predeterminada para todos los demás campos:

    - **Nombre**: escriba *e2ecpucluster*.
    - **Tamaño de máquina virtual** - Ajuste esta configuración de acuerdo con el volumen de datos que espera usar como entrada para la previsión de demanda. El recuento de nodos no debe exceder los 11, porque se requiere un nodo para desencadenar la generación de previsión de demanda y el número máximo de nodos que se pueden usar para generar una previsión es 10. (También establecerá el recuento de nodos en el archivo parameters.py en la sección [Paso 5: crear canalizaciones](#create-pipelines).) En cada nodo, habrá varios procesos de trabajo que ejecutan scripts de previsión en paralelo. El número total de procesos de trabajador en su trabajo será *Número de núcleos que tiene un nodo* × *Recuento de nodos*. Por ejemplo, si su clúster de proceso tiene un tipo de *Estándar\_D4* (ocho núcleos) y un máximo de 11 nodos, y si el valor de `nodes_count` se establece en *10* en el archivo parameters.py, el nivel efectivo de paralelismo es 80.

##### <a name="step-5-create-pipelines"></a><a name="create-pipelines"></a>Paso 5: crear canalizaciones

Las canalizaciones proporcionan una forma de iniciar scripts de previsión desde Supply Chain Management. Utilice el siguiente procedimiento para crear las canalizaciones requeridas.

1. En GitHub, abra el repositorio de [Plantillas para previsión de demanda de Dynamics 365 Supply Chain Management con Azure Machine Learning](https://github.com/microsoft/Dynamics-365-Supply-Chain-Management-Demand-Forecasting-With-Azure-Machine-Learning-Service) y descargue los siguientes archivos:

    - src/parameters.py
    - src/api_trigger.py
    - src/run.py
    - src/REntryScript/forecast.r

1. En Azure Machine Learning Studio, seleccione **Cuadernos de notas** en el navegador.
1. Busque la siguiente ubicación en la estructura **Archivos**: **Usuarios/\[usuario actual\]/src**.
1. Cargue los cuatro archivos que descargó en el paso 1 a la ubicación que encontró en el paso anterior.
1. En Azure, abra y revise el archivo **parameters.py** que acaba de cargar. Asegúrese de que el valor de `nodes_count` es uno menos que el valor que configuró para el clúster de proceso en la sección [Paso 4: configurar los recursos de proceso](#config-compute-resources). Si el valor de `nodes_count` es mayor o igual que el número de nodos en el clúster de proceso, es posible que la ejecución de la canalización pueda iniciarse. Sin embargo, dejará de responder mientras espera los recursos necesarios. Para obtener más información sobre el recuento de nodos, consulte la sección [Paso 4: configurar los recursos de proceso](#config-compute-resources).
1. Seleccione el archivo **api_trigger.py** que acaba de cargar y ejecútelo. Creará una canalización que se puede desencadenar a través de la API.

### <a name="set-up-a-new-active-directory-application"></a><a name="aad-app"></a>Configurar una nueva aplicación de Active Directory

Se requiere una aplicación de Active Directory para autenticarse con los recursos dedicados a la previsión de demanda mediante el uso de la entidad de servicio. Por lo tanto, la aplicación debe tener el nivel más bajo de privilegio necesario para generar la previsión.

1. Inicie sesión en el portal de Azure.
1. Registre una nueva aplicación en el Azure Active Directory (Azure AD) del inquilino. Para obtener instrucciones, consulte [Usar el portal para crear una aplicación de Azure AD y entidad de servicio que puede acceder a los recursos](/azure/active-directory/develop/howto-create-service-principal-portal).
1. Siga las instrucciones en pantalla mientras complete el asistente. Use la configuración predeterminada.
1. Dé acceso a su nueva aplicación de Active Directory a los siguientes recursos que creó en la sección [Configurar aprendizaje automático en Azure](#ml-workspace). Para obtener instrucciones, consulte [Asignar roles de Azure mediante el portal de Azure](/azure/role-based-access-control/role-assignments-portal?tabs=current). Este paso permitirá que el sistema importe y exporte datos de previsión y desencadene ejecuciones de canalización de aprendizaje automático desde Supply Chain Management.

    - Rol de colaborador en el espacio de trabajo de aprendizaje automático
    - Rol de colaborador de la cuenta de almacenamiento dedicada
    - Rol de colaborador de datos de Storage Blob de la cuenta de almacenamiento dedicada

1. En la sección **Certificados y secretos** de la aplicación que creó, cree un secreto para la aplicación. Para obtener instrucciones, consulte [Agregar un secreto de cliente](/azure/active-directory/develop/quickstart-register-app#add-a-client-secret).
1. Anote el ID de la aplicación y su secreto. Necesitará los detalles de esta aplicación más adelante, cuando configure la página **Parámetros de previsión de demanda** en Supply Chain Management.

### <a name="set-up-azure-machine-learning-service-connection-parameters-in-supply-chain-management"></a><a name="demand-forecast-parameters"></a>Configurar los parámetros de conexión del Azure Machine Learning Service en Supply Chain Management

Siga este procedimiento para conectar su entorno de Supply Chain Management con el servicio de aprendizaje automático que acaba de configurar en Azure.

1. Inicie sesión en de Supply Chain Management.
1. Vaya a **Planificación maestra \> Configuración \> Previsión de demanda \> Parámetros de previsión de la demanda**.
1. En la pestaña **General**, asegúrese de que el campo **Estrategia de generación de previsión** está configurado en *Azure Machine Learning Service*.
1. En la pestaña **Claves de asignación de artículos**, asegúrese de que el campo **Estrategia de generación de previsión** está configurado en *Azure Machine Learning Service* para cada clave de asignación que debe usar Azure Machine Learning Service para la previsión de demanda.
1. En la pestaña **Azure Machine Learning Service**, configure los siguientes campos:

    - **Id. de inquilino** - Escriba el Id. de su inquilino de Azure. Supply Chain Management usará este ID para autenticarse con Azure Machine Learning Service. Puede encontrar su ID de inquilino en la página **Descripción general** para Azure AD en el portal de Azure.
    - **Id. de aplicación de entidad de servicio** - Ingrese el Id. de la aplicación que creó en la sección [Aplicación de Active Directory](#aad-app). Este valor se usa para autorizar solicitudes de API a Azure Machine Learning Service.
    - **Secreto de entidad de servicio** - Ingrese el secreto de la aplicación de entidad de servicio para la aplicación que creó en la sección [Aplicación de Active Directory](#aad-app). Este valor se usa para adquirir el token de acceso para la entidad de seguridad que creó para realizar operaciones autorizadas en Azure Storage y el espacio de trabajo de Azure Machine Language.
    - **Nombre de cuenta de almacenamiento** - Ingrese el nombre de la cuenta de almacenamiento de Azure que especificó cuando ejecutó el asistente de configuración en su espacio de trabajo de Azure. (Para obtener más información, vea la sección [Configurar aprendizaje automático en Azure](#ml-workspace).)
    - **Dirección de extremo de canalización** - Ingrese la URL del extremo REST de la canalización para su Azure Machine Learning Service. Usted creó esta canalización como último paso cuando [configuró el aprendizaje automático en Azure](#ml-workspace). Para obtener la URL de canalización, inicie sesión en su portal de Azure, seleccione **Canalizaciones** en la navegación. En la pestaña **Canalización**, seleccione el extremo de canalización que se llama **TriggerDemandForecastGeneration**. Luego copie el extremo REST que se muestra.

    ![Parámetros de la pestaña Azure Machine Learning Service de la página Parámetros de previsión de demanda.](media/azure-ml-service-parameters.png "Parámetros de la pestaña Azure Machine Learning Service de la página Parámetros de previsión de demanda")

## <a name="privacy-notice"></a><a name="privacy"></a>Aviso de privacidad

Cuando selecciona *Azure Machine Learning Service* como estrategia de generación de previsión, Supply Chain Management envía automáticamente los datos de sus clientes para demanda histórica, como cantidades agregadas, nombres de productos y las dimensiones de sus productos, ubicaciones de envío y recepción, identificadores de clientes y también parámetros de previsión, a la región geográfica donde se encuentran su espacio de trabajo de aprendizaje automático y su cuenta de almacenamiento vinculada, con el fin de pronosticar las demandas futuras. El Azure Machine Learning Service puede estar en una región geográfica diferente a la región geográfica donde se implementa Supply Chain Management. Algunos usuarios pueden controlar si esta funcionalidad está habilitada seleccionando la estrategia de generación de previsiones en la página **Parámetros de previsión de demanda**.

## <a name="additional-resources"></a>Recursos adicionales

- [Información general de la previsión de la demanda](introduction-demand-forecasting.md)
- [Generar previsión estadística de línea base](generate-statistical-baseline-forecast.md)
- [Realización de ajustes manuales en la previsión de línea base](manual-adjustments-baseline-forecast.md)
- [Webinar: Azure Machine Learning Series para previsión de demanda](https://aka.ms/DemandForecastingwithAzureMachineLearningSeries)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
