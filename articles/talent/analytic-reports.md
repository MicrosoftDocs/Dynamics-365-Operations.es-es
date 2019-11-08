---
title: Utilizar informes de análisis en Microsoft Dynamics 365 Talent - Attract
description: Este tema describe los informes analíticos para el proceso de contratación en Microsoft Dynamics 365 Talent - Attract
author: fewatson
manager: AnnBe
ms.date: 04/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: fewatson
ms.search.validFrom: 2019-04-30
ms.dyn365.ops.version: Talent April 2019 update
ms.openlocfilehash: 5a4d160e8c90725d5ea129a76fd48da1c5af7900
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2019
ms.locfileid: "2551527"
---
# <a name="use-analytic-reports-in-microsoft-dynamics-365-talent---attract"></a>Utilizar informes de análisis en Microsoft Dynamics 365 Talent - Attract

Los informes analíticos en Microsoft Dynamics 365 Talent: Attract proporcionan una solución de (OOTB) lista para usarse y obtener información del proceso de contratación. Entre las características disponibles se incluyen:

- **Análisis de trabajo:** haga clic en la pestaña **Análisis** dentro de las medidas de un trabajo en los candidatos al trabajo.
- **Centro de análisis:** haga clic en **Análisis** en la barra izquierda para ver las medidas agregadas a lo largo de los trabajos.
- **Seguridad específica de usuario:** el acceso a los informes se controla en Attract mediante [roles](security-attract.md) y el rol del participante en el trabajo.
- **Filtro cruzado:** haga clic en las imágenes en un informe para ver otras medidas filtradas por los datos seleccionados.

>[!NOTE] 
>- Esta característica está actualmente en [vista previa](access-preview-feature.md). Para probarla, debe tener el [**Complemento de contratación completo**](attract-comprehensive-hiring.md).
>- Todos los informes público de vista previa se muestran en inglés.
>- Los informes se actualizan cada 3 horas. La última hora de actualización (en la zona horaria local) se encuentra en la parte superior del informe. Los tiempos de actualización son una aproximación y varían en función del volumen de datos y carga del recurso en la región.

## <a name="job-analytics"></a>Análisis de trabajos

Los informes de Análisis de trabajo ofrecen una instantánea del proceso de contratación para un trabajo.  Entre las medidas clave están:

- Candidatos activos por etapa
- Origen del candidato
- Tipo de candidato (interno o externo)

## <a name="analytics-hub"></a>Centro de análisis

Los informes del Centro de análisis agregan datos a lo largo de los trabajos para revelar tendencias superficiales en el proceso de contratación. Attract incluye dos informes de OOTB: Componentes del resumen y el Análisis de embudo.

### <a name="pipeline-summary"></a>Resumen de proceso

El informe de resumen de proceso agrega los datos para las vacantes. Entre las medidas clave están:

- Candidatos en todos los trabajos por etapa
- Origen del candidato
- Vacantes por nivel de antigüedad

### <a name="funnel-analysis"></a>Análisis de embudo

El informe análisis de embudo agrega los datos para los trabajos que se han cerrado como ocupados. Entre las medidas clave están:

- Tiempo para contratar
- Métricas de conversión (manteniendo el puntero)
- Tasa de aceptación de la propuesta

Nota: para obtener el tiempo para contratar más preciso en el informe, se recomienda el uso de [Administración de la propuesta](offer-setup.md), una característica disponibles como parte del complemento de contratación completo.

>[!TIP] 
>Pruebe a mantener el puntero sobre los gráficos para obtener información adicional. Por ejemplo, al mantener el puntero sobre los gráficos de **Candidatos activos**, estos mostrarán los días medios en etapa. Analizar esta información puede proporcionar datos críticos para reducir el tiempo de contratación y permitir a los reclutadores centrarse en formas de reducir el tiempo empleado en cada etapa.

## <a name="user-specific-security"></a>Seguridad específica del usuario.

Los informes de Attract están accesibles para los [roles](security-attract.md) de Administradores, Leer todos, Reclutador y el Jefe de contratación. Los usuarios no asignados no tienen acceso a las páginas del informe de análisis (Análisis de trabajo y Centro de análisis)

Los informes de Análisis de trabajo muestran datos para el trabajo seleccionado. Los informes del Centro de análisis agregan datos a lo largo de todos los trabajos que puede ver un usuario. Los usuarios que pueden ver Mis trabajos y Todos los trabajos en la página de los trabajos tienen las mismas vistas disponibles en el Centro de análisis.

## <a name="cross-filter"></a>Filtro cruzado

Una de las grandes características de Power BI es la forma que todas las representaciones visuales en una página del informe se interconectan. Si selecciona un punto de datos en una de las representaciones visuales, el resto de representaciones visuales en la página que contengan ese dato cambiarán, basándose en esa selección. Descubra más y ver un ejemplo en [Cómo las representaciones cruzadas usan filtros cruzados en un informe de Power BI](https://docs.microsoft.com/power-bi/consumer/end-user-interactions).

## <a name="export-to-excel"></a>Exportar a Excel

Para ver los datos del informe en Excel, puede hacer clic en el menú de las opciones (tres puntos) en una representación visual y seleccionar **Exportar los datos subyacentes**. Los datos exportados se exportarán filtrados, respetando los permisos de usuario en Attract. Para obtener más información, consulte [Exportar los datos de visualizaciones](https://docs.microsoft.com/power-bi/visuals/power-bi-visualization-export-data).
