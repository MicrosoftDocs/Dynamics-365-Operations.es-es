---
title: "Resolver las discrepancias durante la conciliación de los totales de las facturas"
description: 
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 63413
ms.assetid: 9ac42457-95b2-4191-ad06-c7e323704466
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 1fd606817b06a05b9abaaedf20ea9872bd7edd5d
ms.openlocfilehash: a54b05bba2549a42f24b8425c9ee418c576d056a
ms.lasthandoff: 03/31/2017


---

# <a name="resolve-discrepancies-during-invoice-totals-matching"></a>Resolver las discrepancias durante la conciliación de los totales de las facturas



Un tipo de validación de conciliación de facturas es la conciliación de los totales de las facturas. Para especificar que el sistema debe realizar la conciliación de totales de facturas, en la página **Parámetros de proveedores**, en la pestaña **Validación de facturas**, defina la opción **Conciliar totales de facturas** a **Sí**. 

Puede usar la conciliación de totales de factura para asegurarse de que los importes totales de factura no se desvían de los importes planificados más de la desviación aceptable. Se comparan seis totales en la página **Detalles de la conciliación de totales de facturas**. Si alguno de los totales se desvía del correspondiente total de pedido de compra previsto, se marca una discrepancia de conciliación. 

Para revisar la factura con discrepancias de conciliación de totales, en el área de trabajo **Entrada de la factura de proveedor**, haga clic en el mosaico **Facturas pendientes**. Luego, en el panel de acciones, en la pestaña **Revisar**, haga clic en **Detalles de conciliación**. Si se han detectado discrepancias de conciliación, los iconos de advertencia aparecen junto al importe de la factura. Puede ver más detalles sobre los totales en los detalles de la conciliación de totales de facturas. 

Una vez haya identificado la discrepancia, es posible que deba ponerse en contacto con el proveedor si cree que la información de la factura es incorrecta. Dependiendo del acuerdo resultante con el proveedor, podrá llevar a cabo una de las siguientes acciones:

-   Aceptar la diferencia de precio y registrar la factura con discrepancias. El sistema se puede configurar para requerir la aprobación antes de que pueda registrar si existen discrepancias. En este caso, debe aprobar la discrepancia en la conciliación y puede especificar de forma opcional un comentario de aprobación. Después puede seleccionar registrar la factura.
-   Revisar el importe de la factura con el importe previsto y registrar la factura.
-   Solicitar un crédito previo del proveedor y una nueva factura corregida.



