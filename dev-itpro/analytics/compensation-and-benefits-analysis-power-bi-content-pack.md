---
title: Contenido de Power BI de compensaciones y de prestaciones
description: "En este tema se describe Dynamics 365 for Operations, contenido de Power BI de compensaciones y de prestaciones. Explica cómo tener acceso a los informes que se incluyen en el paquete de contenido, y proporciona información acerca del modelo de datos y las entidades que se utilizaron para generar el paquete del contenido."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations
ms.custom: 263914
ms.assetid: 18634bb5-3341-42f2-9cc9-7b04708b506b
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 557f9218032e2b1160b6ea0631ada951353d2afd
ms.lasthandoff: 03/31/2017


---

# <a name="compensation-and-benefits-power-bi-content"></a>Contenido de Power BI de compensaciones y de prestaciones

[!include[banner](../includes/banner.md)]


En este tema se describe Dynamics 365 for Operations, contenido de Power BI de compensaciones y de prestaciones. Explica cómo tener acceso a los informes que se incluyen en el paquete de contenido, y proporciona información acerca del modelo de datos y las entidades que se utilizaron para generar el paquete del contenido.

<a name="accessing-the-content-pack"></a>Acceso al paquete de contenido
--------------------------

El paquete de contenido de compensaciones y beneficios se encuentra en la biblioteca de activos compartidos de los Servicios de ciclo de vida (LCS) de Microsoft Dynamics. Para obtener más información sobre cómo descargar el paquete de contenido y conectarlo a los datos de Microsoft Dynamics 365 for Operations, consulte [Contenido de Power BI en LCS en Microsoft y sus socios](power-bi-content-microsoft-partners.md).

## <a name="reports-that-are-included-in-the-content-pack"></a>Informes que se incluyen en el paquete de contenido
Tras la conexión del paquete de contenido con sus datos de Dynamics 365 for Operations, los informes muestran los datos de su organización. Si nunca antes ha utilizado Microsoft Power BI, consulte [Aprendizaje dirigido para Power BI](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData) para obtener más información acerca de la aplicación. Los informes incluidos en el paquete de contenido tienen gráficos y tablas que contienen información adicional. En la siguiente tabla se describen los informes.

| Informe                     | Contenido                                                                                                                              |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------|
| Análisis de compensaciones y prestaciones | Empleados por hora y asalariados por empresa, sueldo por hora medio, sueldo medio de asalariado, empleados por tipo de empleo e inscripción del plan |
| Prestaciones del empleado          | Inscripción del empleado por prestación seleccionada                                                                                               |

