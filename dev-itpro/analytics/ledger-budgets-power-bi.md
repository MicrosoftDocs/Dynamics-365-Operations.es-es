---
title: Contenido en Power BI de Real frente a presupuesto
description: "Este tema describe el contenido en Power BI de Real frente a presupuesto Explica cómo tener acceso a los informes que se incluyen en el contenido, y proporciona información acerca del modelo de datos y las entidades que se utilizaron para generar el contenido."
author: ryansandness
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application user, IT Pro
ms.search.scope: Core, Operations, UnifiedOperations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 5d52cce3cccb16f0645d9de1832ebeffbfaf3a09
ms.contentlocale: es-es
ms.lasthandoff: 06/13/2017

---

# Contenido en Power BI de Real frente a presupuesto
<a id="actual-vs-budget-power-bi-content" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Este tema describe el contenido en Microsoft Power BI de **Real frente a presupuesto** Explica cómo obtener acceso a los informes de Power BI y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el contenido. 

# Información general
<a id="overview" class="xliff"></a>

El contenido en Power BI de **Real rente a presupuesto** se creó para aquellas personas que son responsables de supervisar los valores reales frente al presupuesto en su organización. El contenido en Power BI de **Real frente a presupuesto** proporciona visibilidad en las desviaciones de presupuesto. Puede analizar el presupuesto para el año actual por categoría de cuenta, código de presupuesto, cuenta principal, descripciones de la cuenta principal o período fiscal para obtener una mejor comprensión de los motivos que producen las desviaciones. 

# Acceso al contenido de Power BI
<a id="accessing-the-power-bi-content" class="xliff"></a>
Si está usando Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (actualización de julio de 2017), los informes a partir del contenido en Power BI de **Real frente a presupuesto** aparecen en los espacios de trabajo **Presupuestos y previsiones de libro mayor** y **Director financiero**.

# Informes que se incluyen en el contenido de Power BI
<a id="reports-that-are-included-in-the-power-bi-content" class="xliff"></a>
La siguiente tabla ofrece información sobre las métricas que se encuentran en cada página de informe en el contenido de Power BI de **Real frente a presupuesto**.

| Informe                      | Métricas |
|-----------------------------|---------|
| Gastos reales frente a gastos de presupuesto | <ul><li>Total de gastos este año</li><li>Total de gastos de presupuesto este año</li></ul> |
| Ingresos reales frente a ingresos de presupuesto  | <ul><li>Ingresos totales este año</li><li>Total de ingresos de presupuesto este año</li><ul> |
| Gastos                     | <ul><li>Total de gastos este año</li><li>Objetivo de gastos en función de presupuesto </li><ul> |
| Ingresos                     | <ul><li>Ingresos totales este año</li><li>Objetivo de ingresos en función de presupuesto </li><ul> |
| Ingresos netos                  | <ul><li>Ingresos netos este año</li><li>Objetivo de ingresos netos en función de presupuesto </li><ul> |

## Ampliar el contenido de Power BI
<a id="extending-the-power-bi-content" class="xliff"></a>
Mediante los paquetes de contenido disponibles en Microsoft Dynamics Lifecycle Services (LCS), puede ofrecer análisis muy buenos a las personas que no inician sesión en Microsoft Dynamics 365. Puede modificar estos paquetes de contenido para que incluyan otros informes o representaciones visuales y, a continuación, publicar los paquetes de contenidos en el inquilino de Power BI.com para su análisis. 

Puede encontrar el contenido en Power BI de **Real frente a presupuesto** en la biblioteca de activos compartidos de LCS. Para obtener información sobre cómo descargar contenido e implementarlo en su organización, consulte [Contenido de Power BI en LCS en Microsoft y sus socios](power-bi-content-microsoft-partners.md). Para ver una demostración que muestra cómo implementar el contenido de Power BI, consulte [Contenido de Power BI de Microsoft y sus socios en Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) (Office Mix).

# Comprensión del modelo de datos y de las entidades
<a id="understanding-the-data-model-and-entities" class="xliff"></a>

| Entidad                    | Contenido |
|---------------------------|----------|
| Actividades de contabilidad general | Importes de transacción de contabilidad general |
| Actividades de presupuesto         | Importes de transacción para el registro presupuestario |
| Cuentas principales             | Cuentas principales para filtrar informes |
| Calendarios fiscales          | Calendarios fiscales para filtrar informes |
| Libros mayores                   | Libros mayores que se pueden usar para filtrar el informe en la contabilidad actual |
| Códigos de presupuesto              | Códigos presupuestarios para filtrar informes |
| Entidades jurídicas            | Entidades jurídicas que se pueden usar para filtrar el informe para la entidad jurídica actual |

