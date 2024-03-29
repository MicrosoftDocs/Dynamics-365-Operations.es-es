---
title: Contenido de formación de Power BI
description: Este artículo describe el contenido en Power BI de formación.
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
ms.openlocfilehash: a7aca9e47ed26dcb4ef7f4b9aee72987e2d8fdd2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273971"
---
# <a name="learning-power-bi-content"></a>Contenido de formación de Power BI

[!include [banner](../includes/banner.md)]

Este artículo describe el contenido en Microsoft Power BI de **formación**.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Informes que se incluyen en el contenido de Power BI

Los informes incluidos en el contenido **Formación** de Power BI tienen gráficos y tablas que contienen información adicional. En la siguiente tabla se describen los informes.

| Informe                | Contenido |
|-----------------------|----------|
| Visión general de Aprendizaje     | Resumen de otros informes |
| Análisis de curso       | Registro por ubicación, participante por estado, cursos por tipo y por empresa y asistencia al curso por trabajo |
| Análisis de registro | Lista de registros |
| Tipos de cursos          | Tipo de curso por aptitud |
| Análisis de instructor   | Coeficiente de cursos para instructores, número de instructores, cursos por instructor, cursos según instructor y programa del curso por instructor |
| Cursos ofrecidos       | Lista de cursos |
| Diseño de cursos        | Programa del curso |

Puede filtrar los gráficos e iconos en estos informes y anclar los gráficos e iconos al panel de información. Para obtener más información acerca de cómo filtrar y anclar en Power BI, consulte [Crear y configurar un panel de información](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Comprensión del modelo de datos y de las entidades

Los siguientes datos se usan para rellenar los informes en el contenido en Power BI de **Formación**. Esta tabla muestra las entidades en las que se basaba el contenido.

| Entidad           | Contenido                                                         | Relaciones con otras entidades |
|------------------|------------------------------------------------------------------|-----------------------------------|
| Contrapartida del calendario  | Desplazamientos del calendario para dividir informes                                | Programa del curso, asistentes al curso |
| Compañía          | Empresas para filtrar informes por                                   | Programa del curso, asistentes al curso |
| Curso           | Curso, descripción, nombre del instructor, ubicación, sitio y estado | Programa del curso, asistentes al curso, aptitudes del curso |
| Programa del curso    | Programa, curso, y horas de inicio y finalización                          | Empresa, contrapartida del calendario, fecha, curso |
| Asistentes al curso | Nombre, estado, trabajo y fecha de registro                         | Empresa, contrapartida del calendario, fecha, curso, demografía, empleo, curso, nombre del empleado, puesto del empleado, trabajo, puesto |
| Aptitud del curso     | Aptitudes, tipo de aptitud y nivel                                     | Curso |
| Fecha             | Días, semanas, meses y años                                   | Programa del curso, asistentes al curso |
| Datos demográficos     | Fecha de nacimiento, género, origen étnico y estado civil         | Programa del curso, asistentes al curso |
| Empleo       | Fecha de inicio, fecha final y fecha de transición                        | Programa del curso, asistentes al curso |
| Trabajo              | Función tipo y cargo                                        | Programa del curso, asistentes al curso |
| Posición         | Puesto, título y equivalente a jornada completa                  | Programa del curso, asistentes al curso |
| Nombre de empleado    | Nombre, apellido y nombre completo                             | Asistentes al curso |
| Puesto del empleado   | Cargo y fecha de antigüedad                                         | Asistentes al curso |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
