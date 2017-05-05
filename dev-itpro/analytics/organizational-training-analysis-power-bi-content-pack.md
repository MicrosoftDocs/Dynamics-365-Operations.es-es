---
title: "Contenido de Power BI sobre formación organizativa"
description: "En este tema se describe Dynamics 365 for Operations, contenido de Power BI sobre formación organizativa. Explica cómo obtener acceso al paquete de contenido y describe el modelo de datos y las entidades que se utilizan para generar el paquete de contenido."
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

# <a name="organizational-training-power-bi-content"></a>Contenido de Power BI sobre formación organizativa

[!include[banner](../includes/banner.md)]


En este tema se describe Dynamics 365 for Operations, contenido de Power BI sobre formación organizativa. Explica cómo obtener acceso al paquete de contenido y describe el modelo de datos y las entidades que se utilizan para generar el paquete de contenido.

<a name="accessing-the-content-pack"></a>Acceso al paquete de contenido
--------------------------

El paquete de contenido sobre formación organizativa se encuentra en la biblioteca compartida de los activos en los servicios del ciclo de vida de Microsoft Dynamics (LCS). Para obtener más información sobre cómo descargar el paquete de contenido y conectarlo a los datos de Microsoft Dynamics 365 for Operations, consulte [Contenido de Power BI en LCS en Microsoft y sus socios](power-bi-content-microsoft-partners.md).

## <a name="reports-that-are-included-in-the-content-pack"></a>Informes que se incluyen en el paquete de contenido
Tras la conexión del paquete de contenido con sus datos de Dynamics 365 for Operations, los informes muestran los datos de su organización. Si nunca antes ha utilizado Microsoft Power BI, consulte [Aprendizaje dirigido para Power BI](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData) para obtener más información acerca de la aplicación. Los informes incluidos en el paquete de contenido tienen gráficos y tablas que contienen información adicional. En la siguiente tabla se describen los informes.

| Informe          | Contenido                                                                    |
|-----------------|-----------------------------------------------------------------------------|
| Análisis de curso | Registro por ubicación, asistentes del curso por estado y lista de registro |
| Tipos de cursos    | Tipo de curso por aptitud                                                       |

Puede filtrar los gráficos e iconos en estos informes y anclar los gráficos e iconos al panel de información. Para obtener más información acerca de cómo filtrar y anclar en Power BI, consulte [Crear y configurar un panel de información](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Comprensión del modelo de datos y de las entidades
Los datos de Dynamics 365 for Operations se usan para rellenar los informes del paquete de contenido sobre formación organizativa. En la tabla siguiente se muestran las entidades en las que se basaba el paquete de contenido.

| Entidad                    | Contenido                                                         | Relaciones con otras entidades                                                                                                                                                                  |
|---------------------------|------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Training\_CalendarOffset  | Desplazamientos del calendario para dividir informes                                | Training\_CourseAgenda Training\_CourseAttendees                                                                                                                                                   |
| Training\_Company         | Empresas para filtrar informes por                                   | Training\_CourseAgenda Training\_CourseAttendees                                                                                                                                                   |
| Training\_Course          | Curso, descripción, nombre del instructor, ubicación, sitio y estado | Training\_CourseAgenda Training\_CourseAttendees Training\_CourseSkill                                                                                                                             |
| Training\_CourseAgenda    | Programa, curso, y horas de inicio y finalización                          | Training\_Company Training\_CalendarOffset Training\_Date Training\_Course                                                                                                                         |
| Training\_CourseAttendees | Nombre, estado, trabajo y fecha de registro                         | Training\_Company Training\_CalendarOffset Training\_Date Training\_Demographics Training\_Employment Training\_Course Training\_WorkerName Training\_WorkerTitle Training\_Job Training\_Position |
| Training\_CourseSkill     | Aptitudes, tipo de aptitud y nivel                                     | Training\_Course                                                                                                                                                                                   |
| Training\_Date            | Días, semanas, meses y años                                   | Training\_CourseAgenda Training\_CourseAttendees                                                                                                                                                   |
| Training\_Demographics    | Fecha de nacimiento, género, origen étnico y estado civil         | Training\_CourseAgenda Training\_CourseAttendees                                                                                                                                                   |
| Training\_Employment      | Fecha de inicio, fecha final y fecha de transición                        | Training\_CourseAgenda Training\_CourseAttendees                                                                                                                                                   |
| Training\_Job             | Función tipo y cargo                                        | Training\_CourseAgenda Training\_CourseAttendees                                                                                                                                                   |
| Training\_Position        | Puesto, título y equivalente a jornada completa                  | Training\_CourseAgenda Training\_CourseAttendees                                                                                                                                                   |
| Training\_WorkerName      | Nombre, apellido y nombre completo                             | Training\_CourseAttendees                                                                                                                                                                          |
| Training\_WorkerTitle     | Cargo y fecha de antigüedad                                         | Training\_CourseAttendees                                                                                                                                                                          |

Estas entidades se usaban para crear medidas calculadas en el modelo de datos. Estas medidas calculadas se utilizan para calcular los indicadores de rendimiento clave (KPI) y los informes que se utilizan en el paquete del contenido. Si desea incluir cálculos adicionales en sus informes y en el panel de información, puede descargar y modificar el archivo Training.pbix en LCS. Este archivo es el modelo de datos predeterminado usado para crear el paquete del contenido. Una vez que haya realizado las modificaciones, puede crear un panel de información y paquete de contenido organizativo que contienen la información que ha agregado.

## <a name="additional-resources"></a>Recursos adicionales
Estos son algunos vínculos útiles relacionados con las entidades y la creación de contenido de Power BI:

-   [Entidades de datos](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Creación de paquetes de contenido organizativo](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelado de datos con Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Adición de iconos de Power BI a espacios de trabajo](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)





