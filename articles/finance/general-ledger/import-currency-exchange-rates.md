---
title: Importar tipos de cambio de divisa
description: Este tema proporciona información sobre los requisitos para importar tasas de referencia de divisa extranjera publicadas por los proveedores de tipo de cambio.
author: EvgenyPopovMBS
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ExchangeRateProviderConfiguration
audience: Application User
ms.reviewer: kfend
ms.custom: 261374
ms.assetid: b2b22868-de68-439f-914c-78c6930b7340
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: f96622132be3c8a404f3f4e9c34f3ac5085a4fdc007ecb627d06a95d7c80932b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6727333"
---
# <a name="import-currency-exchange-rates"></a>Importar tipos de cambio de divisa

[!include [banner](../includes/banner.md)]

Si una entidad jurídica ha recibido facturas en divisas extranjeras, la divisa extranjera se debe convertir en la divisa local. Esto significa que se requieren tipos de cambio actualizados para las distintas divisas. Este tema proporciona una visión general de los ajustes y el proceso necesarios para importar las tasas de referencia de divisa extranjera publicadas por los proveedores de tipos de cambio, como el Banco Central Europeo y el Central Bank of Russia.

Las siguientes secciones describen el flujo de información que se utiliza para configurar y procesar la importación de tipos de cambio extranjeros.

## <a name="configure-an-exchange-rate-provider"></a>Configurar un proveedor de tipo de cambio
Para poder importar tipos de cambio, debe configurar la información requerida por los proveedores que ofrecen los tipos de cambio. Use la página **Configurar proveedores de tipo de cambio** para seleccionar los proveedores de tipo de cambio. Algunos proveedores de tipo de cambio se incluyen con los datos de demostración en Dynamics 365 Finance. En la siguiente tabla se proporcionan descripciones de los controles de este página.

| Campo | Descripción                   |
|-----------|-----------------------------------|
| **Nombre**  | El nombre del proveedor de tipos de cambio.                                                                                                                                                                                     |
| **Clave**   | El identificador único para cada fragmento de información de configuración que requiere el proveedor. Esta información se agrega automáticamente para cada proveedor de tipos de cambio que se agregue. |
| **Valor** | Información para cada clave. Esta información se agrega para cada proveedor de tipos de cambio que se agregue.                                                                                         |

## <a name="import-currency-exchange-rates"></a>Importar tipos de cambio de divisa
Puede importar tipos de cambio desde el origen de los proveedores del tipo de cambio y agregarlos a la página **Tipos de cambio de divisas**. Use la página **Importar tipos de cambio de divisa** para importar los tipos de cambio. La siguiente tabla proporciona descripciones de los campos necesarios para completar correctamente el proceso de importación.

| Campo | Descripción                   |
|-----------|-----------------------------------|
| **Tipo de cambio**                 | Un tipo de cambio.                                                                                                                                                                                                                                                                                                                                                      |
| **Proveedor de tipos de cambio**             | Un proveedor de tipos de cambio.                                                                                                                                                                                                                                                                                                                                                  |
| **Importar a partir de**                       | Este parámetro administra si importa a partir de la fecha actual o durante un intervalo de fechas específico. Si desea utilizar un intervalo de fecha, escriba o seleccione las fechas inicial y final.                                                                                                                                                                                                                |
| **Crear pares de divisas necesarias**    | Esta casilla administra la creación automática de los pares de divisas, en caso de que no existan los pares de divisas que se han importado. Es posible que esta opción no esté disponible para algunos proveedores.                                                                                                                                                                                               |
| **Invalidar tipos de cambio existentes**   | Esta casilla administra la actualización del tipo de cambio existente para un par de divisas cuando ya existe el tipo de cambio para una fecha específica. Si no activa esta casilla, el tipo de cambio para las fechas específicas no se importa si ya existe otro tipo de cambio.                                                                                       |
| **Evitar la importación en una festividad nacional** | Esta casilla administra la importación del tipo de cambio para la fecha de un día festivo. Por ejemplo, si selecciona esta casilla y usa el Banco Central Europeo como el proveedor del tipo de cambio, el sistema no actualizará el tipo de cambio en un día festivo que esté relacionado con la entidad jurídica actual. Es posible que esta opción no esté disponible para algunos proveedores. |
| **Tipo de cambio del día anterior** | Esta casilla de verificación está disponible si habilita la característica **Importación BCE en la fecha actual o anterior** de la página **Administración de características**. Esta casilla de verificación solo está disponible para el proveedor, *Banco Central Europeo*. Seleccione esta casilla para importar el tipo de cambio de divisa que ha publicado el Banco Central Europeo en el día laborable anterior a las 16:00 CET aproximadamente. La casilla de verificación está activada de forma predeterminada. Desactive esta casilla para importar el tipo de cambio de divisa que se publica el mismo día hábil.  |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]