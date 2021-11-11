---
title: Números de serie y lote de empresas vinculadas
description: Este tema explica lo que sucederá cuando registre números de lote y números de serie para pedidos de empresas vinculadas
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 4da936263bb57c24eeb7021ac61b3945bb2777fb
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548527"
---
# <a name="intercompany-batch-and-serial-numbers"></a>Números de serie y lote de empresas vinculadas

[!include [banner](../../includes/banner.md)]

Las empresas que utilizan números de serie o de lote para realizar el seguimiento de sus artículos también necesitan llevar a cabo el seguimiento de los números de serie y de lote de los artículos seleccionados. La función de empresas vinculadas automatiza la introducción o la extracción de números de serie y números de lote de una empresa a otra. Cuando se registran los números de lote y de serie para los artículos en un pedido de ventas de empresas vinculadas, se puede configurar el programa para especificar estos números automáticamente en el pedido de compra de empresas vinculadas y en el pedido de ventas original. Debe configurar los parámetros relevantes en la página **Empresas vinculadas** para el pedido de ventas:

- Si selecciona el campo **Número de lote** en la página **Directivas de ventas**, el número de lote se sincroniza con las transacciones de inventario en las líneas de pedido de compra de empresas vinculadas cuando se registra el albarán del pedido de ventas de empresas vinculadas.
- Si selecciona el campo **Número de serie**, los números de serie se sincronizan con las transacciones de inventario en las líneas de pedido de compra de empresas vinculadas cuando se registra el albarán del pedido de ventas de empresas vinculadas.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]