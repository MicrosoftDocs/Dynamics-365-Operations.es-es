---
title: Configurar información de envío
description: Este tema describe cómo configurar la información de envío para el módulo de costo de entrega.
author: sherry-zheng
ms.date: 12/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMGoodsDescriptionTable, ITMVesselTable, ITMExporterTable, ITMCommodityCodeTable, ITMCustomsDescription
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-04
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 74ac7e0eac545369eef1a48f0085c820a4728e75
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833698"
---
# <a name="shipping-information-setup"></a>Configurar información de envío

[!include [banner](../../includes/banner.md)]

Este tema describe cómo configurar la información de envío para el módulo de **costo de entrega**.

## <a name="description-of-goods"></a><a name="description-of-goods"></a>Descripción de los bienes

Las descripciones de bienes ayudan a identificar un viaje, contenedor de envío o folio de bienes y los bienes que contiene. Puede seleccionar una descripción de las mercancías en el encabezado del contenedor de envío o en el encabezado del folio.

Para trabajar con descripciones de productos, vaya a **Coste de aterrizaje \> Configuración de la información de envío \> Descripción de bienes**. Allí, puede ver, abrir, crear y eliminar registros para las descripciones de los productos. En la tabla siguiente se describen los campos disponibles para cada registro.

| Campo | Descripción |
|---|---|
| Descripción de los bienes | Ingrese un nombre / número de identificación único para el tipo de bienes que utilizarán esta descripción. |
| Descripción | Ingrese una descripción del tipo de bienes en esta categoría. |

## <a name="vessels"></a><a name="vessels"></a>Embarcaciones

Un barco es el nombre único de un barco o nave que utiliza una empresa o agencia de transporte. Cuando crea un viaje, siempre debe seleccionar o ingresar un barco para él. Si utiliza con frecuencia las mismas naves, puede agilizar y facilitar la creación de un nuevo viaje creando un registro de nave para cada una de ellas, lo que permite a los usuarios seleccionar la nave de una lista en lugar de ingresar el nombre o el número manualmente cada vez.

Para trabajar con naves, vaya a **Coste de aterrizaje \> Configuración de la información de envío \> Naves**. Allí, puede ver, abrir, crear y eliminar registros para naves. En la tabla siguiente se describen los campos disponibles para cada registro.

| Campo | Descripción |
|---|---|
| Embarcación | Ingrese un nombre / número de identificación único para el barco que se utilizará para transportar mercancías en un viaje. |
| Descripción | Especifique una descripción de la nave. Por lo general, esta descripción identifica el nombre del barco y la compañía / agente de envío. |
| Modo de entrega | Seleccione el modo de entrega que utiliza la nave (como _Aéreo_, _Marítimo_ o _Ferroviario_). |

## <a name="exporters"></a>Exportadores

Cada registro de exportador identifica un proveedor o exportador que puede definirse como el proveedor de un viaje. El exportador puede asociarse con un viaje y utilizarse para informar.

Para trabajar con exportadores, vaya a **Coste de aterrizaje \> Configuración de la información de envío \> Exportadores**. Allí, puede ver, abrir, crear y eliminar registros para exportadores. En la tabla siguiente se describen los campos disponibles para cada registro.

| Campo | Descripción |
|---|---|
| Exportador | Ingrese un nombre / número de identificación único para el exportador de bienes que se transportan en un viaje. |
| Descripción | Especifique una descripción del exportador. Por lo general, esta descripción identifica el nombre completo de la compañía/agente de envío. |

## <a name="commodity-codes"></a>Códigos de mercancías

Utiliza códigos de productos básicos para ayudar con la identificación de aduanas y el cálculo de las tasas arancelarias para las mercancías en un viaje. Puede seleccionar códigos de productos en la página **Productos lanzados**.

Para trabajar con códigos de mercacnía, vaya a **Coste de aterrizaje \> Configuración de la información de envío \> Códigos de mercancía**. Allí, puede ver, abrir, crear y eliminar registros para códigos de mercacnía. En la tabla siguiente se describen los campos disponibles para cada registro.

| Campo | Descripción |
|---|---|
| Código de mercancía | Ingrese un código único para este tipo de producto. |
| Descripción | Especifique una descripción del código de tipo de mercancía. |

## <a name="customs-description"></a>Descripción de aduanas

Las descripciones aduaneras ayudan a identificar las mercancías con fines aduaneros. Puede seleccionar una descripción de aduana en la página **Productos lanzados** o en las líneas de la orden de compra.

Para trabajar con descripciones de aduanas, vaya a **Coste de aterrizaje \> Configuración de la información de envío \> Descripción de aduanas**. Allí, puede ver, abrir, crear y eliminar registros para las descripciones de aduanas. En la tabla siguiente se describen los campos disponibles para cada registro.

| Campo | Descripción |
|---|---|
| Descripción de aduanas | Ingrese un código único para este tipo de clasificación de aduanas. A menudo, este código será la descripción oficial proporcionada por una autoridad aduanera para la descripción y el valor cualitativo de las mercancías. |
| Descripción | Especifique una descripción del grupo de clasificación de aduanas. |
