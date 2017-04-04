---
title: "Actualización de revalorización del asiento único y de divisa para Microsoft Dynamics 365 para la versión 1611 de las operaciones"
description: "Algunas organizaciones especifique los diarios que contienen un asiento único con más de un cliente o proveedor, y también ejecutan proceso de revalorización de divisa extranjera de clientes o proveedores. Este tema describe los pasos que estas organizaciones deben cumplir cuando se actualiza el Microsoft Dynamics 365 para la versión 1611 de las operaciones."
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

# <a name="single-voucher-and-currency-revaluation-upgrade-for-microsoft-dynamics-365-for-operations-version-1611"></a>Actualización de revalorización del asiento único y de divisa para Microsoft Dynamics 365 para la versión 1611 de las operaciones

Algunas organizaciones especifique los diarios que contienen un asiento único con más de un cliente o proveedor, y también ejecutan proceso de revalorización de divisa extranjera de clientes o proveedores. Este tema describe los pasos que estas organizaciones deben cumplir cuando se actualiza el Microsoft Dynamics 365 para la versión 1611 de las operaciones.

Siga estos pasos cuando se actualiza en Microsoft Dynamics 365 para la versión 1611 de las operaciones.

1.  Antes de actualizar a Dynamics 365 para las operaciones, ejecute los procesos de revalorización de divisa extranjera para clientes y proveedores. Establezca ** método ** el campo ** fecha de factura **. Se crea una transacción de revalorización de inversión la fecha de última revalorización de divisa extranjera. Por lo tanto, las transacciones abiertas se valoran en la divisa de contabilidad original.
2.  Actualice a Dynamics 365 para la versión 1611 de las operaciones.
3.  Ejecutar a clientes y la revalorización de divisa extranjera de los proveedores vuelve a procesar. Este tiempo, establece ** método ** el campo ** ** estándar. Se crea una nueva transacción de revalorización que se basa en los tipos de cambio actuales. Este registros de transacción el beneficio no realizado/pérdidas y la cuenta contable correcta de resumen.



