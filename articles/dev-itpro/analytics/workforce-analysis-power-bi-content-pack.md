---
title: "Contenido de BI sobre métricas de recursos"
description: "Este tema describe el contenido en Power BI de métricas de recursos. Explica cómo obtener acceso a los informes y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el contenido."
author: jcart1106
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Talent, Core
ms.custom: 264084
ms.assetid: 8e700583-3a7d-4f5f-9ac8-58c4feed1a02
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: cb43245afe578341251b140383a3b03ba2abd962
ms.openlocfilehash: 8ff4eb80eeb47a72fc1ac91ddc4bdfccebc4c0c6
ms.contentlocale: es-es
ms.lasthandoff: 12/19/2017

---

# <a name="workforce-metrics-power-bi-content"></a>Contenido de BI sobre métricas de recursos

[!include[banner](../includes/banner.md)]

Este tema describe el contenido en Microsoft Power BI de **métricas de recursos**. Explica cómo obtener acceso a los informes de Power BI y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el contenido.

## <a name="accessing-the-power-bi-content"></a>Acceso al contenido de Power BI
El contenido en Power BI de **métricas de recursos** se muestra en el espacio de trabajo **Administración de personal** si usa uno de estos productos:

- Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition 
- Microsoft Dynamics 365 for Talent

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Métricas que se incluyen en el contenido de Power BI
En la tabla siguiente se enumeran las métricas que se muestran en cada informe.

| Informe                                           | Métricas                                                                                                                                                                                                            |
|--------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Métrica de las personas                                   | Resumen de otros informes                                                                                                                           |
| Empresa de análisis de recuento de personas, Departamento, Ubicación | Recuento de personas por empresa, recuento de personas por departamento, recuento de personas por ubicación y recuento de personas totales                                                                                                                           |
| Trabajo de análisis de recuento de personas, Paso, Administrador            | Recuento de personas por trabajo, recuento de personas por paso, recuento de personas por administrador y recuento de personas totales                                                                                                                                      |
| Análisis de tendencia del recuento de personas                         | Recuento de personas de este año con relación al año anterior por empresa y recuento de personas acumulado para los últimos 12 meses                                                                                                                        |
| Análisis de FTE                                     | Equivalente a jornada completa (FTE), FTE asignado total, FTE por departamento, FTE de los últimos 12 meses y FTE por trabajo |
| Datos demográficos de recursos                           | Recuento de personas por edad y género, recuento de personas por origen étnico, recuento de personas por estado de excombatiente, recuento de personas por estado civil, número de estudiantes a jornada completa, duración media, edad media, proporción entre mujeres y hombres e idiomas hablados por los empleados |
| Análisis de puestos                                | Vacantes por departamento, puestos vacantes a ocupados, puestos activos a inactivos y puestos por departamento                                                                                                   |
| Análisis de abandono                               | Abandono de este año frente al año pasado, abandono, empleados que salen por antigüedad y género, tiempo medio en la empresa de los empleados que se van, empleados que salen este mes y empleados que se van por un motivo                                                                   |
| Personas por departamento                             | Empleados con un número de personal por departamento, puesto y fechas inicial y final de asignación                                                                                                                       |
| Análisis de antigüedad                               | Promedio de tiempo en la empresa, promedio de años de servicio por empresa y lista de antigüedad                                                                                                                                                              |
| Aniversarios del empleado                           | Aniversarios este mes, aniversarios el siguiente mes, empleados por años de servicio, y aniversarios, años de servicio por departamento                                                                                                                                                                    |
| Cumpleaños del empleado                               | Cumpleaños este mes, el cumpleaños siguiente mes, cumpleaños de los empleados, y cumpleaños por mes y departamento                                                                                                                                                                    |
| Proyectos de contratación masiva                               | Proyectos de contratación masiva totales, proyectos de contratación masiva por estado, proyectos de contratación masiva por departamento y propietario, proyectos de contratación masiva por trabajo, y proyectos de contratación masiva                                                                                                                                                                    |

