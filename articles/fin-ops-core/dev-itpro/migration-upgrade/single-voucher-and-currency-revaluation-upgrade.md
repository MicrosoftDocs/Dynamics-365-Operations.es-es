---
title: Actualizar los diarios de asiento único y las revalorizaciones de divisa
description: Algunas organizaciones especifican diarios que contienen un asiento único con más de un cliente o proveedor, y también ejecutan el proceso de revalorización de divisa de clientes o proveedores. En este tema se describen los pasos que estas organizaciones deben cumplir cuando actualizan a Microsoft Dynamics 365 for Operations versión 1611.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 7c06e54c5be8d0a410b9f15f2a89def3076b4638
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681033"
---
# <a name="upgrade-single-voucher-journals-and-currency-revaluations"></a>Actualizar diarios de asiento único y revalorizaciones de divisa

[!include [banner](../includes/banner.md)]

Algunas organizaciones especifican diarios que contienen un asiento único con más de un cliente o proveedor, y también ejecutan el proceso de revalorización de divisa de clientes o proveedores. En este tema se describen los pasos que estas organizaciones deben cumplir cuando actualizan a Microsoft Dynamics 365 for Operations versión 1611.

Siga estos pasos al actualizar a la versión 1611 de Microsoft Dynamics 365 for Operations.

1.  Antes de actualizar a Finance and Operations, ejecute los procesos de revalorización de divisa extranjera para clientes y proveedores. Establezca el campo **Método** en **Fecha de factura**. Se crea una transacción de revalorización que invierte la última revalorización de divisa extranjera. Por lo tanto, las transacciones abiertas se valoran en la divisa de contabilidad original.
2.  Actualice a la versión 1611.
3.  Ejecute de nuevo los procesos de revalorización de divisa extranjera para clientes y proveedores. Esta vez, establezca **Método** en el **Estándar**. Se crea una nueva transacción de revalorización basada en los tipos de cambio actuales. Esta transacción registra las pérdidas/ganancias no realizadas y la cuenta contable de resumen correcta.