Puede filtrar los gráficos e iconos en estos informes y anclar los gráficos e iconos al panel de información. Para obtener más información acerca de cómo filtrar y anclar en Power BI, consulte [Crear y configurar un panel de información](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Comprensión del modelo de datos y de las entidades
Los datos de Dynamics 365 for Operations se utilizan para rellenar los informes del paquete de contenido sobre compensaciones y prestaciones. En la tabla siguiente se muestran las entidades en las que se basaba el paquete de contenido.

| Entidad                            | Contenido                                                                                                   | Relaciones con otras entidades                                                                                                                                                                                                                                                                                                |
|-----------------------------------|------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Workforce\_CalendarOffset         | Desplazamientos del calendario para dividir informes                                                                          | Workforce\_PastPositionAssignment Workforce\_PositionTrend Workorce\_WorkerTrend Workforce\_TerminatedWorker                                                                                                                                                                                                                     |
| Workforce\_Company                | Empresas para filtrar informes por                                                                             | Workforce\_CurrentCompensation Workforce\_CurrentWorker Workforce\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                        |
| Workforce\_Compensation           | Índice salaria y frecuencia a lo largo del tiempo                                                                           | Workforce\_CurrentCompensation Workforce\_CurrentWorker Workforce\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                        |
| Workforce\_CurrentCompensation    | Índice salarial y frecuencia a partir de la fecha actual                                                              | Workforce\_Company Workforce\_Compensation Workforce\_Demographics Workforce\_Job Workforce\_Position                                                                                                                                                                                                                            |
| Workforce\_CurrentPosition        | Puestos a partir de la fecha actual, equivalentes a tiempo completo (FTE), vacantes y puestos vacantes a ocupados | Workforce\_Job Workforce\_Position                                                                                                                                                                                                                                                                                               |
| Workforce\_CurrentWorker          | Trabajadores a partir de la fecha actual, edad y plantilla                                                         | Workforce\_Company Workforce\_Compensation Workforce\_GeographicLocation Workforce\_Performance Workforce\_WorkerName Workforce\_ReportsToWorkerName Workforce\_WorkerTitle Workforce\_Demographics Workforce\_Job Workforce\_Employment Workforce\_Position Workforce\_WorkerBenefit                                            |
| Workforce\_Date                   | Días, semanas, meses y años                                                                             | Workforce\_PastPositionAssignment Workforce\_PositionTrend Workforce\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                     |
| Workforce\_Demographics           | Fecha de nacimiento, género, origen étnico y estado civil                                                   | Workforce\_CurrentWorker Workforce\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                                                       |
| Workforce\_Employment             | Fecha de inicio, fecha final y fecha de transición                                                                  | Workforce\_CurrentWorker Workforce\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                                                       |
| Workforce\_GeographicLocation     | Ciudad, provincia, código postal y comunidad autónoma                                                           | Workforce\_CurrentWorker Workforce\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                                                       |
| Workforce\_Job                    | Función tipo y cargo                                                                                  | Workforce\_CurrentPosition Workforce\_CurrentWorker                                                                                                                                                                                                                                                                              |
| Workforce\_PastPositionAssignment | Motivo de la asignación, fecha de inicio, fecha final y trabajo                                                           | Workforce\_CalendarOffset Workforce\_Date Workforce\_Job Workforce\_Position                                                                                                                                                                                                                                                     |
| Workforce\_Performance            | Calificación, descripción y modelo de calificación                                                                      | Workforce\_CurrentWorker Workforce\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                                                       |
| Workforce\_Position               | Departamento, FTE, puesto, tipo de puesto y cargo                                                        | Workforce\_CurrentPosition Workforce\_CurrentWorker                                                                                                                                                                                                                                                                              |
| Workforce\_PositionTrend          | Puestos a lo largo del tiempo, FTE y trabajo                                                                          | Workforce\_CalendarOffset Workforce\_Date Workforce\_Job Workforce\_Position                                                                                                                                                                                                                                                     |
| Workforce\_ReportsToWorkerName    | Nombre, apellido y nombre completo                                                                       | Workforce\_CurrentWorker Workforce\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                                                       |
| Workforce\_Skill                  | Aptitudes, tipo de aptitud y calificación                                                                              |                                                                                                                                                                                                                                                                                                                                  |
| Workforce\_TerminatedWorker       | Trabajadores terminados, fecha de finalización, cargo, puesto y trabajo                                             | Workforce\_Company Workforce\_Compensation Workforce\_GeographicLocation Workforce\_Performance Workforce\_WorkerName Workforce\_ReportsToWorkerName Workforce\_CalendarOffset Workforces\_Date Workforce\_WorkerTitle Workforce\_Demographics Workforce\_Employment Workforce\_Job Workforce\_Position Workforce\_WorkerBenefit |
| Workforce\_WorkerBenefit          | Fecha de vigencia, opción de prestación, plan de prestaciones y tipo de prestación                                             | Workforce\_CurrentWorker Workforce\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                                                       |
| Workforce\_WorkerName             | Nombre, apellido y nombre completo                                                                       | Workforce\_CurrentWorker Workforce\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                                                       |
| Workforce\_WorkerTitle            | Cargo y fecha de antigüedad                                                                                   | Workforce\_CurrentWorker Workforce\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                                                       |
| Workorce\_WorkerTrend             | Trabajadores a lo largo del tiempo, plantilla, empresa y puesto                                                        | Workforce\_Company Workforce\_Compensation Workforce\_GeographicLocation Workforce\_Performance Workforce\_WorkerName Workforce\_ReportsToWorkerName Workforce\_CalendarOffset Workforces\_Date Workforce\_WorkerTitle Workforce\_Demographics Workforce\_Employment Workforce\_Job Workforce\_WorkerBenefit                     |

Estas entidades se usaban para crear medidas calculadas en el modelo de datos. Estas medidas calculadas se utilizan para calcular los indicadores de rendimiento clave (KPI) y los informes que se utilizan en el paquete del contenido. Si desea incluir cálculos adicionales en sus informes y en el panel de información, puede descargar y modificar el archivo CompensationandBenefits.pbix en LCS. Este archivo es el modelo de datos predeterminado usado para crear el paquete del contenido. Una vez que haya realizado las modificaciones, puede crear un panel de información y paquete de contenido organizativo que contienen la información que ha agregado.

## <a name="additional-resources"></a>Recursos adicionales
Estos son algunos vínculos útiles relacionados con las entidades y la creación de contenido de Power BI:

-   [Entidades de datos](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Creación de paquetes de contenido organizativo](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelado de datos con Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Adición de iconos de Power BI a espacios de trabajo](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)





