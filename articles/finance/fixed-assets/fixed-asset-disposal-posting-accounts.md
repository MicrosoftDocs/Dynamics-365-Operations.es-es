---
title: Cuentas de registro de cancelación de activos fijos
description: En este artículo se explica cómo configurar cuentas de registro de contabilidad general para cancelar activos.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: kfend
ms.custom: 3461
ms.assetid: dfdc0730-e030-48cc-8d93-15bdc7b23776
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1272cdb16396d24b5495f023e7b9fe3dee341507
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871344"
---
# <a name="fixed-asset-disposal-posting-accounts"></a>Cuentas de registro de cancelación de activos fijos

[!include [banner](../includes/banner.md)]

En este artículo se explica cómo configurar cuentas de registro de contabilidad general cuando cancela activos.

Para configurar cuentas de registro del libro mayor para usar cuando se deshaga de un activo, seleccione **Eliminación - venta** y **Eliminación - desperdicio** en la ficha desplegable **Cuentas contables** en la página **Perfiles de contabilización de activos fijos**.

Para los dos tipos de transacciones (cancelar un activo por venta o desperdicio), la cuenta contable se abona para el valor de cancelación del activo fijo. El débito se registra en una cuenta de contrapartida que puede ser, por ejemplo, una cuenta bancaria (como ejemplo). Si se vende un activo fijo a un cliente, la cuenta del cliente se utiliza en lugar de la cuenta de contrapartida. Para más información, vea [Disponer de un activo fijo como chatarra](dispose-of-a-fixed-asset-as-scrap.md).

Haga clic en **Cancelación**, después en **Venta** o **Residual** y, a continuación, configure cuentas detalladas para revertir el valor neto en los libros de los activos fijos. También puede especificar información en los campos **Valor contable** y **Valor de ventas** en la página **Parámetros de cancelación**. 

La transacción de cancelación de un activo de valor reducido reduce el valor neto en los libros del activo de valor reducido sólo por el importe cancelado. Sin embargo, cuando la venta de un activo excede el valor neto en los libros del activo de valor reducido, el valor neto en los libros se reduce a cero.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
