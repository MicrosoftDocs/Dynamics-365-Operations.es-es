---
title: "Contenido de organización de Power BI de formación"
description: "Este tema describe Dynamics 365 para las operaciones (contenido de organización de Power BI de formación. Explica cómo obtener acceso al paquete de contenido, y describe el modelo de datos y las entidades que se utilizaron para compilar el paquete del contenido."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations
ms.custom: 263874
ms.assetid: 45dbba14-aba6-4571-be0d-5d1aba3515d9
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 104164f8ffd0d2bc3a64bf15d2fb5213234046ce
ms.lasthandoff: 03/31/2017


---

# <a name="organizational-training-power-bi-content"></a>Contenido de organización de Power BI de formación

Este tema describe Dynamics 365 para las operaciones (contenido de organización de Power BI de formación. Explica cómo obtener acceso al paquete de contenido, y describe el modelo de datos y las entidades que se utilizaron para compilar el paquete del contenido.

<a name="accessing-the-content-pack"></a>Acceso al paquete de contenido
--------------------------

Puede encontrar el paquete de organización de contenido de formación en la biblioteca compartida de los activos en los servicios (LCS) del ciclo de vida de Microsoft Dynamics. Para obtener más información sobre cómo descargar el paquete de contenido y conectarlo a su Microsoft Dynamics 365 para los datos de las operaciones, consulte [contenido de Power BI en el CD de Microsoft y sus socios power-bi-content-microsoft-partners.md] ().

## <a name="reports-that-are-included-in-the-content-pack"></a>Informa que se incluye en el paquete de contenido
Después del paquete en línea de contenido con su Dynamics 365 para los datos de las operaciones, los informes muestran los datos de la organización. Si nunca se ha utilizado el BI de la potencia de Microsoft antes, puede obtener más información acerca de ella en [dirigido aprendiendo la página para el BI] de la potencia (https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). Los informes incluidos en el paquete de contenido ambos tienen gráficos y tablas que contienen información adicional. En la siguiente tabla se describen los informes.

| Informe          | Contenido                                                                    |
|-----------------|-----------------------------------------------------------------------------|
| Análisis de curso | Registro por ubicación, los asistentes del curso de estado, y la lista de registro |
| Tipos de curso    | Tipo de curso por aptitud                                                       |

Puede filtrar los gráficos y los mosaicos en estos informes, y ancla los gráficos y los mosaicos al panel. Para obtener más información sobre cómo filtrar y anclar en BI de la potencia [ver, crear y configurar un panel] (https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Comprensión del modelo de datos y de las entidades
La Dynamics 365 para los datos de las operaciones se usa para rellenar los informes en el paquete de organización de contenido de formación. En la tabla siguiente se muestran las partes que el paquete de contenido se basa.

| Entidad                    | Contenido                                                         | Relaciones con otras entidades                                                                                                                                                                  |
|---------------------------|------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Entrenamiento\_CalendarOffset  | Desplazamientos del calendario a informes del segmento                                | Entrenamiento\_que CourseAgenda usuarios\_CourseAttendees                                                                                                                                                   |
| Empresa\_de formación         | Empresas para filtrar por informes                                   | Entrenamiento\_que CourseAgenda usuarios\_CourseAttendees                                                                                                                                                   |
| Curso\_de formación          | Curso, descripción, nombre del instructor, ubicación, sitio, y estado | Entrenamiento\_que CourseAgenda usuarios\_CourseAttendees que usuarios\_CourseSkill                                                                                                                             |
| Entrenamiento\_CourseAgenda    | Programa curso, y las horas de inicio y finalización                          | Empresa\_de formación que usuarios\_CalendarOffset que usuarios a la fecha\_que usuarios al curso\_                                                                                                                         |
| Entrenamiento\_CourseAttendees | Nombre, estado, trabajo, y fecha de registro                         | Empresa\_de formación que usuarios\_CalendarOffset que usuarios a la fecha\_que el Demographics usuarios\_que usuarios al empleo\_que usuarios al curso\_usuarios que\_\_WorkerName que usuarios\_WorkerTitle que usuarios al puesto\_de la formación laboral\_ |
| Entrenamiento\_CourseSkill     | Conocimiento, tipo de aptitud, y nivel                                     | Curso\_de formación                                                                                                                                                                                   |
| Fecha\_de formación            | Días, semanas, meses, años y                                   | Entrenamiento\_que CourseAgenda usuarios\_CourseAttendees                                                                                                                                                   |
| Demographics\_de formación    | Fecha de nacimiento, el género, el origen étnico, y el estado civil         | Entrenamiento\_que CourseAgenda usuarios\_CourseAttendees                                                                                                                                                   |
| Empleo\_de formación      | Fecha inicial, Fecha final, y fecha de la transición                        | Entrenamiento\_que CourseAgenda usuarios\_CourseAttendees                                                                                                                                                   |
| Trabajo\_de formación             | Función tipo, y se incluirán                                        | Entrenamiento\_que CourseAgenda usuarios\_CourseAttendees                                                                                                                                                   |
| Posición\_de formación        | Colocar, titulan (FTE), y equivalente a jornada completa                  | Entrenamiento\_que CourseAgenda usuarios\_CourseAttendees                                                                                                                                                   |
| Entrenamiento\_WorkerName      | Nombre, apellido, y nombre completo                             | Entrenamiento\_CourseAttendees                                                                                                                                                                          |
| Entrenamiento\_WorkerTitle     | Título y la fecha de antigüedad                                         | Entrenamiento\_CourseAttendees                                                                                                                                                                          |

Usaban a estas entidades para crear medidas calculadas en el modelo de datos. Estas medidas calculadas se utilizan para calcular los indicadores clave de rendimiento (KPIs) y los informes que se utilizan en el paquete del contenido. Si desea incluir cálculos adicionales sobre sus informes y panel, puede descargar y modificar el archivo de Training.pbix del CD. Este archivo es el modelo de datos predeterminados usado para crear el paquete del contenido. Una vez que haya creado modificaciones, puede crear un paquete y un panel contentos de organización que contienen información que ha agregado.

## <a name="additional-resources"></a>Recursos adicionales
Estos son algunos vínculos útiles relacionados con las entidades y la creación de contenido de Power BI:

-   [Entidades de datos](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Creación de paquetes de contenido organizativo](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelado de datos con Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Adición de iconos de Power BI a espacios de trabajo](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)



