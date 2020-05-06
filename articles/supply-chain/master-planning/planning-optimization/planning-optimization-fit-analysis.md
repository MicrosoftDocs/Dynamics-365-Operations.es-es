---
title: Análisis de aptitud de la optimización de la planificación
description: Este tema explica cómo comprobar la configuración actual y los datos frente a las prestaciones de la funcionalidad de optimización de la planificación.
author: ChristianRytt
manager: tfehr
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 0382e78942e6cb2047e37b76f1daf5725638d5c3
ms.sourcegitcommit: 915ee7c59ef5fbd4927c10840e5c5e8652f667a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "3277807"
---
# <a name="planning-optimization-fit-analysis"></a>Análisis de aptitud de la optimización de la planificación

[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

Para ver el grado de compatibilidad de su configuración actual y los datos con la funcionalidad de optimización de la planificación, vaya **Planificación maestra** \> **Configuración** \> **Análisis de aptitud de la optimización de la planificación** y después seleccione **Ejecutar análisis**. Si el análisis detecta incoherencias, se enumeran en la misma página. (El análisis puede tardar algunos minutos en ejecutarse).

> [!NOTE]
> Si se encuentran incoherencias, puede usar la optimización de la planificación. Los resultados del análisis de aptitud solo muestran las ubicaciones en las que el servicio de planificación no coincide con la configuración actual. Es decir, muestran las ubicaciones en las que algunos procesos se pueden omitir o no están admitidos.

## <a name="analysis-results-example-1"></a>Resultados de análisis: ejemplo 1

- **Característica:** producción
- **Problema** artículos con un nivel de lista de materiales (BOM) mayor que cero: 56
- **Explicación**: el análisis de aptitud encontró 56 artículos con una lista de materiales configurada para producción. Dado que la versión actual de la optimización de la planificación no admite la producción, la optimización de la planificación generará pedidos de compra planificados en lugar de pedidos de producción planificados. También mostrará una advertencia que enumere los artículos afectados.

## <a name="analysis-results-example-2"></a>Resultados de análisis: ejemplo 2

- **Característica:** acciones
- **Problema:** grupos de cobertura con el cálculo de las acciones habilitado: 6
- **Explicación:** el análisis de aptitud detectó seis grupos de cobertura donde el cálculo de la acción está activado. Dado que la versión actual de la optimización de la planificación no admite acciones, no se generarán acciones durante la planificación maestra.

## <a name="overview-of-possible-results-from-the-fit-analysis"></a>Resumen de posibles resultados del análisis de idoneidad

La siguiente tabla muestra los diversos resultados que se pueden mostrar después de un análisis de idoneidad. Los signos numéricos (_\#_) se reemplazarán con un número que indica el número de registros que tienen el problema mencionado.

| Característica | Problema mencionado | Explicación |
| --- | --- | --- |
| Acciones  | Grupos de cobertura con el cálculo de acciones habilitado: _\#_ | Esta característica está pendiente. Actualmente, las acciones no se generan durante la planificación maestra cuando la optimización de la planificación está habilitada, independientemente de esta configuración. El objetivo principal de las acciones es sugerir cambios en los pedidos existentes. |
| Calendarios base | Calendarios que usan el calendario base: _\#_ | Esta característica está pendiente. Actualmente, el calendario base se ignora cuando la optimización de la planificación está habilitada. |
| Códigos de disposición de lote | Maestros de disposición de lote no incluidos: _\#_ | Esta característica está pendiente. Actualmente, los códigos de disposición de lotes se ignoran cuando la optimización de la planificación está habilitada. |
| Capaz de comprometer (CTP) | Configuración de pedido predeterminada con control de fecha de entrega establecido en CTP: _\#_ | Esta característica está pendiente. Actualmente, CTP se ignora cuando la optimización de planificación está habilitada, independientemente de esta configuración. |
| Copia estática en plan dinámico | La copia de plan estático a dinámico está habilitada en los parámetros de planificación maestra. | La optimización de la planificación no copia el plan estático en el plan dinámico, independientemente de esta configuración. En general, este concepto es menos relevante debido a la velocidad y la regeneración completa que proporciona la optimización de planificación. Si se utilizan dos o más planes, se debe activar la planificación maestra para cada plan. |
| Puesta en firme | Grupos de cobertura con límite de tiempo de puesta en firme automática establecido: _\#_ | En la versión 10.0.7 y posteriores, la reafirmación se admite como un trabajo por lotes de reafirmación separado después de completar la planificación maestra (siempre que _Reafirmación automática para la optimización de la planificación_ se haya habilitado en [Administración de características](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)). Tenga en cuenta que la puesta en firme automática para la optimización de la planificación se basa en la fecha del pedido (fecha de inicio), no en la fecha del requisito (fecha de finalización). Este comportamiento asegura que la reafirmación de las órdenes planificadas se produzca a su debido tiempo, sin tener que incluir el tiempo de entrega en el límite del tiempo de reafirmación. |
| Puesta en firme | Registros de cobertura de artículos con puesta en firme automática establecida: : _\#_ | En la versión 10.0.7 y posteriores, la puesta en firma automática se admite como un trabajo por lotes de reafirmación separado después de completar la planificación maestra (siempre que _Reafirmación automática para la optimización de la planificación_ se haya habilitado en [Administración de características](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)). Tenga en cuenta que la puesta en firme automática para la optimización de la planificación se basa en la fecha del pedido (fecha de inicio), no en la fecha del requisito (fecha de finalización). Este comportamiento asegura que la reafirmación de las órdenes planificadas se produzca a su debido tiempo, sin tener que incluir el tiempo de entrega en el límite del tiempo de reafirmación. |
| Puesta en firme | Planes maestros con puesta en firme automática establecida: _\#_ | En la versión 10.0.7 y posteriores, la puesta en firma automática se admite como un trabajo por lotes de reafirmación separado después de completar la planificación maestra (siempre que _Reafirmación automática para la optimización de la planificación_ se haya habilitado en [Administración de características](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)). Tenga en cuenta que la puesta en firme automática para la optimización de la planificación se basa en la fecha del pedido (fecha de inicio), no en la fecha del requisito (fecha de finalización). Este comportamiento asegura que la reafirmación de las órdenes planificadas se produzca a su debido tiempo, sin tener que incluir el tiempo de entrega en el límite del tiempo de reafirmación. |
| FitAnalysisPlanningItems | Artículos de planificación: _\#_ | Esta característica está pendiente. Actualmente, los elementos de planificación se manejan como elementos normales cuando la optimización de la planificación está habilitada. |
| Previsión | Grupos de cobertura con "Incluir pedidos de empresas vinculadas" habilitado: _\#_ | Esta característica está pendiente. Actualmente, la planificación maestra no incluye la demanda planificada descendente cuando la optimización de la planificación está habilitada, independientemente de esta configuración. Tenga en cuenta que los pedidos liberados/puestos en firme aún funcionan con la funcionalidad entre empresas vinculadas normal y cubrirán la mayoría de los escenarios. |
| Previsión | Grupos de cobertura con la configuración "Reducir pronóstico por" establecida en un valor diferente a "Pedidos": _\#_ | De forma predeterminada, la optimización de la planificación utiliza "Reducir pronóstico por" para los pedidos, independientemente de esta configuración. |
| Previsión | Modelos de previsión con submodelos: _\#_ | Esta característica está pendiente. Actualmente, los pronósticos que usan submodelos no son compatibles cuando la optimización de la planificación está habilitada. Se ignorarán, independientemente de esta configuración. |
| Previsión | Planes maestros con "Incluir pronóstico de suministro" habilitado: _\#_ | Esta característica está pendiente. Actualmente, las previsiones de suministro no son compatibles cuando la optimización de la planificación está habilitada. Se ignorarán, independientemente de esta configuración. |
| Congelar límite de tiempo | Grupos de cobertura con límite de tiempo congelado establecido: _\#_ | El límite de tiempo congelado no se usa con frecuencia y actualmente no hay planes para incluirlo para la optimización de la planificación. Actualmente, la configuración del límite de tiempo contelado se ignora cuando la optimización de planificación está habilitada, independientemente de esta configuración. |
| Congelar límite de tiempo | Registros de cobertura de artículos con límite de tiempo congelado establecido: _\#_ | El límite de tiempo congelado no se usa con frecuencia y actualmente no hay planes para incluirlo para la optimización de la planificación. Actualmente, la configuración del límite de tiempo contelado se ignora cuando la optimización de planificación está habilitada, independientemente de esta configuración. |
| Congelar límite de tiempo | Planes maestros con límite de tiempo congelado establecido: _\#_ | El límite de tiempo congelado no se usa con frecuencia y actualmente no hay planes para incluirlo para la optimización de la planificación. Actualmente, la configuración del límite de tiempo contelado se ignora cuando la optimización de planificación está habilitada, independientemente de esta configuración. |
| Empresas vinculadas | Planes maestros que incluyen demanda planificada descendente: _\#_ | Esta característica está pendiente. Actualmente, la planificación maestra no incluye la demanda planificada descendente cuando la optimización de la planificación está habilitada, independientemente de esta configuración. Tenga en cuenta que los pedidos liberados/puestos en firme aún funcionan con la funcionalidad entre empresas vinculadas normal y cubrirán la mayoría de los escenarios. |
| Kanban | Registros de cobertura de artículos con kanban de tipo de pedido planificado: _\#_ | Esta característica está pendiente. Actualmente, la cobertura de artículos que se establece en kanban se ignorará cuando la optimización de la planificación esté habilitada. El tipo de orden planificada kanban creará una advertencia durante la planificación maestra y se crearán órdenes de compra planificadas para cubrir la demanda relacionada. |
| Kanban | Artículos con kanban de tipo de pedido predeterminado: _\#_ | Actualmente, un tipo de pedido predeterminado que se establece en kanban se ignora cuando la optimización de la planificación está habilitada. El tipo predeterminado de orden planificada kanban creará una advertencia durante la planificación maestra y se crearán órdenes de compra planificadas para cubrir la demanda relacionada. |
| Producción | Líneas de L. MAT con redondeo o configuración múltiple: _\#_ | Esta característica está pendiente. Actualmente, el redondeo y las configuraciones múltiples se ignoran en las líneas de la lista de materiales cuando la optimización de la planificación está habilitada, independientemente de esta configuración. |
| Producción | L. MAT/líneas de fórmula con medida de fórmula: _\#_ | Esta característica está pendiente. Actualmente, la medida de fórmula se ignora en las líneas de la lista de materiales y la fórmula cuando la optimización de la planificación está habilitada, independientemente de esta configuración. |
| Producción | L. MAT/líneas de fórmula con sustitución de artículos (grupos de planes): _\#_ | Esta característica está pendiente. Actualmente, la sustitución de artículos (grupos de plan) se ignora en las líneas de la lista de materiales y la fórmula cuando la optimización de la planificación está habilitada, independientemente de esta configuración. |
| Producción | L. MAT/líneas de fórmula con cantidad negativa: _\#_ | Esta característica está pendiente. Las líneas de lista de materiales y de fórmula que tienen una cantidad negativa se incluirán con una cantidad de 0 (cero) y se emitirá una advertencia cuando se habilite la optimización de la planificación. |
| Producción | L. MAT/líneas de fórmula con consumo de recursos: _\#_ | Esta característica está pendiente. Actualmente, las líneas de BOM y fórmulas que tienen un consumo de recursos se ignoran cuando la optimización de la planificación está habilitada. |
| Producción | L. MAT/líneas de fórmula con consumo de pasos: _\#_ | Esta característica está pendiente. Actualmente, el consumo de pasos se ignora en las líneas de la lista de materiales y la fórmula cuando la optimización de la planificación está habilitada. |
| Producción | L. MAT con residuo constante o residuo variable definido: _\#_ | Esta característica está pendiente. Actualmente, el rechazo constante y el rechazo variable que se definen en las listas de materiales se ignoran cuando la optimización de la planificación está habilitada. |
| Producción | L. MAT con subcontratación: _\#_ | Esta característica está pendiente. Actualmente, la configuración de la subcontratación en las listas de materiales se ignora cuando la optimización de la planificación está habilitada, independientemente de esta configuración. |
| Producción | L. MAT sin sitio: _\#_ | Esta característica está pendiente. Actualmente, las listas de materiales sin un sitio se ignoran cuando la optimización de la planificación está habilitada. |
| Producción | Demanda con requisitos específicos de L. MAT o ruta definidos: _\#_ | Esta característica está pendiente. Actualmente, los requisitos de ruta o lista de materiales específicos que se definen en la demanda (como una sublista de materiales o una ruta secundaria en un pedido de cliente) se ignoran cuando la optimización de la planificación está habilitada. Se utilizará la lista de materiales o la ruta estándar, independientemente de esta configuración. |
| Producción | Versiones de fórmula con coproductos o productos derivados: _\#_ | Esta característica está pendiente. Actualmente, los coproductos y subproductos asociados con la versión de la fórmula se ignoran cuando la optimización de la planificación está habilitada. |
| Producción | Versiones de fórmula con rendimiento: _\#_ | Esta característica está pendiente. Actualmente, el rendimiento asociado con la versión de la fórmula se ignora cuando la optimización de la planificación está habilitada. |
| Producción | Planes que incluyen la secuenciación: _\#_ | Esta característica está pendiente. Actualmente, la secuenciación se ignora cuando la optimización de planificación está habilitada, independientemente de esta configuración. |
| Producción | Pedidos de producción emitidos que no se han iniciado, cuando el inicio programado es anterior al día de hoy: _\#_ | Esta característica está pendiente. |
| Producción | Recursos programados con capacidad finita: _\#_ | Esta característica está pendiente. Actualmente, los recursos que están programados con capacidad finita se ignoran cuando la optimización de la planificación está habilitada. La programación se realiza en función del tiempo de entrega predeterminado del producto. |
| Producción | Rutas usadas en la planificación: _\#_ | Esta característica está pendiente. Actualmente, las rutas se ignoran cuando la optimización de la planificación está habilitada. Se utiliza el tiempo de entrega predeterminado del producto. |
| Producción | Reserva de línea de ventas mediante expansión: _\#_ | La reserva de línea de ventas mediante expansión no se admite cuando la optimización de la planificación está habilitada. |
| Producción | Programación con expansión de pedidos de producción: _\#_ | La programación con expansión de pedidos de producción no se admite cuando la optimización de la planificación está habilitada. Los pedidos de producción se pueden programar individualmente. |
| Solicitud de presupuestos | Planes maestros con solicitudes de presupuestos habilitadas: _\#_ | Esta característica está pendiente. Actualmente, las solicitudes de presupuesto (RFQ) no se consideran demanda cuando la optimización de la planificación está habilitada. Se ignorarán, independientemente de esta configuración. |
| Solicitudes | Planes maestros con solicitudes habilitadas: _\#_ | Esta característica está pendiente. Actualmente, las solicitudes no se consideran cuando la optimización de la planificación está habilitada. Se ignorarán, independientemente de esta configuración. |
| Márgenes de seguridad | Grupos de cobertura con margen de seguridad: _\#_ | Esta característica está pendiente. Actualmente, el margen de seguridad se ignora cuando la optimización de la planificación está habilitada. Para compensar este comportamiento, puede aumentar el tiempo de espera para que incluya el margen de seguridad. |
| Márgenes de seguridad | Planes maestros con margen de seguridad: _\#_ | Esta característica está pendiente. Actualmente, el margen de seguridad se ignora cuando la optimización de planificación está habilitada, independientemente de esta configuración. Para compensar este comportamiento, puede aumentar el tiempo de espera para que incluya el margen de seguridad. |
| Cumplimiento de existencias de seguridad | Registros de cobertura de artículos con "Cumplimiento mínimo" diferente de "Fecha de hoy + tiempo de adquisición": _\#_ | La optimización de la planificación siempre utiliza *Fecha de hoy + tiempo de adquisición*. Este cambio se realiza para prepararse para una configuración de planificación simplificada en el futuro y para proporcionar un resultado procesable. Si no se incluye el tiempo de adquisición para el stock de seguridad, los pedidos planificados que se creen para el inventario disponible bajo actual siempre se retrasarán debido al tiempo de entrega. Este comportamiento puede causar ruido significativo y órdenes planificadas no deseadas. La mejor práctica es cambiar la configuración para que se use *Fecha de hoy + tiempo de adquisición*. |
| Presupuestos de ventas | Planes maestros con presupuestos de ventas habilitados: _\#_ | Esta característica está pendiente. Actualmente, los presupuestos no se consideran cuando la optimización de la planificación está habilitada. Se ignorarán, independientemente de esta configuración. |
| Vida útil | Planes maestros con vida útil habilitada: _\#_ | Esta característica está pendiente. Actualmente, la vida útil no se considera cuando la optimización de planificación está habilitada, independientemente de esta configuración. |

## <a name="related-resources"></a>Recursos relacionados

[Visión general de la optimización de la planificación](planning-optimization-overview.md)

[Introducción a la optimización de la planificación](get-started.md)

[Ver el historial del plan y los registros de planificación](plan-history-logs.md)

[Aplicar filtros a un plan](plan-filters.md)

[Cancelar un trabajo de planificación](cancel-planning-job.md)
