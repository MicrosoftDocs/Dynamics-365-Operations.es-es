---
title: Contenido de competencias y desarrollo de empleados de Power BI
description: Este tema describe el contenido en Power BI de Desarrollo y competencias de empleados.
author: jcart1106
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Operations
ms.custom: 263894
ms.assetid: 7d375d8a-b2de-4bec-b575-93d1d4521b79
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 1bc75da5deb6e0b40bb4f254f64b2f7f6d068a7a
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2181666"
---
# <a name="employee-competencies-and-development-power-bi-content"></a>Contenido de competencias y desarrollo de empleados de Power BI

[!include [banner](../includes/banner.md)]

Este tema describe el contenido en Power BI de Desarrollo y competencias de empleados. 

## <a name="reports-that-are-included-in-the-content-pack"></a>Informes que se incluyen en el paquete de contenido
Tras conectar el paquete de contenido con sus datos, los informes muestran los datos de su organización. Si nunca antes ha utilizado Microsoft Power BI, consulte [Aprendizaje dirigido para Power BI](https://powerbi.microsoft.com/guided-learning/?WT.mc_id=PBIService_GetData) para obtener más información acerca de la aplicación. Los informes incluidos en el paquete de contenido tienen gráficos y tablas que contienen información adicional. En la siguiente tabla se describen los informes.

| Informe                            | Contenido                                               |
|-----------------------------------|--------------------------------------------------------|
| Análisis de competencia y desarrollo | Tipos de aptitudes de miembros del equipo y aptitudes de miembros del equipo por tipo |
| Perfil de aptitudes                     | Perfil de aptitudes para el empleado seleccionado                |
| Análisis de aptitudes                    | Aptitudes por tipo y clasificación                              |

Puede filtrar los gráficos e iconos en estos informes y anclar los gráficos e iconos al panel de información. Para obtener más información acerca de cómo filtrar y anclar en Power BI, consulte [Crear y configurar un panel de información](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Comprensión del modelo de datos y de las entidades
Los datos de la aplicación se utilizan para rellenar los informes del paquete de contenido sobre competencias y desarrollo de empleados. En la tabla siguiente se muestran las entidades en las que se basaba el paquete de contenido.

| Entidad                            | Contenido                                                                                                   | Relaciones con otras entidades |
|-----------------------------------|------------------------------------------------------------------------------------------------------------|-----------------------------------|
| Workforce\_CalendarOffset         | Desplazamientos del calendario para dividir informes                                                                          | |
| Workforce\_Company                | Empresas para filtrar informes por                                                                             | |
| Workforce\_Compensation           | Índice salaria y frecuencia a lo largo del tiempo                                                                           | |
| Workforce\_CurrentCompensation    | Índice salarial y frecuencia a partir de la fecha actual                                                              | Workforce\_Company, Workforce\_CurrentCompensation, Workforce\_Demographics, Workforce\_Job, Workforce\_Position |
| Workforce\_CurrentPosition        | Puestos a partir de la fecha actual, equivalentes a tiempo completo (FTE), vacantes y puestos vacantes a ocupados | Workforce\_Job Workforce\_Position |
| Workforce\_CurrentWorker          | Trabajadores a partir de la fecha actual, edad y plantilla                                                         | Workforce\_Company Workforce\_Compensation, Workforce\_GeographicLocation, Workforce\_Performance, Workforce\_PersonSkill, Workforce\_WorkerName, Workforce\_ReportsToWorkerName, Workforce\_WorkerTitle, Workforce\_Demographics, Workforce\_Job, Workforce\_Employment, Workforce\_Position |
| Workforce\_Date                   | Días, semanas, meses y años                                                                             | |
| Workforce\_Demographics           | Fecha de nacimiento, género, origen étnico y estado civil                                                   | |
| Workforce\_Employment             | Fecha de inicio, fecha final y fecha de transición                                                                  | |
| Workforce\_GeographicLocation     | Ciudad, provincia, código postal y comunidad autónoma                                                           | |
| Workforce\_Job                    | Función tipo y cargo                                                                                  | |
| Workforce\_JobPreferredSkill      | Importancia, clasificación, aptitud y nivel de aptitud                                                                 | Workforce\_Skill, Workforce\_Job |
| Workforce\_PastPositionAssignment | Motivo de la asignación, fecha de inicio, fecha final y trabajo                                                           | Workforce\_CalendarOffset, Workforce\_Date, Workforce\_Job, Workforce\_Position |
| Workforce\_Performance            | Calificación, descripción y modelo de calificación                                                                      | |
| Workforce\_PersonSkill            | Nivel, fecha de nivel y aptitud                                                                               | Workforce\_Skill |
| Workforce\_PersonSkillAnalysis    | Certificación, nivel, fecha de nivel y aptitud                                                                    | Workforce\_WorkerName, Workforce\_Skill |
| Workforce\_Position               | Departamento, FTE, puesto, tipo de puesto y cargo                                                        | |
| Workforce\_PositionTrend          | Puestos a lo largo del tiempo, FTE y trabajo                                                                          | Workforce\_CalendarOffset, Workforce\_Date, Workforce\_Job, Workforce\_Position |
| Workforce\_ReportsToWorkerName    | Nombre, apellido y nombre completo                                                                       | |
| Workforce\_Skill                  | Aptitudes, tipo de aptitud y calificación                                                                              | |
| Workforce\_TerminatedWorker       | Trabajadores terminados, fecha de finalización, cargo, puesto y trabajo                                             | Workforce\_Company, Workforce\_Compensation, Workforce\_GeographicLocation, Workforce\_Performance, Workforce\_WorkerName, Workforce\_ReportsToWorkerName, Workforce\_CalendarOffset, Workforces\_Date, Workforce\_WorkerTitle, Workforce\_Demographics, Workforce\_Employment, Workforce\_Job, Workforce\_Position |
| Workforce\_WorkerName             | Nombre, apellido y nombre completo                                                                       | |
| Workforce\_WorkerTitle            | Cargo y fecha de antigüedad                                                                                   | |
| Workorce\_WorkerTrend             | Trabajadores a lo largo del tiempo, plantilla, empresa y puesto                                                        | Workforce\_Company, Workforce\_Compensation, Workforce\_GeographicLocation, Workforce\_Performance, Workforce\_WorkerName, Workforce\_ReportsToWorkerName, Workforce\_CalendarOffset, Workforces\_Date, Workforce\_WorkerTitle, Workforce\_Demographics, Workforce\_Employment, Workforce\_Job |
