---
title: "Contenido de Power BI para contratación"
description: "En este tema se describe Dynamics 365 for Operations, contenido de Power BI para contratación. Explica cómo tener acceso a los informes que se incluyen en el paquete de contenido, y proporciona información acerca del modelo de datos y las entidades que se utilizaron para generar el paquete del contenido."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations
ms.custom: 263934
ms.assetid: 38e6827b-0819-473c-bc47-821a1ec482b8
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: d307733193b388149f83dd420cc7003edcf7749a
ms.lasthandoff: 03/31/2017


---

# <a name="recruiting-power-bi-content"></a>Contenido de Power BI para contratación

[!include[banner](../includes/banner.md)]


En este tema se describe Dynamics 365 for Operations, contenido de Power BI para contratación. Explica cómo tener acceso a los informes que se incluyen en el paquete de contenido, y proporciona información acerca del modelo de datos y las entidades que se utilizaron para generar el paquete del contenido.

<a name="accessing-the-content-pack"></a>Acceso al paquete de contenido
--------------------------

El paquete de contenido Contratación se encuentra en la biblioteca de activos compartidos de los Servicios de ciclo de vida (LCS) de Microsoft Dynamics. Para obtener más información sobre cómo descargar el paquete de contenido y conectarlo a los datos de Microsoft Dynamics 365 for Operations, consulte [Contenido de Power BI en LCS en Microsoft y sus socios](power-bi-content-microsoft-partners.md).

## <a name="reports-that-are-included-in-the-content-pack"></a>Informes que se incluyen en el paquete de contenido
Tras la conexión del paquete de contenido con sus datos de Dynamics 365 for Operations, los informes muestran los datos de su organización. Si nunca antes ha utilizado Microsoft Power BI, consulte [Aprendizaje dirigido para Power BI](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData) para obtener más información acerca de la aplicación. Los informes incluidos en el paquete de contenido tienen gráficos y tablas que contienen información adicional. En la siguiente tabla se describen los informes.

| Informe                       | Contenido                                                                                               |
|------------------------------|--------------------------------------------------------------------------------------------------------|
| Análisis del candidato           | Candidatos por trabajo, orígenes de los candidatos, candidatos por ubicación y número total de candidatos           |
| Estado del candidato             | Candidatos por tipo y estado y estado del candidato                                                    |
| Datos demográficos del candidato       | Candidatos por edad y género, y candidatos y por nivel de formación y estado                             |
| Análisis de la contratación          | Proporción neta de contratación, promedio de días para contratar, porcentaje de contrataciones fallidas y costes de contratación                    |
| Análisis del proyecto de contratación | Número de proyectos de contratación, vacantes por proyecto de contratación y candidatos por proyecto de contratación |

Puede filtrar los gráficos e iconos en estos informes y anclar los gráficos e iconos al panel de información. Para obtener más información acerca de cómo filtrar y anclar en Power BI, consulte [Crear y configurar un panel de información](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Comprensión del modelo de datos y de las entidades
Se usan los datos de Dynamics 365 for Operations para rellenar los informes del paquete de contenido Contratación. En la tabla siguiente se muestran las entidades en las que se basaba el paquete de contenido.

| Entidad                          | Contenido                                                         | Relaciones con otras entidades                                                                                                                                                                                                                 |
|---------------------------------|------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Recruiting\_Applicant           | Candidatos, candidatos contratados, proporción neta de contratación y costes          | Recruiting\_ApplicantName Recruiting\_Company Recruiting\_CalendarOffset Recuriting\_Date Recruiting\_GeographicLocation Recruiting\_Demographics Recruiting\_Job Recruiting\_Media Recruiting\_RecruitmentProject                                |
| Recruiting\_ApplicantName       | Nombre, apellido y nombre completo del candidato                   | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_CalendarOffset      | Desplazamientos del calendario para dividir informes                                | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_Company             | Empresas para filtrar informes por                                   | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_Date                | Días, semanas, meses y años                                   | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_Demographics        | Fecha de nacimiento, género, origen étnico y estado civil         | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_EmployedApplicant   | Candidato, rendimiento, fecha inicial y tipo del candidato           | Recruiting\_Company Recruiting\_CalendarOffset Recruiting\_Date Recruiting\_GeographicLocation Recruiting\_ApplicantName Recruiting\_Employment Recruiting\_Performance Recruiting\_Job Recruiting\_Media Recruiting\_RecruitmentProject          |
| Recruiting\_Employment          | Fecha de inicio, fecha final y fecha de transición                        | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_GeographicLocation  | Ciudad, provincia, código postal y comunidad autónoma                 | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_Job                 | Función tipo y cargo                                        | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_Media               | Origen de los candidatos                                             | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_Performance         | Calificación, descripción y modelo de calificación                            | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_RecruitmentProject  | Descripción del proyecto, estado del proyecto y vacantes                | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_TerminatedApplicant | Candidatos cesados, motivo, rendimiento y fecha de cese | Recruiting\_Company Recruiting\_CalendarOffset Recruiting\_Date Recruiting\_GeographicLocation Recruiting\_Performance Recruiting\_Demographics Recruiting\_Employment Recruiting\_Media Recruiting\_RecruitmentProject Recruiting\_ApplicantName |

Estas entidades se usaban para crear medidas calculadas. Estas medidas calculadas se utilizan para calcular los indicadores de rendimiento clave (KPI) y los informes que se utilizan en el paquete del contenido. Si desea incluir cálculos adicionales en sus informes y en el panel de información, puede descargar y modificar el archivo Recruiting.pbix en LCS. Este archivo es el modelo de datos predeterminado usado para crear el paquete del contenido. Una vez que haya realizado las modificaciones, puede crear un panel de información y paquete de contenido organizativo que contienen la información que ha agregado.

## <a name="additional-resources"></a>Recursos adicionales
Estos son algunos vínculos útiles relacionados con las entidades y la creación de contenido de Power BI:

-   [Entidades de datos](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Creación de paquetes de contenido organizativo](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelado de datos con Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Adición de iconos de Power BI a espacios de trabajo](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)





