---
title: Visión general de la resolución de discrepancias durante la conciliación de los totales de las facturas
description: Puede usar la conciliación de totales de factura para asegurarse de que los importes totales de factura no se desvían de los importes planificados más de la desviación aceptable.
author: abruer
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 63413,  ""intro-internal
ms.assetid: 9ac42457-95b2-4191-ad06-c7e323704466
ms.search.form: VendTotalPriceTolerance
ms.openlocfilehash: fa248622a21b0571b08c97eff507ee1035daa7f9
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268599"
---
# <a name="resolve-discrepancies-during-invoice-totals-matching-overview"></a>Visión general de la resolución de discrepancias durante la conciliación de los totales de las facturas

[!include [banner](../includes/banner.md)]

Un tipo de validación de conciliación de facturas es la conciliación de los totales de las facturas. Para especificar que el sistema debe realizar la conciliación de totales de facturas, en la página **Parámetros de proveedores**, en la pestaña **Validación de facturas**, defina la opción **Conciliar totales de facturas** a **Sí**. 

Puede usar la conciliación de totales de factura para asegurarse de que los importes totales de factura no se desvían de los importes planificados más de la desviación aceptable. Se comparan seis totales en la página **Detalles de la conciliación de totales de facturas**. Si alguno de los totales se desvía del correspondiente total de pedido de compra previsto, se marca una discrepancia de conciliación. 

Para revisar la factura con discrepancias de conciliación de totales, en el área de trabajo **Entrada de la factura de proveedor**, haga clic en el mosaico **Facturas pendientes**. Luego, en el panel de acciones, en la pestaña **Revisar**, haga clic en **Detalles de conciliación**. Si se han detectado discrepancias de conciliación, los iconos de advertencia aparecen junto al importe de la factura. Puede ver más detalles sobre los totales en los detalles de la conciliación de totales de facturas. 

Una vez haya identificado la discrepancia, es posible que deba ponerse en contacto con el proveedor si cree que la información de la factura es incorrecta. Dependiendo del acuerdo resultante con el proveedor, podrá llevar a cabo una de las siguientes acciones:

-   Aceptar la diferencia de precio y registrar la factura con discrepancias. El sistema se puede configurar para requerir la aprobación antes de que pueda registrar si existen discrepancias. En este caso, debe aprobar la discrepancia en la conciliación y puede especificar de forma opcional un comentario de aprobación. Después puede seleccionar registrar la factura.
-   Revisar el importe de la factura con el importe previsto y registrar la factura.
-   Solicitar un crédito previo del proveedor y una nueva factura corregida.

Para obtener más información, consulte [Investigar o resolver las excepciones](tasks/research-resolve-exceptions.md).




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
