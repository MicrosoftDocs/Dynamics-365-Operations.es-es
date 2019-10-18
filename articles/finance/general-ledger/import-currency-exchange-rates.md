---
title: Importar tipos de cambio de divisa
description: Si una entidad jurídica ha recibido facturas en divisas extranjeras, es necesario convertir la divisa extranjera en la divisa local. Esto significa que se requieren tipos de cambio actualizados para las distintas divisas. Este tema proporciona una visión general de los ajustes y el proceso necesarios para importar las tasas de referencia de divisa extranjera publicadas en Internet por los proveedores de tipos de cambio, como el Banco Central Europeo y el Central Bank of Russia.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ExchangeRateProviderConfiguration
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 261374
ms.assetid: b2b22868-de68-439f-914c-78c6930b7340
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: cdc9373ab22092e1f28bd087519f7476a7f2139a
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186518"
---
# <a name="import-currency-exchange-rates"></a>Importar tipos de cambio de divisa

[!include [banner](../includes/banner.md)]

Si una entidad jurídica ha recibido facturas en divisas extranjeras, es necesario convertir la divisa extranjera en la divisa local. Esto significa que se requieren tipos de cambio actualizados para las distintas divisas. Este tema proporciona una visión general de los ajustes y el proceso necesarios para importar las tasas de referencia de divisa extranjera publicadas en Internet por los proveedores de tipos de cambio, como el Banco Central Europeo y el Central Bank of Russia.

Las siguientes secciones describen el flujo de información que se utiliza para configurar y procesar la importación de tipos de cambio extranjeros.

## <a name="configure-an-exchange-rate-provider"></a>Configurar un proveedor de tipo de cambio
Para poder importar tipos de cambio, debe configurar la información requerida por los proveedores que ofrecen los tipos de cambio. Use la página **Configurar proveedores de tipo de cambio** para seleccionar los proveedores de tipo de cambio. Algunos proveedores de tipo de cambio se incluyen con los datos de demostración en Dynamics 365 Finance. En la siguiente tabla se proporcionan descripciones de los controles de este página.

|           |                                                                                                                                                                                                                             |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Campo** | **Descripción**                                                                                                                                                                                                             |
| **Nombre**  | El nombre del proveedor de tipos de cambio.                                                                                                                                                                                     |
| **Clave**   | El identificador único para cada fragmento de información de configuración que requiere el proveedor. Esta información se agrega automáticamente para cada proveedor de tipos de cambio que agregue cuando haga clic en el botón **Agregar**. |
| **Valor** | Información para cada clave. Esta información se agrega para cada proveedor de tipos de cambio que agregue cuando haga clic en el botón **Agregar**.                                                                                         |

## <a name="import-currency-exchange-rates"></a>Importar tipos de cambio de divisa
Puede importar tipos de cambio desde el origen de los proveedores del tipo de cambio y configurarlos en la página **Tipos de cambio de divisas**. Use la página **Importar tipos de cambio de divisa** para importar los tipos de cambio. La siguiente tabla proporciona descripciones de los campos necesarios para completar correctamente el proceso de importación.

|                                        |                                                                                                                                                                                                                                                                                                                                                                             |
|----------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Campo**                              | **Descripción**                                                                                                                                                                                                                                                                                                                                                             |
| **Tipo de cambio**                 | Un tipo de cambio.                                                                                                                                                                                                                                                                                                                                                      |
| **Proveedor de tipos de cambio**             | Un proveedor de tipos de cambio.                                                                                                                                                                                                                                                                                                                                                  |
| **Importar a partir de**                       | Este parámetro administra si importa a partir de la fecha de hoy o durante un intervalo de fechas. Si desea utilizar un intervalo de fecha, escriba o seleccione las fechas inicial y final del intervalo.                                                                                                                                                                                                                |
| **Crear pares de divisas necesarias**    | Esta casilla administra la creación automática de los pares de divisas, en caso de que no existan los pares de divisas que se han importado. Es posible que esta opción no esté disponible para algunos proveedores.                                                                                                                                                                                               |
| **Invalidar tipos de cambio existentes**   | Esta casilla administra la actualización del tipo de cambio existente para un par de divisas cuando ya existe el tipo de cambio para una fecha específica. Si no activa esta casilla, el tipo de cambio para las fechas específicas no se importa si ya existe otro tipo de cambio.                                                                                       |
| **Evitar la importación en una festividad nacional** | Esta casilla administra la importación del tipo de cambio para una fecha que es un día festivo. Por ejemplo, si selecciona esta casilla y usa el Banco Central Europeo como el proveedor del tipo de cambio, el sistema no actualizará el tipo de cambio en un día festivo que esté relacionado con la entidad jurídica actual. Es posible que esta opción no esté disponible para algunos proveedores. |





