---
title: "Cuentas de registro de adquisición de activos fijos"
description: "En este artículo se explica cómo configurar cuentas de registro de contabilidad general para adquirir activos."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 23021
ms.assetid: d7e86f72-95db-4423-9b04-761e9536a959
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: d89bff85317a6aee952d32a9c29f0ebdd27934ec
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="fixed-asset-acquisition-posting-accounts"></a>Cuentas de registro de adquisición de activos fijos

[!include[banner](../includes/banner.md)]


En este artículo se explica cómo configurar cuentas de registro de contabilidad general para adquirir activos.

Las cuentas usadas para registrar adquisiciones de activos fijos pueden variar en función del método usado para adquirir el activo. En la página Perfiles de contabilización de activos fijos, en la pestaña Cuentas contables, seleccione Adquisición y Ajuste de adquisición para configurar cuentas de activos fijos para registrarlas en la contabilidad. 

En los diarios y en los pedidos de compra, Cuenta contable es normalmente la cuenta de balance de situación, donde se adeuda el valor de adquisición del activo fijo nuevo. Esta cuenta no se puede ver en el diario ni sustituir en las transacciones. 

Cuenta de contrapartida también es una cuenta de balance de situación. En el diario general y en diario de activos fijos, esta cuenta suele ser la cuenta bancaria utilizada para pagar la adquisición del activo. La cuenta de contrapartida es una cuenta predeterminada sugerida en los diarios. Es posible cambiarla en el diario a una cuenta del plan contable o a una cuenta del proveedor, si un proveedor ha comprado el activo fijo. 

Cuando se utiliza Diario de facturas o Pedidos de compra en Proveedores para las adquisiciones de activos fijos, la cuenta de contrapartida de la transacción de activos fijos se sustituye por la cuenta de proveedor seleccionada para la transacción.

En las adquisiciones registradas con el diario Inventario a activos fijos en la contabilidad general, el activo fijo no se compra por fuentes externas, sino que se transfiere del propio inventario de la empresa. Por lo tanto, la cuenta de contrapartida es una cuenta de emisión de inventario del artículo de inventario de Gestión del inventario.

Para obtener más información, consulte [Adquisición de activos mediante compra](acquire-assets-procurement.md).




