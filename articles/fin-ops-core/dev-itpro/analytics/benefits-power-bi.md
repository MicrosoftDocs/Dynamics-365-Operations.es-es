---
title: Contenido de prestaciones de Power BI
description: Este tema describe el contenido en Power BI de Prestaciones.
author: jcart1106
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmBenefitWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 8bbd1e35c0a6efd8feae80cb0010b84bbbf5cd6a
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559926"
---
# <a name="benefits-power-bi-content"></a>Contenido de prestaciones de Power BI

[!include [banner](../includes/banner.md)]

Este tema describe el contenido de **Ventajas** de Microsoft Power BI. Explica cómo obtener acceso a los informes incluidos y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el contenido.

## <a name="accessing-the-power-bi-content"></a>Acceso al contenido de Power BI
El contenido en Power BI de **Prestaciones** se muestra en el espacio de trabajo **Administración de prestaciones** si usa uno de los siguientes productos:

- Microsoft Dynamics 365 Finance
- Microsoft Dynamics 365 Human Resources

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Informes que se incluyen en el contenido de Power BI
Los informes incluidos en el contenido **Prestaciones** de Power BI tienen gráficos y tablas que contienen información adicional. En la siguiente tabla se describen los informes.

| Informe                      | Contenido                                                                                       |
|-----------------------------|------------------------------------------------------------------------------------------------|
| Información general sobre la inscripción en el beneficio | Planes inscritos mayoritarios y minoritarios, inscripción por grupo de empleados y plan de prestación seleccionado |
| Prestaciones del empleado           | Inscripción del empleado por prestación seleccionada                                                        |

Puede filtrar los gráficos e iconos en estos informes y anclar los gráficos e iconos al panel de información. Para obtener más información acerca de cómo filtrar y anclar en Power BI, consulte [Crear y configurar un panel de información](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Comprensión del modelo de datos y de las entidades
Los siguientes datos se usan para rellenar los informes en el contenido en Power BI de **Prestaciones**. Esta tabla muestra las entidades en las que se basaba el contenido.

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