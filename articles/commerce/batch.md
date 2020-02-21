---
title: Control mejorado de artículos con seguimiento por lotes
description: En este tema se describen las mejoras que se han realizado al control de los lotes para los artículos con seguimiento por lotes durante el proceso de registro de extracto.
author: josaw1
manager: AnnBe
ms.date: 11/04/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-05-28
ms.dyn365.ops.version: 10
ms.openlocfilehash: ecff18f0a34d22ef359f473fa6aaaff16c811bb6
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "3004214"
---
# <a name="improved-handling-of-batch-tracked-items"></a>Control mejorado de artículos con seguimiento por lotes


[!include [banner](includes/banner.md)]


En el punto de venta (PDV), no se pueden obtener los números de lotes para los artículos con seguimiento por lotes en el momento de la venta. Sin embargo, para las configuraciones específicas, cuando se registran las ventas en las sedes a través del registro de extractos o pedidos de clientes, el sistema de Microsoft Dynamics espera que existan números de lotes válidos para artículos con seguimiento por lotes y que se usarán durante el proceso de facturación.

Si hay números de lotes válidos disponibles para los productos, el proceso de facturación de pedidos de clientes y el proceso de facturación de pedidos de ventas del registro de extractos los usan. De lo contrario, el proceso de facturación de pedidos de clientes no puede registrar y el usuario del PDV recibe un mensaje de error. El registro de extractos entra a continuación en un estado de error. Este estado de error se produce cuando se ha activado inventario negativo para los productos.

Las mejoras que se han realizado en Retail versión 10.0.4 y posteriores ayudan a garantizar que, cuando se activa inventario negativo para artículos con seguimiento por lotes, no se bloquean la facturación de pedidos de clientes ni la facturación de pedidos de ventas a través del registro de extractos para esos artículos si el inventario es 0 (cero) o un número de lote no está disponible. La nueva funcionalidad usa un id. de lote predeterminado para las líneas de ventas cuando los números de lotes no están disponibles.

Para definir el id. de lote predeterminado que se usa para pedidos de cliente, en la página **Parámetros de Commerce**, en la pestaña **Pedidos de cliente**, en la ficha desplegable **Pedido**, establezca el campo de **Id. de lote predeterminado**.

Para definir el id. de lote predeterminado que se usa para facturación de pedidos de ventas a través del registro de extractos, en la página **Parámetros de Commerce**, en la pestaña **Registro**, en la ficha desplegable **Actualización del inventario**, establezca el campo de **id. de lote predeterminado**.

> [!NOTE]
> Esta funcionalidad solo está disponible cuando el almacenamiento avanzado está activado para los artículos y el almacén de la tienda específicos. En una versión posterior, la funcionalidad también se admitirá para escenarios donde no se use la gestión avanzada de almacenes.

> [!NOTE]
> La compatibilidad para el control mejorado de los artículos con seguimiento por lotes durante el registro de extractos para los escenarios no avanzados de gestión de almacenes se introdujo en Retail versión 10.0.5.
