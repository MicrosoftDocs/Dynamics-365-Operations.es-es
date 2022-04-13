---
title: Asistencia de configuración de planificación maestra (contiene vídeo)
description: Este tema describe cómo ejecutar el asistente de configuración de planificación maestra para configurar la planificación maestra.
author: t-benebo
ms.date: 10/21/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-05-31
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: a5914f63de654acd076048240c6e37d5b67f4ffa
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2022
ms.locfileid: "8470216"
---
# <a name="master-planning-setup-wizard"></a>Asistencia de configuración de planificación maestra

[!include [banner](../includes/banner.md)]

Este tema proporciona una guía para **Asistente de configuración de planificación maestra**. Explica cómo se calculan las sugerencias de parámetros y también proporciona ejemplos de cómo las distintas empresas configuran la planificación maestra, en función de as necesidades de su negocio.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3YnSB]

El vídeo [Asistencia de configuración de planificación maestra en Dynamics 365 Supply Chain Management](https://youtu.be/c-e6n-8rZb4) (aparece más arriba) está incluido en la [Lista de reproducción de Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponibles en YouTube.


## <a name="specific-requirements-of-your-company"></a>Requisitos específicos de la empresa

La primera página del asistente pregunta por los requisitos específicos de la empresa. Sus respuestas a estas preguntas no tienen que ser exactas, pero debe poder proporcionar una aproximación del número de artículos y de pedidos planificados que habrá para la entidad jurídica. Sus respuestas se utilizan para configurar los parámetros que se aplican a la entidad jurídica, no sólo al plan maestro que ha seleccionado. En las secciones siguientes se describen los parámetros que se calculan y las fórmulas que se usan.

### <a name="number-of-threads"></a>Número de subprocesos

- **Sifabrica alguno de los artículos:** Número de subprocesos = Número de pedidos planificados ÷ 1000
- **Si no fabrica ninguno de los artículos:** Número de subprocesos = Número de artículos ÷ 1000

Si el número de subprocesos calculado excede el 75 por ciento del número de subprocesos disponible, se limita en el 75 por ciento del número de subprocesos que está disponible para cada cliente. (El número de subprocesos disponible será determinado para cada cliente).

Para más información, consulte [Número de subprocesos](/dynamics365/unified-operations/supply-chain/master-planning/master-planning-performance#number-of-threads).

### <a name="bundle-size"></a>Tamaño de agrupación de trabajos

El tamaño de la agrupación de trabajos se establecerá en **1**. Este valor es a menudo el mejor valor, ya que ayuda a mejorar el rendimiento de la planificación maestra.

Para obtener más información, consulte [Número de tareas en la agrupación de trabajos del ayudante](/dynamics365/unified-operations/supply-chain/master-planning/master-planning-performance#number-of-tasks-in-helper-task-bundle).

### <a name="firming-bundle-size"></a>Tamaño de agrupación de trabajos de puesta en firme

- **Si fabrica cualquiera de los artículos:** El tamaño de agrupación de trabajos de puesta en firme se establecerá en el mayor de los dos valores: **10** y el cálculo de la agrupación de trabajos.
- **Si no fabrica ninguno de los artículos:** El tamaño de agrupación de trabajos de puesta en firme se establecerá en el mayor de los dos valores: **50** y el cálculo de la agrupación de trabajos.

Cálculo de la agrupación de trabajos = (Número de pedidos planificados × (límite de tiempo de puesta en firme ÷ límite de tiempo de cobertura) ÷ Número de subprocesos) ÷ 10

### <a name="cache-size"></a>Tamaño de caché

El tamaño de caché se establecerá en **Máximo**. Este valor es a menudo el mejor valor, ya que ayuda a mejorar el rendimiento de la planificación maestra.

Para obtener más información, consulte [Asignar tiempo a los trabajos de una agrupación de trabajos](/dynamics365/unified-operations/supply-chain/production-control/allocate-time-jobs-job-bundle).

### <a name="manufacturing-setup"></a>Configuración de la fabricación

Si fabrica los artículos, aparecerá una página **Configuración de fabricación** más adelante en el asistente.

## <a name="scope-of-the-current-plan"></a>Ámbito del plan actual

En la página **Ámbito del plan actual** del asistente, responda a las preguntas relacionadas con el momento máximo en el futuro en que se considerarán y calcularán diferentes requisitos en la planificación maestra. Cada pregunta plantea si desea utilizar una característica y cómo desea configurarla.

Por ejemplo, para la característica del plan de previsión, el asistente pregunta si desea usar un plan de previsión en la planificación maestra de modo que los pedidos planificados se sugieran para satisfacer la demanda prevista.

Las opciones siguientes están disponibles:

- **No**: la planificación maestra no sugerirá pedidos planificados para satisfacer una previsión. En la pestaña **Límites de tiempo** de la página **Planes maestros** (**Planificación maestra \> Configuración \> Planes \> Planes maestros**), el asistente establecerá la opción **Plan de previsión (límite de tiempo)** en **Sí** y establecerá el número de días en **0** (cero). Esta configuración anulará el límite de tiempo que se especifica en el grupo de cobertura. Dado que el número de días se establece en **0** (cero), la característica no se usará.
- **Sí, como se define en este plan maestro**: un campo estará disponible para especificar el número de días que la planificación maestra sugerirá pedidos planificados para satisfacer la demanda prevista. El asistente establecerá la opción **Plan de previsión (límite de tiempo)** en **Sí** y establecerá el número de días en el número introducido en el campo **Plan de previsión** de la pestaña **Límites de tiempo** de la página **Planes maestros**. Esta configuración invalidará los valores que se establezcan en los grupos de cobertura.
- **Sí, como se define en la cobertura**: el asistente establecerá la opción **Plan de previsión (límite de tiempo)** en **No**. Los límites de tiempo que se especifican en el grupo de cobertura se usarán para especificar durante cuánto tiempo se planeará la previsión.

La resto de las preguntas en esta página y sus respuestas siguen el mismo esquema:

- **No**: la opción **Plan de previsión (límite de tiempo)** se establecerá en **Sí** y el número de días se establecerá en **0** (cero).
- **Sí, como se define en este plan maestro**: la opción **Plan de previsión (límite de tiempo)** se establecerá en **Sí**. Se usará el número de días que especifique y se invalidarán los valores que se establecen en los grupos de cobertura.
- **Sí, como se define en el grupo de cobertura**: la opción **Plan de previsión (límite de tiempo)** se establecerá en **No**.

Para obtener más información, consulte [Programación de trabajos](/dynamics365/unified-operations/supply-chain/production-control/job-scheduling).

## <a name="scheduling-options"></a>Opciones de programación

La página **Opciones de programación** aparece solo si respondió **Sí** a la pregunta sobre si fabrica alguno de los artículos planificados en la primera página del asistente.

La respuesta a la primera pregunta de esta página (“¿Necesita programar las operaciones divididas en trabajos individuales?") determina el método de programación de la pestaña **General** de la página **Planes maestros**.

- **Sí**: se usará la programación de trabajos.
- **No**. se ussará la programación de operaciones.

Para obtener más información, consulte [Programación de operaciones](/dynamics365/unified-operations/supply-chain/production-control/operations-scheduling) y [Programación de trabajos](/dynamics365/unified-operations/supply-chain/production-control/job-scheduling).

## <a name="updates-of-demand-and-supply"></a>Actualizaciones de demanda y suministro

Las preguntas de la página **Actualizaciones de oferta y demanda** están relacionadas con la puesta en firme, los mensajes de acción y los retrasos.

La configuración de la planificación maestra se actualizará en función de la respuestas, según el mismo esquema que se describe en la sección anterior:

- **No**: la opción **Plan de previsión (límite de tiempo)** de la página **Planes maestros** se establecerá en **Sí** y el número de días se establecerá en **0** (cero).
- **Sí, como se define en este plan maestro**: la opción **Límite de tiempo** se establecerá en **Sí**. Se usará el número de días que especifique y se invalidarán los valores que se establecen en los grupos de cobertura.
- **Sí, como se define en el grupo de cobertura**: la opción **Límite de tiempo** se establecerá en **No**.

Para los retrasos calculados, las respuestas a las preguntas del asistente actualizarán los parámetros correspondientes en la pestaña **Retrasos calculados** de la página **Planes maestros**.

## <a name="summary-of-your-changes"></a>Resumen de sus cambios

La última página del asistente muestra los cambios recomendados en función de las respuestas. Muestra el valor de la configuración (**Configuración actual**) y el valor que el asistente recomienda (**Nueva configuración**).

También puede modificar los parámetros de la nueva configuración. Los parámetros se separan en los parámetros que se aplican a la entidad jurídica y parámetros que solo se aplican al plan maestro que ha seleccionado. Para ver todos los parámetros de configuración que se pueden cambiar con el asistente, seleccione **Mostrar todos los parámetros** en la parte inferior de la página. Posteriormente puede cambiar los parámetros.

Finalmente, cuando seleccione **Finalizar**, se aplicará la configuración nueva. Si se selecciona **Cancelar**, no se aplica ninguno de los cambios.

## <a name="examples"></a>Ejemplo

Esta sección describe la configuración de dos empresas ficticias para mostrar cómo la configuración puede cambiar según las necesidades de cada negocio.

### <a name="example-1-contoso-manufacturer"></a>Ejemplo 1: Contoso Manufacturer

Contoso Manufacturer es una empresa de fabricación que produce altavoces. Compras de varios proveedores las materias primas y los componentes que se usan para fabricar los altavoces finales. Estas son algunas de las características del suministro y la fabricación:

- Los artículos finales que la empresa fabrica tienen una estructura de lista de materiales (BOM).
- Todos los artículos y componentes finales se planifican según la planificación maestra. No se realiza planificación manual.
- Se define una ruta de operaciones para la producción de cada artículo final.
- La fábrica produce los artículos finales. Tiene un número definido de fresadoras y perforadoras que se usan para procesar los componentes. Los distintos componentes deben ser procesados por estas máquinas.
- Existen varios proveedores. El plazo medio para los artículos es de una semana. Un grupo de artículos del mismo proveedor tendrá un plazo de siete semanas.

En el asistente, se especifican los siguientes valores para Contoso Manufacturer:

- **Cobertura:**

    - **Pregunta:** “¿Desea especificar el número de días del horizonte de planificación?"
    - **Respuesta:** “Sí, como se define en los grupos de cobertura”.

    Dado que el plazo para los artículos es muy diferente, Contoso no tiene que planificar todos los artículos para el mismo período futuro. Se crean grupos de cobertura para los artículos. Los artículos que tengan un plazo similar se asignan al mismo grupo de cobertura. El horizonte de planificación de cada grupo de cobertura (es decir, el límite de tiempo de cobertura) es aproximadamente el plazo más un margen de una semana. La planificación maestra se asegura de que los artículos están planificados por adelantado, en función de su plazo.

    Por lo tanto, se crearán dos grupos de cobertura para este ejemplo. Un grupo de cobertura tendrá un límite de tiempo de cobertura de dos semanas y el otro tendrá un límite de tiempo de cobertura de ocho semanas.

    Si se selecciona **Sí, como se define en este plan maestro** como respuesta, el número de días que se especifica debe superar el plazo más largo de todos los artículos. Sin embargo, dado que muchos artículos no tienen que planificarse con tanta antelación, muchos pedidos planificados se calcularán pero nunca se utilizarán. Por lo tanto, el tiempo de ejecución de la planificación maestra aumentará.

- **Programación:**

    - **Pregunta:** “¿Necesita programar las operaciones divididas en trabajos individuales?"
    - **Respuesta:** "Sí".

    Contoso Manufacturing debe planificar y programar los trabajos individuales que se realizarán en planta. Por lo tanto, utilizará la programación de trabajos.

- **Capacidad:**

    - **Pregunta:** “¿Desea programar con la capacidad de recursos?”
    - **Respuesta:** “Sí, como se define en este plan maestro”. Se especifica **10 días**.

    El número de fresadoras y perforadoras es limitado. La planificación de producción debe tener en cuenta esta limitación y organizar los trabajos a tiempo según la capacidad de los recursos. Es decir, los trabajos que se programen se replanificarán en función de las limitaciones de recursos. La planificación usará el plazo además del período definido. (Los pedidos de producción planificados se pueden superponer). Dado que el plazo de producción para los artículos es de siete días, se tendrá en cuenta la capacidad de los recursos para la planificación maestra durante 10 días.

- **Secuenciación:**

    - **Pregunta:** “¿Desea secuenciar los pedidos planificados según la configuración de secuencia del producto?"
    - **Respuesta:** “Sí, como se define en los grupos de cobertura”.

    Se define una ruta para la producción de cada artículo final. Por lo tanto, la planificación maestra programará los pedidos a tiempo según las rutas definidas.

- **Expansión:**

    - **Pregunta:** “¿Desea planificar los pedidos para todos los elementos de una lista de materiales (el plan para el artículo principal y todos los artículos secundarios)?"
    - **Respuesta:** “Sí, como se define en los grupos de cobertura”.

    Todos los artículos que se usan para la producción deben planificarse. Dado que los artículos tienen plazos muy diferentes, la planificación maestra tendrá un mejor rendimiento cuándo use los grupos de cobertura. De nuevo, se puede introducir un margen de una semana y la expansión se puede hacer para el mismo tiempo que la cobertura.

### <a name="example-2-contoso-retailer"></a>Ejemplo 2: Contoso Retailer

Contoso Retailer es una empresa de distribución en el sector de la moda. Usa la planificación maestra para calcular cuándo deben realizarse los pedidos de compra, en función de las ventas previstas. Aquí están algunas de sus características:

- Contoso Retailer usa la previsión de la demanda para pronosticar las ventas. Los pedidos de compra se planifican según la previsión.
- Las tiendas utilizan solicitudes de reabastecimiento.
- El plazo desde el almacén principal hasta cada tienda es de aproximadamente dos semanas para todos los artículos.

En el asistente, se especifican los siguientes valores para Contoso Retailer:

- **Previsión de la demanda:**

    - **Pregunta:** “¿Desea usar un plan de previsión en la planificación maestra de modo que los pedidos planificados se sugieran para satisfacer la demanda prevista?"
    - **Respuesta:** “Sí, como se define en este plan maestro”.

    Contoso ha incluido una previsión de la demanda para pronosticar las ventas. Por lo tanto, la planificación maestra debe recomendar los pedidos planificados para satisfacer la previsión.

- **Puesta en firme:**

    - **Pregunta:** “¿Desea que la planificación maestra ponga en firme automáticamente los pedidos planificados en los documentos de pedido, por ejemplo producción o pedidos de compra?"
    - **Respuesta:** “Sí, como se define en este plan maestro”. Se especifica **1 día**.

    Dado que Contoso Retailer creará pedidos de compra directamente a partir de los pedidos de compra planificados, resulta útil que los pedidos de compra planificados se pongan en firme automáticamente. Dado que la empresa opera con planificación maestra cada día, un límite de tiempo de consolidación de un día pondrá en firme automáticamente todos los pedidos que se requieran para el día siguiente.

- **Solicitudes aprobadas:**

    - **Pregunta:** “¿Desea incluir la demanda de solicitudes aprobadas para reabastecer las tiendas al por menor?"
    - **Respuesta:** “Sí, como se define en este plan maestro”. Se especifica **1 día**.

    Contoso usa las solicitudes aprobadas de sus tiendas para crear pedidos de compra planificados para reabastecer las tiendas. Dado que la planificación maestra se ejecuta cada día, se incluirán en la planificación las solicitudes a partir del último día.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]