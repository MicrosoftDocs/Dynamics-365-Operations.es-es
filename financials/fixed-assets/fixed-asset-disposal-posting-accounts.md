---
title: "Cuentas de registro de cancelación de activos fijos"
description: "En este artículo se explica cómo configurar cuentas de registro de contabilidad general para cancelar activos."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 0540ba30cb26abe274075deea80ca1e9cfc686f9
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="fixed-asset-disposal-posting-accounts"></a>Cuentas de registro de cancelación de activos fijos

[!include[banner](../includes/banner.md)]


En este artículo se explica cómo configurar cuentas de registro de contabilidad general para cancelar activos.

En la página Perfiles de contabilización de activos fijos, en la ficha desplegable Cuentas contables, seleccione Venta y Cancelación para configurar los registros en el libro mayor.

Para los dos tipos de transacciones, la cuenta contable se abona para el valor de cancelación del activo fijo. El débito se registra en una cuenta de contrapartida que puede ser, por ejemplo, una cuenta bancaria. Si se vende un activo fijo a un cliente, la cuenta del cliente se utiliza en lugar de la cuenta de contrapartida.

Haga clic en Cancelación, después en Venta o residual y, a continuación, configure cuentas detalladas para revertir el valor neto en los libros de los activos fijos. También puede especificar información en los campos Valor contable y Valor de ventas en la página Parámetros de cancelación. 

La transacción de cancelación de un activo de valor reducido reduce el valor neto en los libros del activo de valor reducido sólo por el importe cancelado. Sin embargo, cuando la venta de un activo excede el valor neto en los libros del activo de valor reducido, el valor neto en los libros se reduce a cero.






