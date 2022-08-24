---
title: Contenido de compensación de Power BI
description: Este artículo describe el contenido de Compensación de Power BI. Explica cómo acceder a los informes y proporciona información sobre el modelo de datos utilizado.
author: jcart1106
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.search.form: HcmCompensationWorkspace
ms.openlocfilehash: 58d78dede753d8ed81a0e815b9ea02c69b70121f
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291840"
---
# <a name="compensation-power-bi-content"></a>Contenido de compensación de Power BI

[!include [banner](../includes/banner.md)]

Este artículo describe el contenido de **Compensación** de Microsoft Power BI. Explica cómo obtener acceso a los informes y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el contenido.

## <a name="accessing-the-power-bi-content"></a>Acceso al contenido de Power BI
El contenido de Power BI de **Compensación** se muestra en el espacio de trabajo **Administración de compensaciones** si usa uno de los siguientes productos:

- Aplicaciones de finanzas y operaciones
- Microsoft Dynamics 365 Human Resources

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Informes que se incluyen en el contenido de Power BI
Los informes incluidos en el contenido **Compensación** de Power BI tienen gráficos y tablas que contienen información adicional. En la siguiente tabla se describen los informes.

| Informe                     | Contenido |
|----------------------------|----------|
| Información general sobre compensaciones      | Resumen de otros informes |
| Análisis de compensaciones      | Empleados pagados por hora y con sueldo de la empresa, empleados totales por plan de compensación, empleados de sexo masculino y femenino por el plan de compensación y compensación del empleado por departamento |
| Análisis de pago por puesto      | Remuneración más alta y más baja por hora y por salario, puestos con remuneración más alta y más baja y puestos a jornada completa y media jornada |
| Análisis del plan de compensaciones | Inscripción del empleado por prestación seleccionada |

Puede filtrar los gráficos e iconos en estos informes y anclar los gráficos e iconos al panel de información. Para obtener más información acerca de cómo filtrar y anclar en Power BI, consulte [Crear y configurar un panel de información](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Comprensión del modelo de datos y de las entidades
Los siguientes datos se usan para rellenar los informes en el contenido en Power BI de **Compensación**. Esta tabla muestra las entidades en las que se basaba el contenido.

| Entidad                   | Contenido                                                                                                   | Relaciones con otras entidades |
|--------------------------|------------------------------------------------------------------------------------------------------------|-----------------------------------|
| Contrapartida del calendario          | Desplazamientos del calendario para dividir informes                                                                          | Asignación de puesto anterior, tenencia de puestos, tendencia de empleado, empleado cesado |
| Compañía                  | Empresas para filtrar informes por                                                                             | Compensación actual, empleado actual, empleado cesado, tendencia del empleado |
| Compensación             | Índice salaria y frecuencia a lo largo del tiempo                                                                           | Compensación actual, empleado actual, empleado cesado, tendencia del empleado |
| Compensación actual     | Índice salarial y frecuencia a partir de la fecha actual                                                              | Empresa, compensación, demográfico, trabajo, puesto |
| Puesto actual         | Puestos a partir de la fecha actual, equivalentes a tiempo completo (FTE), vacantes y puestos vacantes a ocupados | Trabajo, puesto |
| Empleado actual         | Trabajadores a partir de la fecha actual, edad y plantilla                                                         | Empresa, compensación, ubicación geográfica, nombre del empleado, responsable ante, cargo del empleado, demografía, trabajo, empleo, puesto, prestaciones |
| Fecha                     | Días, semanas, meses y años                                                                             | Asignación de puesto anterior, tenencia de puestos, tendencia de empleado, tendencia de empleado |
| Datos demográficos             | Fecha de nacimiento, género, origen étnico y estado civil                                                   | Empleado actual, empleado cesado, tendencia del empleado |
| Empleo               | Fecha de inicio, fecha final y fecha de transición                                                                  | Empleado actual, empleado cesado, tendencia del empleado |
| Ubicación geográfica      | Ciudad, provincia, código postal y comunidad autónoma                                                           | Empleado actual, empleado cesado, tendencia del empleado |
| Trabajo                      | Función tipo y cargo                                                                                  | Puesto actual, empleado actual |
| Asignación de puestos anteriores | Motivo de la asignación, fecha de inicio, fecha final y trabajo                                                           | Contrapartida del calendario, fecha, trabajo, puesto |
| Posición                 | Departamento, FTE, puesto, tipo de puesto y cargo                                                        | Puesto actual, empleado actual |
| Tendencia de puestos           | Puestos a lo largo del tiempo, FTE y trabajo                                                                          | Contrapartida del calendario, fecha, trabajo, puesto |
| Es responsable ante               | Nombre, apellido y nombre completo                                                                       | Trabajador actual, empleado cesado, tendencia del empleado |
| Empleado cesado      | Empleados cesados, fecha de cese, cargo, puesto y trabajo                                           | Empresa, compensación, ubicación geográfica, nombre del empleado, responsable ante, contrapartida del calendario, fecha, puesto del empleado, demografía, trabajo, trabajo, puesto, prestaciones |
| Beneficios                 | Fecha de vigencia, opción de prestación, plan de prestaciones y tipo de prestación                                             | Nombre del trabajador, empleado cesado, tendencia del empleado |
| Nombre de empleado            | Nombre, apellido y nombre completo                                                                       | Empleado actual, empleado cesado, tendencia del empleado |
| Puesto del empleado           | Cargo y fecha de antigüedad                                                                                   | Empleado actual, empleado cesado, tendencia del empleado |
| Tendencia del empleado           | Trabajadores a lo largo del tiempo, plantilla, empresa y puesto                                                        | Empresa, compensación, ubicación geográfica, nombre del empleado, responsable ante, contrapartida del calendario, fecha, puesto del empleado, demografía, empleo, trabajo, prestaciones |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
