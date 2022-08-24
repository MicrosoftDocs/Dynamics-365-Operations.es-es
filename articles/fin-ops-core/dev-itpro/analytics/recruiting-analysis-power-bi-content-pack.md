---
title: Contratación de contenido de Power BI
description: Este artículo describe el contenido en Power BI de contratación.
author: jcart1106
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom: 263934
ms.assetid: 38e6827b-0819-473c-bc47-821a1ec482b8
ms.search.form: HcmRecruitmentWorkspace
ms.openlocfilehash: 412a1225544bb73649c9f0e703ec7b9a0d2613e0
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276608"
---
# <a name="recruiting-power-bi-content"></a>Contratación de contenido de Power BI

[!include [banner](../includes/banner.md)]

Este artículo describe el contenido en Microsoft Power BI de **contratación**. Explica cómo obtener acceso a los informes Power BI y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el contenido.

## <a name="accessing-the-power-bi-content"></a>Acceso al contenido de Power BI
El contenido de Power BI **Contratación** se muestra en el área de trabajo **Administración de contratación**.

## <a name="reports-and-visuals-in-the-recruitment-management-workspace"></a>Informes y representaciones visuales en el espacio de trabajo de Administración de contratación
El área de trabajo **Gestión de contratación** contiene la pestaña **Análisis**. Esta pestaña tiene el contenido de contrataciones incrustado de Power BI. El contenido consiste en una ficha de visión general y otras fichas con detalles. En la tabla siguiente se describen los informes de cada ficha.

| Informe               | Contenido |
|----------------------|----------|
| Visión general de contratación | Resume otros informes |
| Análisis del candidato   | Número total de candidatos, candidatos por trabajo, orígenes de los candidatos, proporción de candidatos hombres y mujeres y candidatos por ubicación |
| Estado del candidato     | Candidatos por tipo y estado y estado del candidato |
| Análisis de la contratación  | Relación de contratación neta, promedio de días a contratar, porcentaje de contrataciones fallidas, costes de contratación, número de proyectos de contratación, contratación aplicada y número de candidatos por puesto por proyecto de contratación |

## <a name="understanding-the-data-model-and-entities"></a>Comprensión del modelo de datos y de las entidades
Puede filtrar los gráficos e iconos en estos informes y anclar los gráficos e iconos al panel de información. Para obtener más información acerca de cómo filtrar y anclar en Power BI, consulte [Crear y configurar un panel de información](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

En la tabla siguiente se muestran las entidades en las que se basaba el contenido de Power BI de **Contratación**.

| Entidad               | Contenido                                                         | Relaciones con otras entidades |
|----------------------|------------------------------------------------------------------|-----------------------------------|
| Candidato            | Candidatos, candidatos contratados, proporción neta de contratación y costes          | Nombre del candidato, empresa, contrapartida del calendario, fecha, ubicación geográfica, grupo demográfico, trabajo, medios, proyecto de contratación |
| Nombre del candidato       | Nombre, apellido y nombre completo del candidato                   | Candidato, candidato empleado, candidato finalizado |
| Contrapartida del calendario      | Desplazamientos del calendario para dividir informes                                | Candidato, candidato empleado, candidato finalizado |
| Compañía              | Empresas para filtrar informes por                                   | Candidato, candidato empleado, candidato finalizado |
| Fecha                 | Días, semanas, meses y años                                   | Candidato, candidato empleado, candidato finalizado |
| Datos demográficos         | Fecha de nacimiento, género, origen étnico y estado civil         | Candidato, candidato empleado, candidato finalizado |
| Candidato empleado   | Candidato, rendimiento, fecha inicial y tipo del candidato           | Empresa, contrapartida del calendario, fecha, ubicación geográfica, nombre del candidato, empleo, rendimiento, trabajo, medios, proyecto de contratación |
| Empleo           | Fecha de inicio, fecha final y fecha de transición                        | Candidato, candidato empleado, candidato finalizado |
| Ubicación geográfica  | Ciudad, provincia, código postal y comunidad autónoma                 | Candidato, candidato empleado, candidato finalizado |
| Trabajo                  | Función tipo y cargo                                        | Candidato, candidato empleado, candidato finalizado |
| Medios                | Origen de los candidatos                                             | Candidato, candidato empleado, candidato finalizado |
| Rendimiento          | Calificación, descripción y modelo de calificación                            | Candidato, candidato empleado, candidato finalizado |
| Proyecto de contratación  | Descripción del proyecto, estado del proyecto y vacantes                | Candidato, candidato empleado, candidato finalizado |
| Candidato finalizado | Candidatos cesados, motivo, rendimiento y fecha de cese | Empresa, contrapartida del calendario, fecha, ubicación geográfica, rendimiento, grupo demográfico, empleo, medios, proyecto de contratación, nombre del candidato |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
