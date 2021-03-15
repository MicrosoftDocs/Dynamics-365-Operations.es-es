---
title: Importar datos históricos para previsiones de la demanda
description: Para obtener previsiones precisas de demanda necesita datos históricos de demanda por artículo o por clave de asignación de artículos. En este tema se explica cómo usar entidades de datos para importar datos históricos de la demanda desde cualquier sistema, de modo que tenga un historial más amplio de los datos de previsión de la demanda.
author: roxanadiaconu
manager: tfehr
ms.date: 05/10/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.assetid: 59c0d269-9db0-48e7-b8c7-9a388781a9ca
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d6ba2e1a3a884d29bff491f914aa2d5f9ece2b84
ms.sourcegitcommit: 79621e667cd7f48ba3bdbf2731f6f33d8e9f57f6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/10/2021
ms.locfileid: "5154236"
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

## <a name="example"></a>Ejemplo

Puede utilizar el siguiente archivo como ejemplo. Descargue [HistoricalDemandData](https://docs.microsoft.com/dynamics/s-e/). Este archivo contiene los datos históricos de la demanda para el artículo D0001. Contiene solo los siguientes campos obligatorios: sitio, cantidad y la fecha de la demanda.

1. Seleccione la empresa en la que desea importar los datos históricos.
2. Abra el espacio trabajo **Administración de datos** .
3. Seleccione el icono **Importar**.
4. Escriba un nombre para el proyecto de importación, como por ejemplo **Demanda histórica de importación para el artículo D0001**.
5. En el campo **Formato de datos de origen**, seleccione el formato de archivo del archivo que está importando. Para importar el archivo HistoricalDemandData para este ejemplo, seleccione **CSV**.
6. En el campo **Nombre de entidad**, seleccione **Demanda externa histórica**.
7. Guarde el archivo en su equipo y, a continuación, cárguelo.
8. Seleccione **Importar**.
9. Se abre automáticamente la página **Resumen de la ejecución**. Compruebe los datos importados en la página.

Una vez importados los datos históricos de la demanda, puede generar una previsión de la demanda.

## <a name="additional-resources"></a>Recursos adicionales

[Generar previsión estadística de línea base](generate-statistical-baseline-forecast.md)  
[Visión general de los trabajos de exportación e importación de datos](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]