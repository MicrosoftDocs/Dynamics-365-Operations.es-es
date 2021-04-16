---
title: Contenido de compensaciones y prestaciones de Power BI
description: Este tema describe el contenido de compensaciones y prestaciones de Power BI.
author: jcart1106
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 263914
ms.assetid: 18634bb5-3341-42f2-9cc9-7b04708b506b
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: ec8df69423add8f118d3ce1ad4bae95ea6abb469
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5754431"
---
# <a name="compensation-and-benefits-power-bi-content"></a>Contenido de compensaciones y prestaciones de Power BI

[!include [banner](../includes/banner.md)]

Este tema describe el contenido de compensaciones y prestaciones de Power BI. 

## <a name="reports-that-are-included-in-the-content-pack"></a>Informes que se incluyen en el paquete de contenido
Tras conectar el paquete de contenido con sus datos, los informes muestran los datos de su organización. Si nunca antes ha utilizado Microsoft Power BI, puede aprender más de la aplicación en [Aprendizaje dirigido para Power BI](https://powerbi.microsoft.com/guided-learning/?WT.mc_id=PBIService_GetData). Los informes incluidos en el paquete de contenido tienen gráficos y tablas que contienen información adicional. En la siguiente tabla se describen los informes.

| Informe                     | Contenido                                                                                                                              |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------|
| Análisis de compensaciones y prestaciones | Empleados por hora y asalariados por empresa, sueldo por hora medio, sueldo medio de asalariado, empleados por tipo de empleo e inscripción del plan |
| Prestaciones del empleado          | Inscripción del empleado por prestación seleccionada                                                                                               |

Puede filtrar los gráficos e iconos en estos informes y anclar los gráficos e iconos al panel de información. Para obtener más información acerca de cómo filtrar y anclar en Power BI, consulte [Crear y configurar un panel de información](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Comprensión del modelo de datos y de las entidades
Los datos de la aplicación se utilizan para rellenar los informes del paquete de contenido sobre compensaciones y prestaciones. En la tabla siguiente se muestran las entidades en las que se basaba el paquete de contenido.

| Entidad                            | Contenido                                                                                                   | Relaciones con otras entidades |
|-----------------------------------|------------------------------------------------------------------------------------------------------------|-----------------------------------|
| Workforce\_CalendarOffset         | Desplazamientos del calendario para dividir informes                                                                          | Workforce\_PastPositionAssignment, Workforce\_PositionTrend, Workforce\_WorkerTrend, Workforce\_TerminatedWorker |
| Workforce\_Company                | Empresas para filtrar informes por                                                                             | Workforce\_CurrentCompensation, Workforce\_CurrentWorker, Workforce\_TerminatedWorker, Workforce\_WorkerTrend |
| Workforce\_Compensation           | Índice salaria y frecuencia a lo largo del tiempo                                                                           | Workforce\_CurrentCompensation, Workforce\_CurrentWorker, Workforce\_TerminatedWorker, Workforce\_WorkerTrend |
| Workforce\_CurrentCompensation    | Índice salarial y frecuencia a partir de la fecha actual                                                              | Workforce\_Company, Workforce\_Compensation, Workforce\_Demographics, Workforce\_Job, Workforce\_Position |
| Workforce\_CurrentPosition        | Puestos a partir de la fecha actual, equivalentes a tiempo completo (FTE), vacantes y puestos vacantes a ocupados | Workforce\_Job, Workforce\_Position |
| Workforce\_CurrentWorker          | Trabajadores a partir de la fecha actual, edad y plantilla                                                         | Workforce\_Company, Workforce\_Compensation, Workforce\_GeographicLocation, Workforce\_Performance, Workforce\_WorkerName, Workforce\_ReportsToWorkerName, Workforce\_WorkerTitle, Workforce\_Demographics, Workforce\_Job, Workforce\_Employment, Workforce\_Position, Workforce\_WorkerBenefit |
| Workforce\_Date                   | Días, semanas, meses y años                                                                             | Workforce\_PastPositionAssignment, Workforce\_PositionTrend, Workforce\_TerminatedWorker, Workforce\_WorkerTrend |
| Workforce\_Demographics           | Fecha de nacimiento, género, origen étnico y estado civil                                                   | Workforce\_CurrentWorker, Workforce\_TerminatedWorker, Workforce\_WorkerTrend |
| Workforce\_Employment             | Fecha de inicio, fecha final y fecha de transición                                                                  | Workforce\_CurrentWorker, Workforce\_TerminatedWorker, Workforce\_WorkerTrend |
| Workforce\_GeographicLocation     | Ciudad, provincia, código postal y comunidad autónoma                                                           | Workforce\_CurrentWorker, Workforce\_TerminatedWorker, Workforce\_WorkerTrend |
| Workforce\_Job                    | Función tipo y cargo                                                                                  | Workforce\_CurrentPosition, Workforce\_CurrentWorker |
| Workforce\_PastPositionAssignment | Motivo de la asignación, fecha de inicio, fecha final y trabajo                                                           | Workforce\_CalendarOffset, Workforce\_Date, Workforce\_Job, Workforce\_Position |
| Workforce\_Performance            | Calificación, descripción y modelo de calificación                                                                      | Workforce\_CurrentWorker, Workforce\_TerminatedWorker, Workforce\_WorkerTrend |
| Workforce\_Position               | Departamento, FTE, puesto, tipo de puesto y cargo                                                        | Workforce\_CurrentPosition, Workforce\_CurrentWorker |
| Workforce\_PositionTrend          | Puestos a lo largo del tiempo, FTE y trabajo                                                                          | Workforce\_CalendarOffset, Workforce\_Date, Workforce\_Job, Workforce\_Position |
| Workforce\_ReportsToWorkerName    | Nombre, apellido y nombre completo                                                                       | Workforce\_CurrentWorker, Workforce\_TerminatedWorker, Workforce\_WorkerTrend |
| Workforce\_Skill                  | Aptitudes, tipo de aptitud y calificación                                                                              | |
| Workforce\_TerminatedWorker       | Trabajadores terminados, fecha de finalización, cargo, puesto y trabajo                                             | Workforce\_Company, Workforce\_Compensation, Workforce\_GeographicLocation, Workforce\_Performance, Workforce\_WorkerName, Workforce\_ReportsToWorkerName, Workforce\_CalendarOffset, Workforces\_Date, Workforce\_WorkerTitle, Workforce\_Demographics, Workforce\_Employment, Workforce\_Job, Workforce\_Position, Workforce\_WorkerBenefit |
| Workforce\_WorkerBenefit          | Fecha de vigencia, opción de prestación, plan de prestaciones y tipo de prestación                                             | Workforce\_CurrentWorker, Workforce\_TerminatedWorker, Workforce\_WorkerTrend |
| Workforce\_WorkerName             | Nombre, apellido y nombre completo                                                                       | Workforce\_CurrentWorker, Workforce\_TerminatedWorker, Workforce\_WorkerTrend |
| Workforce\_WorkerTitle            | Cargo y fecha de antigüedad                                                                                   | Workforce\_CurrentWorker, Workforce\_TerminatedWorker, Workforce\_WorkerTrend |
| Workforce\_WorkerTrend            | Trabajadores a lo largo del tiempo, plantilla, empresa y puesto                                                        | Workforce\_Company, Workforce\_Compensation, Workforce\_GeographicLocation, Workforce\_Performance, Workforce\_WorkerName, Workforce\_ReportsToWorkerName, Workforce\_CalendarOffset, Workforces\_Date, Workforce\_WorkerTitle, Workforce\_Demographics, Workforce\_Employment, Workforce\_Job, Workforce\_WorkerBenefit |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]