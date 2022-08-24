---
title: Análisis de idoneidad de optimización de la planificación
description: Este artículo explica cómo comprobar la configuración actual y los datos frente a las prestaciones de la funcionalidad de optimización de la planificación.
author: t-benebo
ms.date: 08/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MpsFitAnalysis, MpsIntegrationParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: af7f4b09fd624aeda2ff002292e11cf84fd02991
ms.sourcegitcommit: e4b6521337dfff3515f70086b0125d4c23308c71
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2022
ms.locfileid: "9262340"
---
# <a name="planning-optimization-fit-analysis"></a>Análisis de idoneidad de optimización de la planificación

[!include [banner](../../includes/banner.md)]

Debe analizar el resultado del análisis de ajuste de Planning Optimization como parte del proceso de migración. Tenga en cuenta que el alcance de la optimización de la planificación no es igual a la funcionalidad de planificación maestra incorporada actual. Le recomendamos que trabaje con su socio y lea la documentación para prepararse para la migración. 

El análisis de ajuste de Planning Optimization le ayuda a identificar dónde puede diferir el resultado entre el motor de planificación maestro integrado y Planning Optimization. Este análisis se realiza en función de su configuración y datos actuales. 

Para ver el resultado del análisis de ajuste de Planning Optimization, vaya a **Planificacion maestra** \> **Preparar** \> **Análisis de ajuste de optimización de planificación** y luego seleccione **Ejecutar análisis**. Si el análisis detecta incoherencias, se enumeran en la misma página. (El análisis puede tardar algunos minutos en ejecutarse).

> [!NOTE]
>
> - Algunas incoherencias no se pueden identificar mediante el análisis de ajuste de Optimización de planificación. Para obtener más información, consulte [Diferencias entre la planificación maestra clásica y Optimización de planificación](planning-optimization-differences-with-built-in.md).
>
> - Si se encuentran incoherencias, puede usar la optimización de la planificación. Los resultados del análisis de aptitud solo muestran las ubicaciones en las que el servicio de planificación no coincide con la configuración actual. Es decir, muestran las ubicaciones en las que algunos procesos se pueden omitir o no están admitidos.

## <a name="analysis-results-example-1"></a>Resultados de análisis: ejemplo 1

- **Característica:** producción
- **Problema** artículos con un nivel de lista de materiales (BOM) mayor que cero: 56
- **Explicación**: el análisis de aptitud encontró 56 artículos con una lista de materiales configurada para producción. Dado que la versión actual de la optimización de la planificación no admite la producción, la optimización de la planificación generará pedidos de compra planificados en lugar de pedidos de producción planificados. También mostrará una advertencia que enumere los artículos afectados.

## <a name="analysis-results-example-2"></a>Resultados de análisis: ejemplo 2

- **Característica:** acciones
- **Problema:** grupos de cobertura con el cálculo de las acciones habilitado: 6
- **Explicación:** el análisis de aptitud detectó seis grupos de cobertura donde el cálculo de la acción está activado. Dado que la versión actual de la optimización de la planificación no admite acciones, no se generarán acciones durante la planificación maestra.

## <a name="overview-of-possible-results-from-the-fit-analysis"></a>Resumen de posibles resultados del análisis de idoneidad

