---
title: Contenido de Power BI sobre competencias y desarrollo de empleados
description: "En este tema se describe Finance and Operations, contenido de Power BI sobre competencias y desarrollo de empleados Explica cómo tener acceso a los informes que se incluyen en el paquete de contenido, y proporciona información acerca del modelo de datos y las entidades que se utilizaron para generar el paquete del contenido."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations, UnifiedOperations
ms.custom: 263894
ms.assetid: 7d375d8a-b2de-4bec-b575-93d1d4521b79
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: f5b3c180f0a9d60fa5d4d8398daf79a14da2d6f4
ms.contentlocale: es-es
ms.lasthandoff: 06/13/2017


---

# Contenido de Power BI sobre competencias y desarrollo de empleados
<a id="employee-competencies-and-development-power-bi-content" class="xliff"></a>

[!include[banner](../includes/banner.md)]


En este tema se describe Finance and Operations, contenido de Power BI sobre competencias y desarrollo de empleados Explica cómo tener acceso a los informes que se incluyen en el paquete de contenido, y proporciona información acerca del modelo de datos y las entidades que se utilizaron para generar el paquete del contenido.

Acceso al paquete de contenido
<a id="accessing-the-content-pack" class="xliff"></a>
--------------------------

El paquete de contenido sobre competencias y desarrollo de empleados se encuentra en la biblioteca de activos compartidos de los Servicios de ciclo de vida (LCS) de Microsoft Dynamics. Para obtener más información sobre cómo descargar el paquete de contenido y conectarlo a los datos de Microsoft Dynamics 365 for Finance and Operations consulte [Contenido de Power BI en LCS en Microsoft y sus socios](power-bi-content-microsoft-partners.md).

## Informes que se incluyen en el paquete de contenido
<a id="reports-that-are-included-in-the-content-pack" class="xliff"></a>
Tras la conexión del paquete de contenido con sus datos de Finance and Operations, los informes muestran los datos de su organización. Si nunca antes ha utilizado Microsoft Power BI, consulte [Aprendizaje dirigido para Power BI](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData) para obtener más información acerca de la aplicación. Los informes incluidos en el paquete de contenido tienen gráficos y tablas que contienen información adicional. En la siguiente tabla se describen los informes.

| Informe                            | Contenido                                               |
|-----------------------------------|--------------------------------------------------------|
| Análisis de competencia y desarrollo | Tipos de aptitudes de miembros del equipo y aptitudes de miembros del equipo por tipo |
| Perfil de aptitudes                     | Perfil de aptitudes para el empleado seleccionado                |
| Análisis de aptitudes                    | Aptitudes por tipo y clasificación                              |

