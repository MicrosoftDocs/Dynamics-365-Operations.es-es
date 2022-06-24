---
title: Números de serie y lote de empresas vinculadas
description: Este artículo explica lo que sucederá cuando registre números de lote y números de serie para pedidos de empresas vinculadas
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 5c743c8eee8d27a2c2357523a11236eb247ec5be
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8851518"
---
# <a name="intercompany-batch-and-serial-numbers"></a>Números de serie y lote de empresas vinculadas

[!include [banner](../../includes/banner.md)]

Las empresas que utilizan números de serie o de lote para realizar el seguimiento de sus artículos también necesitan llevar a cabo el seguimiento de los números de serie y de lote de los artículos seleccionados. La función de empresas vinculadas automatiza la introducción o la extracción de números de serie y números de lote de una empresa a otra. Cuando se registran los números de lote y de serie para los artículos en un pedido de ventas de empresas vinculadas, se puede configurar el programa para especificar estos números automáticamente en el pedido de compra de empresas vinculadas y en el pedido de ventas original. Debe configurar los parámetros relevantes en la página **Empresas vinculadas** para el pedido de ventas:

- Si selecciona el campo **Número de lote** en la página **Directivas de ventas**, el número de lote se sincroniza con las transacciones de inventario en las líneas de pedido de compra de empresas vinculadas cuando se registra el albarán del pedido de ventas de empresas vinculadas.
- Si selecciona el campo **Número de serie**, los números de serie se sincronizan con las transacciones de inventario en las líneas de pedido de compra de empresas vinculadas cuando se registra el albarán del pedido de ventas de empresas vinculadas.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
