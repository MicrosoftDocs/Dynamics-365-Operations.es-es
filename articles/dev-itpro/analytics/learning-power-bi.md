---
title: "Contenido en Power BI de Aprendizaje"
description: Este tema describe el contenido de Power BI de Aprendizaje.
author: jcart1106
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 0ee0cc2e22609d1a87e7d2b6dcd031606191f879
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---

# <a name="learning-power-bi-content"></a>Contenido en Power BI de Aprendizaje

[!include [banner](../includes/banner.md)]

Este tema describe el contenido en Microsoft Power BI de **Aprendizaje**.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Informes que se incluyen en el contenido de Power BI

Los informes incluidos en el contenido en Power BI de **Aprendizaje** tienen gráficos y tablas que contienen información adicional. En la siguiente tabla se describen los informes.

| Informe                | Contenido |
|-----------------------|----------|
| Visión general de Aprendizaje     | Resumen de otros informes |
| Análisis de curso       | Registro por ubicación, participante por estado, cursos por tipo y por empresa y asistencia al curso por trabajo |
| Análisis de registro | Lista de registros |
| Tipos de cursos          | Tipo de curso por aptitud |
| Análisis de instructor   | Coeficiente de cursos para instructores, número de instructores, cursos por instructor, cursos según instructor y programa del curso por instructor |
| Cursos ofrecidos       | Lista de cursos |
| Diseño de cursos        | Programa del curso |

Puede filtrar los gráficos e iconos en estos informes y anclar los gráficos e iconos al panel de información. Para obtener más información acerca de cómo filtrar y anclar en Power BI, consulte [Crear y configurar un panel de información](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Comprensión del modelo de datos y de las entidades

Los siguientes datos se usan para rellenar los informes en el contenido de Power BI de **Aprendizaje**. Esta tabla muestra las entidades en las que se basaba el contenido.

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

