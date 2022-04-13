---
title: Importar datos históricos para previsiones de la demanda
description: Para obtener previsiones precisas de demanda necesita datos históricos de demanda por artículo o por clave de asignación de artículos. En este tema se explica cómo usar entidades de datos para importar datos históricos de la demanda desde cualquier sistema, de modo que tenga un historial más amplio de los datos de previsión de la demanda.
author: t-benebo
ms.date: 05/10/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.assetid: 59c0d269-9db0-48e7-b8c7-9a388781a9ca
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c52d27d6e3aa8a20d6cc1dc81e4ade981c6a8091
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2022
ms.locfileid: "8470412"
---
# <a name="import-historical-data-for-demand-forecasts"></a>Importar datos históricos para previsiones de la demanda

[!include [banner](../includes/banner.md)]

Como ayuda para garantizar la precisión de las previsiones de demanda, debe tener todos los datos históricos de demanda que pueda obtener por artículo o por clave de asignación de artículos. Si aún no ha importado los datos históricos de demanda, utilice la entidad de datos **Demanda externa histórica** (ReqDemPlanHistoricalExternalDemandEntity) de Dynamics 365 Supply Chain Management para importarlos.

En el espacio de trabajo **Administración de datos** podrá ver una descripción de todos los campos de la entidad.

1. Abra el espacio trabajo **Administración de datos** .
2. Seleccione el icono **Entidades de datos**.
3. Busque la lista de entidades para **Demanda externa histórica**.
4. Seleccione **Campos objetivo**. Los siguientes campos de entidad son obligatorios: sitio (**DeliveringSiteId**), fecha (**DemandDate**), cantidad (**DemandQuantity**), y número de artículo (**ItemNumber**) o clave de asignación de artículos (**ProductAllocationKeyId**).

Para usar la entidad de datos debe tener un archivo de Microsoft Excel o de valores separados por comas (CSV) que contenga los datos históricos de la demanda. El siguiente ejemplo muestra cómo importar datos desde un archivo CSV.

Para obtener más información sobre cómo importar datos, incluido cómo limpiar datos después de una importación, consulte [Descripción general de trabajos de importación y exportación de datos](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md) y sus temas relacionados.

Vea también [Generar previsión estadística de línea base](generate-statistical-baseline-forecast.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]