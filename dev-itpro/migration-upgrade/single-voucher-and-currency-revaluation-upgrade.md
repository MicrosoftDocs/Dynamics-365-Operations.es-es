---
title: "Actualización de asiento único y revalorización de divisa para Microsoft Dynamics 365 for Operations versión 1611"
description: "Algunas organizaciones especifican diarios que contienen un asiento único con más de un cliente o proveedor, y también ejecutan el proceso de revalorización de divisa de clientes o proveedores. En este tema se describen los pasos que estas organizaciones deben cumplir cuando actualizan a Microsoft Dynamics 365 for Operations versión 1611."
author: twheeloc
manager: AnnBe
ms.date: 2016-12-28 16 - 04 - 17
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: d42c753d0dc8b8efc2a0d2a26da32a4951d85503
ms.lasthandoff: 03/31/2017


---

# <a name="single-voucher-and-currency-revaluation-upgrade-for-microsoft-dynamics-365-for-operations-version-1611"></a>Actualización de asiento único y revalorización de divisa para Microsoft Dynamics 365 for Operations versión 1611

Algunas organizaciones especifican diarios que contienen un asiento único con más de un cliente o proveedor, y también ejecutan el proceso de revalorización de divisa de clientes o proveedores. En este tema se describen los pasos que estas organizaciones deben cumplir cuando actualizan a Microsoft Dynamics 365 for Operations versión 1611.

Siga estos pasos cuando actualice a Microsoft Dynamics 365 for Operations versión 1611.

1.  Antes de actualizar a Dynamics 365 for Operations, ejecute los procesos de revalorización de divisa extranjera para clientes y proveedores. Establezca el campo **Método** en **Fecha de factura**. Se crea una transacción de revalorización que invierte la última revalorización de divisa extranjera. Por lo tanto, las transacciones abiertas se valoran en la divisa de contabilidad original.
2.  Actualice a Dynamics 365 for Operations versión 1611.
3.  Ejecute de nuevo los procesos de revalorización de divisa extranjera para clientes y proveedores. Esta vez, establezca **Método** en ** el **Estándar**. Se crea una nueva transacción de revalorización basada en los tipos de cambio actuales. Esta transacción registra las pérdidas/ganancias no realizadas y la cuenta contable de resumen correcta.