Puede filtrar los gráficos e iconos en estos informes y anclar los gráficos e iconos al panel de información. Para obtener más información acerca de cómo filtrar y anclar en Power BI, consulte [Crear y configurar un panel de información](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

Asegúrese de descargar el contenido en Power BI de **métricas de recursos** que se aplica a la versión de Microsoft Dynamics 365 que esté usando.

>[!NOTE]
>Los archivos .pbix disponibles en Lifecycle Services se aplican solamente a Finance and Operations.

## <a name="understanding-the-data-model-and-entities"></a>Comprensión del modelo de datos y de las entidades
En la tabla siguiente se muestran las entidades en las que se basaba el contenido.

| Entidad                   | Contenido                                                                            | Relaciones con otras entidades |
|--------------------------|-------------------------------------------------------------------------------------|-----------------------------------|
| Contrapartida del calendario          | Desplazamientos del calendario para dividir informes                                                   | Asignación de puesto anterior, tenencia de puestos, tendencia de empleado, empleado cesado |
| Compañía                  | Empresas para filtrar informes por                                                      | Empleado actual, empleado cesado, tendencia del empleado |
| Puesto actual         | Puestos a fecha actual, FTE, vacantes y puestos vacantes a ocupados | Trabajo, puesto |
| Empleado actual         | Trabajadores a partir de la fecha actual, edad y plantilla                                  | Empresa, ubicación geográfica, nombre del empleado, responsable ante, cargo del empleado, demografía, trabajo, empleo, puesto |
| Fecha                     | Días, semanas, meses y años                                                      | Asignación de puesto anterior, tenencia de puestos, tendencia de empleado, tendencia de empleado |
| Datos demográficos             | Fecha de nacimiento, género, origen étnico y estado civil                            | Empleado actual, empleado cesado, tendencia del empleado |
| Empleo               | Fecha de inicio, fecha final y fecha de transición                                           | Empleado actual, empleado cesado, tendencia del empleado |
| Ubicación geográfica      | Ciudad, provincia, código postal y comunidad autónoma                                    | Empleado actual, empleado cesado, tendencia del empleado |
| Trabajo                      | Función tipo y cargo                                                           | Puesto actual, empleado actual |
| Asignación de puestos anteriores | Motivo de la asignación, fecha de inicio, fecha final y trabajo                                    | Contrapartida del calendario, fecha, trabajo, puesto |
| Posición                 | Departamento, FTE, puesto, tipo de puesto y cargo                                 | Puesto actual, empleado actual |
| Tendencia de puestos           | Puestos a lo largo del tiempo, FTE y trabajo                                                   | Contrapartida del calendario, fecha, trabajo, puesto |
| Es responsable ante               | Nombre, apellido y nombre completo                                                | Empleado actual, empleado cesado, tendencia del empleado |
| Empleado cesado      | Trabajadores terminados, fecha de finalización, cargo, puesto y trabajo                      | Empresa, ubicación geográfica, nombre del empleado, responsable ante, contrapartida del calendario, fecha, puesto del empleado, demografía, empleo, trabajo, puesto |
| Nombre de empleado            | Nombre, apellido y nombre completo                                                | Trabajador actual, empleado cesado, tendencia del empleado |
| Puesto del empleado           | Cargo y fecha de antigüedad                                                            | Empleado actual, empleado cesado, tendencia del empleado |
| Tendencia del empleado           | Trabajadores a lo largo del tiempo, plantilla, empresa y puesto                                 | Empresa, ubicación geográfica, nombre del empleado, responsable ante, contrapartida del calendario, fecha, puesto del empleado, demografía, empleo, trabajo |
| Proyecto de contratación masiva        | Número de proyectos de contratación masiva, propietario del proyecto, y estado de proyecto                     | Empresa, línea de contratación masiva |
| Línea de contratación masiva           | Departamento, tipo de empleo y puesto                                           | Fecha, trabajo, proyecto de contratación masiva |



