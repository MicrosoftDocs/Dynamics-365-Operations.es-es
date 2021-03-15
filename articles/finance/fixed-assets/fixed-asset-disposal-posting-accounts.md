---
title: Cuentas de registro de cancelación de activos fijos
description: En este tema se explica cómo configurar cuentas de registro de contabilidad general para cancelar activos.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: roschlom
ms.custom: 3461
ms.assetid: dfdc0730-e030-48cc-8d93-15bdc7b23776
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 67d9c386b5da90918226e8b1a224bf628c65702b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4989011"
---
# <a name="fixed-asset-disposal-posting-accounts"></a>Cuentas de registro de cancelación de activos fijos

[!include [banner](../includes/banner.md)]

En este tema se explica cómo configurar cuentas de registro de contabilidad general para cancelar activos.

En la página Perfiles de contabilización de activos fijos, en la ficha desplegable Cuentas contables, seleccione Venta y Cancelación para configurar los registros en el libro mayor.

Para los dos tipos de transacciones, la cuenta contable se abona para el valor de cancelación del activo fijo. El débito se registra en una cuenta de contrapartida que puede ser, por ejemplo, una cuenta bancaria. Si se vende un activo fijo a un cliente, la cuenta del cliente se utiliza en lugar de la cuenta de contrapartida.

Haga clic en Cancelación, después en Venta o residual y, a continuación, configure cuentas detalladas para revertir el valor neto en los libros de los activos fijos. También puede especificar información en los campos Valor contable y Valor de ventas en la página Parámetros de cancelación. 

La transacción de cancelación de un activo de valor reducido reduce el valor neto en los libros del activo de valor reducido sólo por el importe cancelado. Sin embargo, cuando la venta de un activo excede el valor neto en los libros del activo de valor reducido, el valor neto en los libros se reduce a cero.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]