Puede filtrar los gráficos e iconos en estos informes y anclar los gráficos e iconos al panel de información. Para obtener más información acerca de cómo filtrar y anclar en Power BI, consulte [Crear y configurar un panel de información](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## Comprensión del modelo de datos y de las entidades
<a id="understanding-the-data-model-and-entities" class="xliff"></a>
Los datos de Finance and Operations se utilizan para rellenar los informes del paquete de contenido sobre competencias y desarrollo de empleados. En la tabla siguiente se muestran las entidades en las que se basaba el paquete de contenido.

| Entidad                            | Contenido                                                                                                   | Relaciones con otras entidades                                                                                                                                                                                                                                                                       |
|-----------------------------------|------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Workforce\_CalendarOffset         | Desplazamientos del calendario para dividir informes                                                                          |                                                                                                                                                                                                                                                                                                         |
| Workforce\_Company                | Empresas para filtrar informes por                                                                             |                                                                                                                                                                                                                                                                                                         |
| Workforce\_Compensation           | Índice salaria y frecuencia a lo largo del tiempo                                                                           |                                                                                                                                                                                                                                                                                                         |
| Workforce\_CurrentCompensation    | Índice salarial y frecuencia a partir de la fecha actual                                                              | Workforce\_Company Workforce\_CurrentCompensation Workforce\_Demographics Workforce\_Job Workforce\_Position                                                                                                                                                                                            |
| Workforce\_CurrentPosition        | Puestos a partir de la fecha actual, equivalentes a tiempo completo (FTE), vacantes y puestos vacantes a ocupados | Workforce\_Job Workforce\_Position                                                                                                                                                                                                                                                                      |
| Workforce\_CurrentWorker          | Trabajadores a partir de la fecha actual, edad y plantilla                                                         | Workforce\_Company Workforce\_Compensation Workforce\_GeographicLocation Workforce\_Performance Workforce\_PersonSkill Workforce\_WorkerName Workforce\_ReportsToWorkerName Workforce\_WorkerTitle Workforce\_Demographics Workforce\_Job Workforce\_Employment Workforce\_Position                     |
| Workforce\_Date                   | Días, semanas, meses y años                                                                             |                                                                                                                                                                                                                                                                                                         |
| Workforce\_Demographics           | Fecha de nacimiento, género, origen étnico y estado civil                                                   |                                                                                                                                                                                                                                                                                                         |
| Workforce\_Employment             | Fecha de inicio, fecha final y fecha de transición                                                                  |                                                                                                                                                                                                                                                                                                         |
| Workforce\_GeographicLocation     | Ciudad, provincia, código postal y comunidad autónoma                                                           |                                                                                                                                                                                                                                                                                                         |
| Workforce\_Job                    | Función tipo y cargo                                                                                  |                                                                                                                                                                                                                                                                                                         |
| Workforce\_JobPreferredSkill      | Importancia, clasificación, aptitud y nivel de aptitud                                                                 | Workforce\_Skill Workforce\_Job                                                                                                                                                                                                                                                                         |
| Workforce\_PastPositionAssignment | Motivo de la asignación, fecha de inicio, fecha final y trabajo                                                           | Workforce\_ClaendarOffset Workforce\_Date Workforce\_Job Workforce\_Position                                                                                                                                                                                                                            |
| Workforce\_Performance            | Calificación, descripción y modelo de calificación                                                                      |                                                                                                                                                                                                                                                                                                         |
| Workforce\_PersonSkill            | Nivel, fecha de nivel y aptitud                                                                               | Workforce\_Skill                                                                                                                                                                                                                                                                                        |
| Workforce\_PersonSkillAnalysis    | Certificación, nivel, fecha de nivel y aptitud                                                                    | Workforce\_WorkerName Workforce\_Skill                                                                                                                                                                                                                                                                  |
| Workforce\_Position               | Departamento, FTE, puesto, tipo de puesto y cargo                                                        |                                                                                                                                                                                                                                                                                                         |
| Workforce\_PositionTrend          | Puestos a lo largo del tiempo, FTE y trabajo                                                                          | Workforce\_CalendarOffset Workforce\_Date Workforce\_Job Workforce\_Position                                                                                                                                                                                                                            |
| Workforce\_ReportsToWorkerName    | Nombre, apellido y nombre completo                                                                       |                                                                                                                                                                                                                                                                                                         |
| Workforce\_Skill                  | Aptitudes, tipo de aptitud y calificación                                                                              |                                                                                                                                                                                                                                                                                                         |
| Workforce\_TerminatedWorker       | Trabajadores terminados, fecha de finalización, cargo, puesto y trabajo                                             | Workforce\_Company Workforce\_Compensation Workforce\_GeographicLocation Workforce\_Performance Workforce\_WorkerName Workforce\_ReportsToWorkerName Workforce\_CalendarOffset Workforces\_Date Workforce\_WorkerTitle Workforce\_Demographics Workforce\_Employment Workforce\_Job Workforce\_Position |
| Workforce\_WorkerName             | Nombre, apellido y nombre completo                                                                       |                                                                                                                                                                                                                                                                                                         |
| Workforce\_WorkerTitle            | Cargo y fecha de antigüedad                                                                                   |                                                                                                                                                                                                                                                                                                         |
| Workorce\_WorkerTrend             | Trabajadores a lo largo del tiempo, plantilla, empresa y puesto                                                        | Workforce\_Company Workforce\_Compensation Workforce\_GeographicLocation Workforce\_Performance Workforce\_WorkerName Workforce\_ReportsToWorkerName Workforce\_CalendarOffset Workforces\_Date Workforce\_WorkerTitle Workforce\_Demographics Workforce\_Employment Workforce\_Job                     |

Estas entidades se usaban para crear medidas calculadas en el modelo de datos. Estas medidas calculadas se utilizan para calcular los indicadores de rendimiento clave (KPI) y los informes que se utilizan en el paquete del contenido. Si desea incluir cálculos adicionales en sus informes y en el panel de información, puede descargar y modificar el archivo CompetenciesandDevelopment.pbix en LCS. Este archivo es el modelo de datos predeterminado usado para crear el paquete del contenido. Una vez que haya realizado las modificaciones, puede crear un panel de información y paquete de contenido organizativo que contienen la información que ha agregado.

## Recursos adicionales
<a id="additional-resources" class="xliff"></a>
Estos son algunos vínculos útiles relacionados con las entidades y la creación de contenido de Power BI:

-   [Entidades de datos](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Creación de paquetes de contenido organizativo](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelado de datos con Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Adición de iconos de Power BI a espacios de trabajo](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)





