---
title: "Usar catálogos externos para la adquisición electrónica de marcaje de salida"
description: "Este tema explica cómo puede usar catálogos externos para crear y enviar solicitudes."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable, PurchVendorPortalRequests
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 035c5d15e5508c78dd66a349defd534bfecc96bb
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="use-external-catalogs-for-punchout-eprocurement"></a>Usar catálogos externos para la adquisición electrónica de marcaje de salida
Mediante los catálogos externos para la adquisición electrónica de marcaje de salida, no tiene que mantener información sobre los productos de los proveedores en sus propios datos maestros. En su lugar, el carro de la compra en la página web de un proveedor se convierte en las líneas de la solicitud con la información correcta de producto. 

Debe evitar mantener las descripciones y los precios de los productos de los proveedores en sus propios datos de producto maestro. Es mejor usar catálogos externos para la adquisición electrónica de marcaje de salida. A continuación, cuando los empleados creen solicitudes, pueden consultar el sitio del catálogo externo del proveedor (es decir, salir del sistema y dirigirse al sitio del proveedor). Los productos que se agregan al carro de la compra en la página web del proveedor se pueden convertir a continuación en líneas de solicitud. Por lo tanto, se recopila la información de producto correcta: identificador, nombre, precio y demás datos del producto.

Para usar catálogos externos, un empleado debe crear una solicitud en la página **Mis solicitudes de compra** .

El empleado que crea una solicitud se conoce como preparador de la solicitud. Como preparador, puede realizar las tareas siguientes.

Use la acción de línea **Catálogos externos** para abrir una página que incluya todos los catálogos externos disponibles para el solicitante especificado, la entidad jurídica compradora y la unidad operativa receptora.

Dependiendo de sus permisos, cambie el solicitante, la entidad jurídica compradora y la unidad operativa receptora. Un cambio en estos valores puede cambiar la lista de catálogos externos disponibles para un solicitante. Los catálogos externos disponibles dependen de las directivas de compra del activo actual para la entidad jurídica compradora o la unidad operativa receptora. Estas directivas pueden permitir o impedir el acceso a categorías de compras específicas. Por lo tanto, la lista de catálogos externos que se asignen a estas categorías de compras puede verse afectada.

Para obtener más información sobre directivas, vea [Directivas de compra](../procurement/purchase-policies.md).

- Para obtener los catálogos externos para categorías de compras específicas, escriba el texto en el campo de búsqueda de catálogos.
- Para agregar productos de un catálogo externo de un proveedor en la página web, haga clic en el catálogo externo. A continuación, agregue los productos al carro de la compra y confirme la compra. Las líneas del carro de la compra se transferirán a Microsoft Dynamics 365.

Si existen varias opciones para categorías de compras, seleccione la categoría de compras correcta antes de agregar líneas a la solicitud.
Una vez las líneas se hayan agregado a una solicitud, puede agregar más líneas sin usar catálogos externos. Como alternativa, puede continuar utilizando catálogos externos para agregar líneas.

Cuando la solicitud esté lista, use la acción **Flujo de trabajo** > **Enviar** para enviarla para su aprobación.

