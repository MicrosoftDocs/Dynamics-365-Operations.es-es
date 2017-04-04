---
title: "Cuentas de registro de cancelación de activos fijos"
description: "En este artículo se explica cómo configurar cuentas de registro de contabilidad general para cancelar activos."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3461
ms.assetid: dfdc0730-e030-48cc-8d93-15bdc7b23776
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3b16ef53f9fb57a6663db0be1f7e0a57471db2fb
ms.openlocfilehash: 670a67de2287fa5d0be29463f6f456b27fd88000
ms.lasthandoff: 03/31/2017


---

# <a name="fixed-asset-disposal-posting-accounts"></a>Cuentas de registro de cancelación de activos fijos

En este artículo se explica cómo configurar cuentas de registro de contabilidad general para cancelar activos.

En la página Perfiles de contabilización de activos fijos, en la ficha desplegable Cuentas contables, seleccione Venta y Cancelación para configurar los registros en el libro mayor.

Para los dos tipos de transacciones, la cuenta contable se abona para el valor de cancelación del activo fijo. El débito se registra en una cuenta de contrapartida que puede ser, por ejemplo, una cuenta bancaria. Si se vende un activo fijo a un cliente, la cuenta del cliente se utiliza en lugar de la cuenta de contrapartida.

Haga clic en Cancelación, después en Venta o residual y, a continuación, configure cuentas detalladas para revertir el valor neto en los libros de los activos fijos. También puede especificar información en los campos Valor contable y Valor de ventas en la página Parámetros de cancelación. 

La transacción de cancelación de un activo de valor reducido reduce el valor neto en los libros del activo de valor reducido sólo por el importe cancelado. Sin embargo, cuando la venta de un activo excede el valor neto en los libros del activo de valor reducido, el valor neto en los libros se reduce a cero.




