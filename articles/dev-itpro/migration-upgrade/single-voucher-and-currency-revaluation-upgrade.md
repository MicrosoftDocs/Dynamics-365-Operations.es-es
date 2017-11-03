---
title: "Actualización de revalorización de divisa y asiento único"
description: "Algunas organizaciones especifican diarios que contienen un asiento único con más de un cliente o proveedor, y también ejecutan el proceso de revalorización de divisa de clientes o proveedores. En este tema se describen los pasos que estas organizaciones deben cumplir cuando actualizan a Microsoft Dynamics 365 for Operations versión 1611."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 13ad43cc77731727525aae1edc4d405c166acbc1
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="single-voucher-and-currency-revaluation-upgrade"></a>Actualización de revalorización de divisa y asiento único

[!include[banner](../includes/banner.md)]


Algunas organizaciones especifican diarios que contienen un asiento único con más de un cliente o proveedor, y también ejecutan el proceso de revalorización de divisa de clientes o proveedores. En este tema se describen los pasos que estas organizaciones deben cumplir cuando actualizan a Microsoft Dynamics 365 for Operations versión 1611.

Siga estos pasos cuando actualice a Microsoft Dynamics 365 for Operations versión 1611.

1.  Antes de actualizar a Dynamics 365 for Operations, ejecute los procesos de revalorización de divisa extranjera para clientes y proveedores. Establezca el campo **Método** en **Fecha de factura**. Se crea una transacción de revalorización que invierte la última revalorización de divisa extranjera. Por lo tanto, las transacciones abiertas se valoran en la divisa de contabilidad original.
2.  Actualice a Dynamics 365 for Operations versión 1611.
3.  Ejecute de nuevo los procesos de revalorización de divisa extranjera para clientes y proveedores. Esta vez, establezca **Método** en el **Estándar**. Se crea una nueva transacción de revalorización basada en los tipos de cambio actuales. Esta transacción registra las pérdidas/ganancias no realizadas y la cuenta contable de resumen correcta.





