---
title: "Contenido de contratación de Power BI"
description: "Este tema describe Dynamics 365 para las operaciones (contenido de contratación de Power BI. Explica de cómo obtener acceso a los informes que se incluyen en el paquete de contenido, y proporciona información acerca del modelo de datos y las entidades que se utilizaron para compilar el paquete del contenido."
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

# <a name="recruiting-power-bi-content"></a>Contenido de contratación de Power BI

Este tema describe Dynamics 365 para las operaciones (contenido de contratación de Power BI. Explica de cómo obtener acceso a los informes que se incluyen en el paquete de contenido, y proporciona información acerca del modelo de datos y las entidades que se utilizaron para compilar el paquete del contenido.

<a name="accessing-the-content-pack"></a>Acceso al paquete de contenido
--------------------------

Puede encontrar el paquete de contenido contratación de la biblioteca compartida de los activos en los servicios (LCS) del ciclo de vida de Microsoft Dynamics. Para obtener más información sobre cómo descargar el paquete de contenido y conectarlo a su Microsoft Dynamics 365 para los datos de las operaciones, consulte [contenido de Power BI en el CD de Microsoft y sus socios power-bi-content-microsoft-partners.md] ().

## <a name="reports-that-are-included-in-the-content-pack"></a>Informa que se incluye en el paquete de contenido
Después del paquete en línea de contenido con su Dynamics 365 para los datos de las operaciones, los informes muestran los datos de la organización. Si nunca se ha utilizado el BI de la potencia de Microsoft antes, puede obtener más información acerca de ella en [dirigido aprendiendo la página para el BI] de la potencia (https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). Los informes incluidos en el paquete de contenido ambos tienen gráficos y tablas que contienen información adicional. En la siguiente tabla se describen los informes.

| Informe                       | Contenido                                                                                               |
|------------------------------|--------------------------------------------------------------------------------------------------------|
| Análisis del candidato           | Candidatos de trabajo, de orígenes del candidato, de los candidatos por ubicación, y el número total de candidatos           |
| Estado del candidato             | Candidatos del tipo y estado, y el estado del candidato                                                    |
| Demographics del candidato       | Candidatos por antigüedad y género, candidatos y por el nivel de formación y estado                             |
| Análisis de contratación          | Relación de transformación neto de contratación, días medios a contratar, el porcentaje de alquileres incorrectas, y los costes de contratación                    |
| Análisis del proyecto de contratación | Número de proyectos de contratación, de aperturas por proyecto de contratación, y candidatos por proyecto de contratación |

Puede filtrar los gráficos y los mosaicos en estos informes, y ancla los gráficos y los mosaicos al panel. Para obtener más información sobre cómo filtrar y anclar en BI de la potencia [ver, crear y configurar un panel] (https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Comprensión del modelo de datos y de las entidades
La Dynamics 365 para los datos de las operaciones se usa para rellenar los informes en el paquete de responsables de contratación. En la tabla siguiente se muestran las partes que el paquete de contenido se basa.

| Entidad                          | Contenido                                                         | Relaciones con otras entidades                                                                                                                                                                                                                 |
|---------------------------------|------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Candidato de contratación\_           | Candidatos contratados, candidatos, coeficiente de alquiler de la red, y costes          | \_ApplicantName contratación de trabajadores que la empresa\_que los CalendarOffset\_Recuriting\_\_fecha de contratación GeographicLocation que el Demographics los sitios\_que los el trabajo\_que los medios\_\_RecruitmentProject de contratación                                |
| \_ApplicantName de contratación       | Nombre, apellido, y nombre completo del candidato                   | Candidato de contratación\_trabajadores que\_\_EmployedApplicant que los TerminatedApplicant\_                                                                                                                                                               |
| \_CalendarOffset de contratación      | Desplazamientos del calendario a informes del segmento                                | Candidato de contratación\_trabajadores que\_\_EmployedApplicant que los TerminatedApplicant\_                                                                                                                                                               |
| Empresa de contratación\_             | Empresas para filtrar por informes                                   | Candidato de contratación\_trabajadores que\_\_EmployedApplicant que los TerminatedApplicant\_                                                                                                                                                               |
| Fecha de contratación\_                | Días, semanas, meses, años y                                   | Candidato de contratación\_trabajadores que\_\_EmployedApplicant que los TerminatedApplicant\_                                                                                                                                                               |
| Demographics de contratación\_        | Fecha de nacimiento, el género, el origen étnico, y el estado civil         | Candidato de contratación\_trabajadores que\_\_EmployedApplicant que los TerminatedApplicant\_                                                                                                                                                               |
| \_EmployedApplicant de contratación   | Candidato, rendimiento, Fecha inicial, y tipo del candidato           | Empresa de contratación\_trabajadores que\_\_CalendarOffset los que la fecha\_que los GeographicLocation\_\_que los trabajadores que ApplicantName el empleo\_que los el rendimiento\_que los el trabajo\_que los medios\_\_RecruitmentProject de contratación          |
| Empleo de contratación\_          | Fecha inicial, Fecha final, y fecha de la transición                        | Candidato de contratación\_trabajadores que\_\_EmployedApplicant que los TerminatedApplicant\_                                                                                                                                                               |
| \_GeographicLocation de contratación  | Ciudad, provincia, código postal, y comunidad autónoma/provincia                 | Candidato de contratación\_trabajadores que\_\_EmployedApplicant que los TerminatedApplicant\_                                                                                                                                                               |
| Trabajo de contratación\_                 | Función tipo, y se incluirán                                        | Candidato de contratación\_trabajadores que\_\_EmployedApplicant que los TerminatedApplicant\_                                                                                                                                                               |
| Medios de contratación\_               | Origen de candidatos                                             | Candidato de contratación\_trabajadores que\_\_EmployedApplicant que los TerminatedApplicant\_                                                                                                                                                               |
| Rendimiento de contratación\_         | Calificación, descripción, y el modelo de evaluación                            | Candidato de contratación\_trabajadores que\_\_EmployedApplicant que los TerminatedApplicant\_                                                                                                                                                               |
| \_RecruitmentProject de contratación  | Descripción de proyecto, estado del proyecto, y aperturas                | Candidato de contratación\_trabajadores que\_\_EmployedApplicant que los TerminatedApplicant\_                                                                                                                                                               |
| \_TerminatedApplicant de contratación | Candidatos finalizados, motivo, rendimiento, y fecha final | Empresa de contratación\_trabajadores que\_\_CalendarOffset los que la fecha\_que\_GeographicLocation los trabajadores que el rendimiento\_que el Demographics los sitios\_que los el empleo\_que los medios\_\_RecruitmentProject contratación de trabajadores que\_ApplicantName |

Usaban a estas entidades para crear medidas calculadas. Estas medidas calculadas se utilizan para calcular los indicadores clave de rendimiento (KPIs) y los informes que se utilizan en el paquete del contenido. Si desea incluir cálculos adicionales sobre sus informes y panel, puede descargar y modificar el archivo de Recruiting.pbix del CD. Este archivo es el modelo de datos predeterminados usado para crear el paquete del contenido. Una vez que haya creado modificaciones, puede crear un paquete y un panel contentos de organización que contienen información que ha agregado.

## <a name="additional-resources"></a>Recursos adicionales
Estos son algunos vínculos útiles relacionados con las entidades y la creación de contenido de Power BI:

-   [Entidades de datos](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Creación de paquetes de contenido organizativo](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelado de datos con Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Adición de iconos de Power BI a espacios de trabajo](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)



