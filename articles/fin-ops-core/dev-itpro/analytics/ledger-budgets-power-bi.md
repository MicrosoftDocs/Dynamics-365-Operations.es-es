---
title: Contenido Real frente a presupuesto de Power BI
description: Este artículo describe el contenido en Power BI de Real frente a presupuesto. Explica cómo acceder a los informes y proporciona información sobre el modelo de datos.
author: panolte
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetTrackingWorkspace
audience: Application user, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: ff57d052b66103ad716ad8d55afb4fcb095d2c02
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8847293"
---
# <a name="actual-vs-budget-power-bi-content"></a>Contenido Real frente a presupuesto de Power BI

[!include [banner](../includes/banner.md)]

Este artículo describe el contenido en Microsoft Power BI de **Real frente a presupuesto**. Explica cómo obtener acceso a los informes Power BI y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el contenido.

## <a name="overview"></a>Información general

El contenido en Power BI de **Real rente a presupuesto** se creó para aquellas personas que son responsables de supervisar los valores reales frente al presupuesto en su organización. El contenido en Power BI de **Real frente a presupuesto** proporciona visibilidad en las desviaciones de presupuesto. Puede analizar el presupuesto para el año actual por categoría de cuenta, código de presupuesto, cuenta principal, descripciones de la cuenta principal o período fiscal para obtener una mejor comprensión de los motivos que producen las desviaciones.

## <a name="accessing-the-power-bi-content"></a>Acceso al contenido de Power BI
Los informes del contenido de Power BI **Real frente a presupuesto** se muestran en los espacios de trabajo **Presupuestos y previsiones de libro mayor** y **CFO**.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Informes que se incluyen en el contenido de Power BI
La siguiente tabla ofrece información sobre las métricas que se encuentran en cada página de informe en el contenido de Power BI de **Real frente a presupuesto**.

| Informe                      | Métricas                                                                             |
|-----------------------------|-------------------------------------------------------------------------------------|
| Gastos reales frente a gastos de presupuesto | <ul><li>Total de gastos este año</li><li>Total de gastos de presupuesto este año</li></ul>  |
| Ingresos reales frente a ingresos de presupuesto  | <ul><li>Ingresos totales este año</li><li>Total de ingresos de presupuesto este año</li><ul>     |
| Gastos                     | <ul><li>Total de gastos este año</li><li>Objetivo de gastos en función de presupuesto</li><ul> |
| Ingresos                     | <ul><li>Ingresos totales este año</li><li>Objetivo de ingresos en función de presupuesto</li><ul>   |
| Ingresos netos                  | <ul><li>Ingresos netos este año</li><li>Objetivo de ingresos netos en función de presupuesto</li><ul>   |

## <a name="understanding-the-data-model-and-entities"></a>Comprensión del modelo de datos y de las entidades

| Entidad                    | Contenido                                                                         |
|---------------------------|----------------------------------------------------------------------------------|
| Actividades de contabilidad general | Importes de transacción de contabilidad general                                       |
| Actividades de presupuesto         | Importes de transacción para el registro presupuestario                                      |
| Cuentas principales             | Cuentas principales para filtrar informes                                               |
| Calendarios fiscales          | Calendarios fiscales para filtrar informes                                            |
| Libros mayores                   | Libros mayores que se pueden usar para filtrar el informe en la contabilidad actual              |
| Códigos de presupuesto              | Códigos presupuestarios para filtrar informes                                                |
| Entidades jurídicas            | Entidades jurídicas que se pueden usar para filtrar el informe para la entidad jurídica actual |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]