La siguiente tabla muestra los diversos resultados que se pueden mostrar después de un análisis de idoneidad. Los signos numéricos (*\#*) se reemplazarán con un número que indica el número de registros que tienen el problema mencionado.

> [!IMPORTANT]
> Para las funciones que aún no son compatibles, la siguiente tabla proporciona información de disponibilidad esperada que se estima en función de nuestra hoja de ruta actual. Estas estimaciones están sujetas a cambios sin previo aviso.

| Característica | Problema mencionado | Explicación | Disponibilidad prevista |
| --- | --- | --- | --- |
| Acciones | Grupos de cobertura con el cálculo de acciones habilitado: *\#* | Esta característica ahora se admite. | Compatible |
| Calendarios base | Calendarios que usan el calendario base: *\#* | Esta característica ahora se admite. | Compatible | 
| Códigos de disposición de lote | Maestros de disposición de lote no incluidos: *\#* | Esta característica está pendiente. Actualmente, los códigos de disposición de lotes se ignoran cuando la optimización de la planificación está habilitada. | Segundo lanzamiento de versiones de 2022 |
| Capaz de comprometer (CTP) | Configuración de pedido predeterminada con control de fecha de entrega establecido en CTP: *\#* | En Supply Chain Management 10.0.28 y posteriores, un proceso llamado *CTP para Optimización de planificación* hace que las fechas confirmadas de envío y recepción estén disponibles después de que se haya ejecutado el plan dinámico. Para versiones anteriores de Supply Chain Management, la configuración de CTP heredada se ignora cuando se habilita Optimización de la planificación. | Compatible |
| Copia estática en plan dinámico | La copia de plan estático a dinámico está habilitada en los parámetros de planificación maestra. | La optimización de la planificación no copia el plan estático en el plan dinámico, independientemente de esta configuración. En general, este concepto es menos relevante debido a la velocidad y la regeneración completa que proporciona la optimización de planificación. Si se utilizan dos o más planes, se debe activar la planificación maestra para cada plan. | N/A |
| Puesta en firme | Grupos de cobertura con límite de tiempo de puesta en firme automática establecido: *\#* | En la versión 10.0.7 y posteriores, la puesta en firme se admite como un trabajo por lotes de puesta en firme independiente después de completar la planificación maestra (siempre que *Puesta en firme automática para la optimización de la planificación* se haya habilitado en [Administración de características](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)). Tenga en cuenta que la puesta en firme automática para la optimización de la planificación se basa en la fecha del pedido (fecha de inicio), no en la fecha del requisito (fecha de finalización). Este comportamiento asegura que la puesta en firme de las órdenes planificadas se produzca a su debido tiempo, sin tener que incluir el tiempo de entrega en el límite del tiempo de puesta en firme. | Compatible |
| Puesta en firme | Registros de cobertura de artículos con puesta en firme automática establecida: : *\#* | En la versión 10.0.7 y posteriores, la puesta en firme automática se admite como un trabajo por lotes de puesta en firme independiente después de completar la planificación maestra (siempre que *Puesta en firme automática para la optimización de la planificación* se haya habilitado en [Administración de características](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)). Tenga en cuenta que la puesta en firme automática para la optimización de la planificación se basa en la fecha del pedido (fecha de inicio), no en la fecha del requisito (fecha de finalización). Este comportamiento asegura que la puesta en firme de las órdenes planificadas se produzca a su debido tiempo, sin tener que incluir el tiempo de entrega en el límite del tiempo de puesta en firme. | Compatible |
| Puesta en firme | Planes maestros con puesta en firme automática establecida: *\#* | En la versión 10.0.7 y posteriores, la puesta en firme automática se admite como un trabajo por lotes de puesta en firme independiente después de completar la planificación maestra (siempre que *Puesta en firma automática para la optimización de la planificación* se haya habilitado en [Administración de características](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)). Tenga en cuenta que la puesta en firme automática para la optimización de la planificación se basa en la fecha del pedido (fecha de inicio), no en la fecha del requisito (fecha de finalización). Este comportamiento asegura que la puesta en firme de las órdenes planificadas se produzca a su debido tiempo, sin tener que incluir el tiempo de entrega en el límite del tiempo de puesta en firme. | Compatible |
| FitAnalysisPlanningItems | Artículos de planificación: *\#* | Esta característica está pendiente. Actualmente, los elementos de planificación se manejan como elementos normales cuando la optimización de la planificación está habilitada. | Segundo lanzamiento de versiones de 2022 o posterior |
| Previsión | Grupos de cobertura con "Incluir pedidos de empresas vinculadas" habilitado: *\#* | Esta característica ahora se admite. Para obtener información adicional, consulte [Planificación de empresas vinculadas](Intercompany-planning.md) | Compatible |
| Previsión | Grupos de cobertura con la configuración "Reducir previsión por" establecida en un valor diferente a "Pedidos": *\#* | Esta característica ahora se admite. Para obtener más información, consulte [Planificación maestra con previsiones de demanda](demand-forecast.md) | Compatible |
| Previsión | Modelos de previsión con submodelos: *\#* |  Esta característica ahora se admite. Para obtener más información, consulte [Planificación maestra con previsiones de demanda](demand-forecast.md) | Compatible |
| Previsión | Planes maestros con "Incluir previsión de suministro" habilitado: *\#* | Esta característica está pendiente. Actualmente, las previsiones de suministro no son compatibles cuando la optimización de la planificación está habilitada. Se ignorarán, independientemente de esta configuración. | Segundo lanzamiento de versiones de 2022 o posterior |
| Congelar límite de tiempo | Grupos de cobertura con congelación del límite de tiempo establecido: *\#* | Esta característica está pendiente. Actualmente, la configuración del límite de tiempo contelado se ignora cuando la optimización de planificación está habilitada, independientemente de esta configuración. | Segundo lanzamiento de versiones de 2022 |
| Congelar límite de tiempo | Registros de cobertura de artículos con congelación del límite de tiempo establecido: *\#* | Esta característica está pendiente. Actualmente, la configuración del límite de tiempo contelado se ignora cuando la optimización de planificación está habilitada, independientemente de esta configuración. | Segundo lanzamiento de versiones de 2022 |
| Congelar límite de tiempo | Planes maestros con congelación del límite de tiempo establecido: *\#* | Esta característica está pendiente. Actualmente, la configuración del límite de tiempo contelado se ignora cuando la optimización de planificación está habilitada, independientemente de esta configuración. | Segundo lanzamiento de versiones de 2022 |
| Empresas vinculadas | Planes maestros que incluyen demanda planificada descendente: *\#* | Esta característica ahora se admite. Para obtener información adicional, consulte [Planificación de empresas vinculadas](Intercompany-planning.md) | Compatible |
| Kanban | Registros de cobertura de artículos con kanban de tipo de pedido planificado: *\#* | Esta característica está pendiente. Actualmente, la cobertura de artículos que se establece en kanban se ignorará cuando la optimización de la planificación esté habilitada. El tipo de orden planificada kanban creará una advertencia durante la planificación maestra y se crearán órdenes de compra planificadas para cubrir la demanda relacionada. | 2023 o posterior |
| Kanban | Artículos con kanban de tipo de pedido predeterminado: *\#* | Actualmente, un tipo de pedido predeterminado que se establece en kanban se ignora cuando la optimización de la planificación está habilitada. El tipo predeterminado de orden planificada kanban creará una advertencia durante la planificación maestra y se crearán órdenes de compra planificadas para cubrir la demanda relacionada. | 2023 o posterior |
| Estado de ciclo de vida de producto | Estados de ciclo de vida de producto no activos para planificación: *\#* | Esta característica ahora se admite. Para obtener información adicional, consulte [Excluir productos que tienen estados de ciclo de vida de productos específicos](product-lifecycle-state.md) | Compatible |
| Producción | Líneas de L. MAT con redondeo o configuración múltiple: *\#* | Esta característica está pendiente. Actualmente, el redondeo y las configuraciones múltiples se ignoran en las líneas de la lista de materiales cuando la optimización de la planificación está habilitada, independientemente de esta configuración. | 2023 o posterior |
| Producción | L. MAT/líneas de fórmula con medida de fórmula: *\#* | Esta característica está pendiente. Actualmente, la medida de fórmula se ignora en las líneas de la lista de materiales y la fórmula cuando la optimización de la planificación está habilitada, independientemente de esta configuración. | Segundo lanzamiento de versiones de 2022 |
| Producción | L. MAT/líneas de fórmula con sustitución de artículos (grupos de planes): *\#* | Esta característica está pendiente. Actualmente, la sustitución de artículos (grupos de plan) se ignora en las líneas de la lista de materiales y la fórmula cuando la optimización de la planificación está habilitada, independientemente de esta configuración. | Segundo lanzamiento de versiones de 2022 |
| Producción | L. MAT/líneas de fórmula con cantidad negativa: *\#* | Esta característica está pendiente. Las líneas de lista de materiales y de fórmula que tienen una cantidad negativa se incluirán con una cantidad de 0 (cero) y se emitirá una advertencia cuando se habilite la optimización de la planificación. Actualice los datos maestros para evitar advertencias. | Segundo lanzamiento de versiones de 2022 |
| Producción | L. MAT/líneas de fórmula con consumo de recursos: *\#* | Esta característica está pendiente. Actualmente, las líneas de BOM y fórmulas que tienen un consumo de recursos se ignoran cuando la optimización de la planificación está habilitada. Cuando se admite esta característica, el requisito de material se establecerá en la fecha de inicio de producción. Hasta que se admita esta característica no se generarán requisitos para materiales indicados con una marca de consumo de recursos. | Segundo lanzamiento de versiones de 2022 |
| Producción | L. MAT/líneas de fórmula con consumo de pasos: *\#* | Esta característica está pendiente. Actualmente, el consumo de pasos se ignora en las líneas de la lista de materiales y la fórmula cuando la optimización de la planificación está habilitada. | Segundo lanzamiento de versiones de 2022 |
| Producción | L. MAT con residuo constante o residuo variable definido: *\#* | Esta característica está pendiente. Actualmente, el rechazo constante y el rechazo variable que se definen en las listas de materiales se ignoran cuando la optimización de la planificación está habilitada. | Segundo lanzamiento de versiones de 2022 |
| Producción | L. MAT con subcontratación: *\#* | Esta característica ahora se admite. | Compatible |
| Producción | L. MAT sin sitio: *\#* | Esta característica ahora se admite. Para obtener información adicional, consulte [Planificación de producción](production-planning.md) | Compatible |
| Producción | Demanda con requisitos específicos de L. MAT o ruta definidos: *\#* | Esta característica está pendiente. Actualmente, los requisitos de ruta o lista de materiales específicos que se definen en la demanda (como una sublista de materiales o una ruta secundaria en un pedido de cliente) se ignoran cuando la optimización de la planificación está habilitada. Se utilizará la lista de materiales o la ruta estándar, independientemente de esta configuración. | Segundo lanzamiento de versiones de 2022 |
| Producción | Versiones de fórmula con coproductos o productos derivados: *\#* | Esta característica está pendiente. Actualmente, los coproductos y subproductos asociados con la versión de la fórmula se ignoran cuando la optimización de la planificación está habilitada. | Segundo lanzamiento de versiones de 2022 |
| Producción | Versiones de fórmula con rendimiento: *\#* | Esta característica está pendiente. Actualmente, el rendimiento asociado con la versión de la fórmula se ignora cuando la optimización de la planificación está habilitada. | Segundo lanzamiento de versiones de 2022 |
| Producción | Planes que incluyen la secuenciación: *\#* | Esta característica está pendiente. Actualmente, la secuenciación se ignora cuando la optimización de planificación está habilitada, independientemente de esta configuración. | Segundo lanzamiento de versiones de 2022 |
| Producción | Pedidos de producción emitidos que no se han iniciado, cuando el inicio programado es anterior al día de hoy: *\#* | Esta característica está pendiente. Actualmente, si se retrasa una orden de producción, la planificación maestra asumirá que se completará hoy. Esto es relevante para las órdenes de producción emitidas en las que una fecha de entrega es del pasado, pero aún no se ha completado. | 2023 o posterior |
| Producción | Recursos programados con capacidad finita: *\#* | Esta característica está pendiente. Actualmente, los recursos que están programados con capacidad finita se ignoran cuando la optimización de la planificación está habilitada. La programación se realiza en función del tiempo de entrega predeterminado del producto. | Segundo lanzamiento de versiones de 2022 |
| Producción | Rutas usadas en la planificación: *\#* | Esta característica se admite. | Compatible |
| Producción | Reserva de línea de ventas mediante expansión: *\#* | La reserva de línea de ventas mediante expansión no se admite cuando la optimización de la planificación está habilitada. | 2023 o posterior |
| Producción | Programación con expansión de pedidos de producción: *\#* | La programación con expansión de pedidos de producción no se admite cuando la optimización de la planificación está habilitada. Los pedidos de producción se pueden programar individualmente. | 2023 o posterior |
| Solicitud de presupuestos | Planes maestros con solicitudes de presupuestos habilitadas: *\#* | Esta característica está pendiente. Actualmente, las solicitudes de presupuesto (RFQ) no se consideran demanda cuando la optimización de la planificación está habilitada. Se ignorarán, independientemente de esta configuración. | Segundo lanzamiento de versiones de 2022 |
| Solicitudes | Planes maestros con solicitudes habilitadas: *\#* | Esta característica ahora se admite. Para obtener más información, consulte [Solicitudes de compra](purchase-requisitions.md) | Compatible |
| Márgenes de seguridad | Grupos de cobertura con margen de seguridad: *\#* | Esta característica ahora se admite. Para obtener información adicional, consulte [Márgenes de seguridad](safety-margins.md) | Compatible |
| Márgenes de seguridad | Planes maestros con margen de seguridad: *\#* | Esta característica ahora se admite. Para obtener información adicional, consulte [Márgenes de seguridad](safety-margins.md) |  Compatible |
| Cumplimiento de existencias de seguridad | Registros de cobertura de artículos con "Cumplimiento mínimo" diferente de "Fecha de hoy + tiempo de adquisición": *\#* | La optimización de la planificación siempre utiliza *Fecha de hoy + tiempo de adquisición*. Este cambio se realiza para prepararse para una configuración de planificación simplificada en el futuro y para proporcionar un resultado procesable. Si no se incluye el tiempo de adquisición para el stock de seguridad, los pedidos planificados que se creen para el inventario disponible bajo actual siempre se retrasarán debido al tiempo de entrega. Este comportamiento puede causar ruido significativo y órdenes planificadas no deseadas. La mejor práctica es cambiar la configuración para que se use *Fecha de hoy + tiempo de adquisición*. Actualice los datos maestros para evitar advertencias. | N/D |
| Presupuestos de ventas | Planes maestros con presupuestos de ventas habilitados: *\#* | Esta característica está pendiente. Actualmente, los presupuestos no se consideran cuando la optimización de la planificación está habilitada. Se ignorarán, independientemente de esta configuración. | Segundo lanzamiento de versiones de 2022 o posterior |
| Vida útil | Planes maestros con vida útil habilitada: *\#* | Esta característica está pendiente. Actualmente, la vida útil no se considera cuando la optimización de planificación está habilitada, independientemente de esta configuración. | Compatible |

## <a name="additional-resources"></a>Recursos adicionales

[Información general de la optimización de la planificación](planning-optimization-overview.md)

[Introducción a Optimización de planificación](get-started.md)

[Diferencias entre la planificación maestra clásica y Optimización de planificación](planning-optimization-differences-with-built-in.md)

[Parámetros no utilizados por Optimización de planificación](not-used-parameters.md)

[Ver historial del plan y registros de planificación](plan-history-logs.md)

[Aplicar filtros a un plan](plan-filters.md)

[Cancelar un trabajo de planificación](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
