---
title: "Espacio de trabajo de facturación de colaboración de proveedor"
description: "Este tema explica cómo puede ver las facturas de proveedor y enviar las facturas desde el espacio de trabajo de la facturacíon de colaboración de proveedor."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 221534
ms.assetid: c4ed62f3-d351-41d7-a2ad-790576cde4ab
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 7aebcdf0578d931d326420b42e2b220407049bc6
ms.contentlocale: es-es
ms.lasthandoff: 04/25/2017


---

# <a name="vendor-collaboration-invoicing-workspace"></a>Espacio de trabajo de facturación de colaboración de proveedor

[!include[banner](../includes/banner.md)]


Este tema explica cómo puede ver las facturas de proveedor y enviar las facturas desde el espacio de trabajo de la facturacíon de colaboración de proveedor.

El espacio de trabajo de **Facturación de colaboración de proveedor** se puede usar para ver información de la factura de proveedor y para enviar facturas a Microsoft Dynamics 365 for Operations mediante capacidades del flujo de trabajo.
Espacio de trabajo de facturación de colaboración de proveedor
----------------------------------------

### <a name="summary-tiles"></a>Iconos de resumen

Las fichas de **Resumen** ofrecen una visión general de las facturas para el proveedor seleccionado. Puede visualizar facturas por su estado.
-   Las facturas de borrador no se han enviado al flujo de trabajo.
-   Las facturas enviadas no aprobadas son aquellas facturas que el proveedor ha enviado pero que no se han registrado en Dynamics 365 for Operations.
-   Las facturas aprobadas no pagadas son aquellas facturas que el proveedor ha registrado en Dynamics 365 for Operations pero que todavía no se han pagado por completo.
-   Las facturas pagadas son aquellas que se han pagado por completo en Dynamics 365 for Operations.

Si hace clic en una ficha, abrirá una vista filtrada de la página **Lista de facturas**.
### <a name="tabular-lists"></a>Listas tabulares

En la sección **Listas tabulares**, el estado de la facturación se desglosa de forma similar a las fichas del resumen: Borrador y Enviado, listas no aprobadas. Cuando se encuentre en estado de Borrador, una factura se puede enviar al flujo de trabajo o eliminarse. La última lista tabular es una opción para buscar facturas. Puede filtrar según busca para permitir búsquedas más rápidas.
Página de la lista de todas las facturas de proveedor
-----------------------------

Puede ver todas las facturas de proveedor registradas y sin registrar en la página de la lista de **Facturas de colaboración de proveedore**. Puede usar dicha página para ver el estado del pago de las facturas. Los estados del pago incluyen No registradas, Sin pagar, Pagadas parcialemente y Pagadas completamente.
Crear una nueva factura a partir de un pedido de compra
--------------------------------------------

Puede crear una nueva factura de proveedor seleccionando la acción **Nueva** en el espacio de trabajo de **Facturación de colaboración de proveedor**. El proveedor debe proporcionar el número de pedido de compra y de factura. De forma predeterminada, todas las líneas de pedido de compra del proveedor aparecerán en la nueva factura. La información sobre cantidad y coste se puede editar antes de enviar la factura de proveedor al flujo de trabajo. Puede adjuntar archivos, notas, imágenes y direcciones URL a una factura antes de enviarla.



Para obtener más información, consulte [Colaboración con los proveedores mediante el portal de proveedores](/dynamics365/operations/supply-chain/procurement/collaborate-vendors-vendor-portal)




