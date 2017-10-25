---
title: Contenido en Power BI de Desarrollo de empleados
description: "Este tema describe el contenido en Power BI de Desarrollo de empleados. Explica cómo obtener acceso a los informes y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el contenido."
author: jcart1106
manager: AnnBe
ms.date: 05/24/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, UnifiedOperations, Talent, Core
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 91f7071cc759686dd90b5893adaf58d1521e9185
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="employee-development-power-bi-content"></a>Contenido en Power BI de Desarrollo de empleados

[!include[banner](../includes/banner.md)]

Este tema describe el contenido en Microsoft Power BI de **Desarrollo de empleados**. Explica cómo obtener acceso a los informes y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el contenido.

## <a name="accessing-the-power-bi-content"></a>Acceso al contenido de Power BI

Si está usando Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (julio de 2017), puede encontrar el paquete de contenido **Desarrollo de empleados** en la biblioteca de activos compartidos en Microsoft Dynamics Lifecycle Services (LCS). Para obtener información sobre cómo descargar el paquete de contenido y conectarlo a sus datos, consulte [Contenido de Power BI en LCS en Microsoft y sus socios](power-bi-content-microsoft-partners.md).

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Informes que se incluyen en el contenido de Power BI
Los informes incluidos en el contenido de Power BI de **Desarrollo de empleados** tienen gráficos y tablas que contienen información adicional. En la siguiente tabla se describen los informes.

| Informe                        | Contenido |
|-------------------------------|----------|
| Visión general de Desarrollo de empleados | Resumen de otros informes |
| Análisis de aptitudes de empleados       | Tipos de aptitudes de empleados y aptitudes de empleados por tipo |
| Análisis de nivel de aptitud de empleados | Niveles de aptitud de empleado por departamento, empleados por nivel de aptitud y tipo de aptitud y niveles superiores e inferiores por aptitud |
| Perfil de aptitudes                 | Perfil de aptitudes para el empleado seleccionado |
| Análisis de aptitudes                | Aptitudes por tipo y clasificación |
| Análisis de la evaluación del desempeño   | Empleados por evaluación más alta y más bajo por trabajo, evaluaciones de empleado por departamento, empleados por evaluación y tipo de posición y evaluaciones más altas y más bajas por puesto  |
| Análisis del desempeño de empleados | Evaluaciones de empleados para evaluación seleccionada por director |

Puede filtrar los gráficos e iconos en estos informes y anclar los gráficos e iconos al panel de información. Para obtener más información acerca de cómo filtrar y anclar en Power BI, consulte [Crear y configurar un panel de información](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Comprensión del modelo de datos y de las entidades
| Entidad                   | Contenido                                                                                                   | Relaciones con otras entidades |
|--------------------------|------------------------------------------------------------------------------------------------------------|-----------------------------------|
| Contrapartida del calendario          | Desplazamientos del calendario para dividir informes                                                                          | Asignación de puesto anterior, tenencia de puestos, tendencia de empleado, empleado cesado 
| Compañía                  | Empresas para filtrar informes por                                                                             | Empleado actual, empleado cesado, tendencia del empleado |
| Puesto actual         | Puestos a partir de la fecha actual, equivalentes a tiempo completo (FTE), vacantes y puestos vacantes a ocupados | Trabajo, puesto |
| Empleado actual         | Trabajadores a partir de la fecha actual, edad y plantilla                                                         | Empresa, ubicación geográfica, nombre del empleado, responsable ante, cargo del empleado, demografía, trabajo, empleo, puesto |
| Fecha                     | Días, semanas, meses y años                                                                             | Asignación de puesto anterior, tenencia de puestos, tendencia de empleado, tendencia de empleado |
| Datos demográficos             | Fecha de nacimiento, género, origen étnico y estado civil                                                   | Empleado actual, cesado, empleado, tendencia del empleado |
| Empleo               | Fecha de inicio, fecha final y fecha de transición                                                                  | Empleado actual, empleado cesado, tendencia del empleado |
| Ubicación geográfica      | Ciudad, provincia, código postal y comunidad autónoma                                                           | Empleado actual, empleado cesado, tendencia del empleado |
| Trabajo                      | Función tipo y cargo                                                                                  | Puesto actual, empleado actual |
| Asignación de puestos anteriores | Motivo de la asignación, fecha de inicio, fecha final y trabajo                                                           | Contrapartida del calendario, fecha, trabajo, puesto |
| Posición                 | Departamento, FTE, puesto, tipo de puesto y cargo                                                        | Puesto actual, empleado actual |
| Tendencia de puestos           | Puestos a lo largo del tiempo, FTE y trabajo                                                                          | Contrapartida del calendario, fecha, trabajo, puesto |
| Es responsable ante               | Nombre, apellido y nombre completo                                                                       | Empleado actual, empleado cesado, tendencia del empleado |
| Empleado cesado      | Trabajadores terminados, fecha de finalización, cargo, puesto y trabajo                                             | Empresa, ubicación geográfica, nombre del empleado, responsable ante, contrapartida del calendario, fecha, puesto del empleado, demografía, empleo, trabajo, puesto |
| Nombre de empleado            | Nombre, apellido y nombre completo                                                                       | Trabajador actual, empleado cesado, tendencia del empleado |
| Puesto del empleado           | Cargo y fecha de antigüedad                                                                                   | Empleado actual, empleado cesado, tendencia del empleado |
| Tendencia del empleado           | Trabajadores a lo largo del tiempo, plantilla, empresa y puesto                                                        | Empresa, ubicación geográfica, nombre del empleado, responsable ante, contrapartida del calendario, fecha, puesto del empleado, demografía, empleo, trabajo |
| Trabajo                      | Función tipo y cargo                                                                                      | Empleado actual, puesto actual, tendencia del empleado, aptitud preferida del trabajo, asignación de puesto anterior, tendencia del puesto, empleado cesado |
| Aptitud preferida de trabajo      | Importancia, clasificación, aptitud y nivel de aptitud                                                                 | Trabajo |
| Análisis de aptitudes de empleados  | Certificación, nivel, fecha de nivel y aptitud                                                                    | Nombre del empleado, aptitud |  
| Rendimiento              | Calificación, descripción y modelo de calificación                                                                      | Empleado actual, puesto actual, tendencia del empleado, aptitud preferida del trabajo, asignación de puesto anterior, tendencia del puesto, empleado cesado |
|  Aptitud                   | Aptitudes, tipo de aptitud y calificación                                                                              | Análisis de aptitudes de empleados, aptitud preferida del trabajo |                                                                                                                        

Estas entidades se usaban para crear medidas calculadas en el modelo de datos. Estas medidas calculadas se utilizan para calcular los indicadores de rendimiento clave (KPI) y los informes que se utilizan en el contenido de Power BI. Si desea incluir cálculos adicionales en sus informes y en el panel de información, puede descargar y modificar el archivo .pbix en LCS. Este archivo es el modelo de datos predeterminado usado para crear el contenido de Power BI. Una vez que haya realizado las modificaciones, puede crear un panel de información y paquete de contenido organizativo que contienen la información que ha agregado.
