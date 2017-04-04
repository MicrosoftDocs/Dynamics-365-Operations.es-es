---
title: Importar tipos de cambio de divisa
description: "Si una entidad jurídica ha recibido facturas en divisas extranjeras, es necesario convertir la divisa extranjera en la divisa local. Esto significa que requieren los tipos de cambio actualizados para las divisas distintas. Este tema proporciona una visión general de la configuración y de procesamiento necesarios para importar las tasas de referencia de divisa extranjera publicadas por Internet por los proveedores del tipo de cambio, como el Banco Central Europeo y el banco central de Rusia."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ExchangeRateProviderConfiguration
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 261374
ms.assetid: b2b22868-de68-439f-914c-78c6930b7340
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: bf66a1b1c9314b454223274810a21913d54b702d
ms.lasthandoff: 03/31/2017


---

# <a name="import-currency-exchange-rates"></a>Importar tipos de cambio de divisa

Si una entidad jurídica ha recibido facturas en divisas extranjeras, es necesario convertir la divisa extranjera en la divisa local. Esto significa que requieren los tipos de cambio actualizados para las divisas distintas. Este tema proporciona una visión general de la configuración y de procesamiento necesarios para importar las tasas de referencia de divisa extranjera publicadas por Internet por los proveedores del tipo de cambio, como el Banco Central Europeo y el banco central de Rusia.

Las secciones siguientes describen el flujo de información que se usa para capitalizar y procesar la importación de tasas de divisas.

## <a name="configure-an-exchange-rate-provider"></a>Configurar un proveedor del tipo de cambio
Para poder importar tipos de cambio, debe configurar la información requerida por los proveedores que proporcionan a los tipos de cambio. Use ** configurar los proveedores del tipo de cambio ** la página para seleccionar los proveedores del tipo de cambio. Algunos proveedores de tipo de cambio se incluyen con los datos de prueba en Microsoft Dynamics 365 para las operaciones. La siguiente tabla ofrece descripciones de los controles de esta página.

|           |                                                                                                                                                                                                                             |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Field** | **Description**                                                                                                                                                                                                             |
| **Name**  | El nombre del proveedor de tipos de cambio.                                                                                                                                                                                     |
| ** Tecla **   | El identificador único para cada fragmento de información de configuración que requiere el proveedor. Esta información se agrega automáticamente para cada proveedor del tipo de cambio que se agregan al hacer clic en ** agregue ** el botón. |
| **Value** | Información para cada clave. Esta información se agrega para cada proveedor del tipo de cambio que se agregan al hacer clic en ** agregue ** el botón.                                                                                         |

## <a name="import-currency-exchange-rates"></a>Importar tipos de cambio de divisa
Puede importar tipos de cambio del origen de los proveedores del tipo de cambio, y liquidarlos hacia arriba en ** los tipos de cambio de divisa ** la página. ** Use los tipos de cambio de divisa de importación ** la página para importar los tipos de cambio. En la tabla siguiente se proporcionan descripciones los campos necesarios para completar correctamente el proceso de importación.

|                                        |                                                                                                                                                                                                                                                                                                                                                                             |
|----------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Field**                              | **Description**                                                                                                                                                                                                                                                                                                                                                             |
| **Exchange rate type**                 | Un tipo de cambio.                                                                                                                                                                                                                                                                                                                                                      |
| **Exchange rate provider**             | Un proveedor del tipo de cambio.                                                                                                                                                                                                                                                                                                                                                  |
| **Import as of**                       | Este parámetro si administra importar a partir de la fecha de hoy o para un intervalo de fechas. Si desea usar un intervalo de fechas, especifique o seleccione las fechas iniciales y finales.                                                                                                                                                                                                                |
| **Create necessary currency pairs**    | Esta casilla administrar la creación automática de par de divisas, si no existen pares de divisas se han importado. Esta opción no esté disponible para algunos proveedores.                                                                                                                                                                                               |
| **Override existing exchange rates**   | Esta casilla administrar la actualización del tipo de cambio existente para un par de divisas cuando existe el tipo de cambio para una fecha específica ya. Si no activa esta casilla, no importan el tipo de cambio para fechas específicas si existe otro tipo de cambio ya.                                                                                       |
| **Prevent import on national holiday** | Esta casilla administrar la importación del tipo de cambio para una fecha que sea del día festivo. Por ejemplo, si selecciona esta casilla y usa el Banco Central Europeo como el proveedor del tipo de cambio, el sistema no actualizará el tipo de cambio en un día festivo que esté relacionado con la entidad jurídica actual. Esta opción no esté disponible para algunos proveedores. |




