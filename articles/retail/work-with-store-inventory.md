---
title: Gestión de inventario en tienda
description: En este tema se describen los tipos de documentos que puede usar para gestionar el inventario.
author: rubencdelgado
manager: AnnBe
ms.date: 01/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 21391
ms.assetid: bfef3717-d0e0-491d-8466-d8a9c995177d
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 02f8afbe3bb6f94c66a8b5aa02531c219adc3963
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "339243"
---
# <a name="store-inventory-management"></a>Gestión de inventario en tienda

[!include [banner](includes/banner.md)]

En este tema se describen los tipos de documentos que puede usar para gestionar el inventario.

Puede utilizar los siguientes tipos de documentos para gestionar el inventario de la organización.

Al trabajar con el inventario en Dynamics 365 for Retail y con la aplicación de PDV, es importante tener en cuenta que PDV ofrece compatibilidad limitada para las dimensiones de inventario y algunos tipos de artículos de inventario.  

La solución de PDV no admite configuraciones del artículo siguiente:
- Elementos de MAT (excepto los productos de kit, que se usan algunos componentes del marco de MAT)
- Artículos con peso capturado
- Artículos controlados por lote

La aplicación de PDV no admite actualmente las dimensiones de seguimiento siguientes en el PDV:
- Dimensión de seguimiento por lotes
- Dimensión de propietario

La solución de PDV ofrece compatibilidad limitada para las dimensiones siguientes. La compatibilidad limitada indica que el PDV puede establecer como valor predeterminado algunas de estas dimensiones en transacciones de inventario basadas automáticamente en la configuración del almacén o la tienda. PDV no será totalmente compatible con las dimensiones de la manera en que se admiten si una transacción de ventas se introduce manualmente en el ERP. 

- Ubicación
- Placa (solo aplicable cuando se ha habilitado **Usar proceso de gestión de almacenes** en el artículo y el almacén de la tienda)
- Número de serie
- Estado de inventario

> [!NOTE]
> Todas las organizaciones deben probar las configuraciones de artículo con PDV en entornos de desarrollo o de prueba antes de implementarlos para la producción. Pruebe los artículos realizando transacciones de ventas al contacto habituales de tiendas y creando pedidos de cliente (si procede) con PDV con sus artículos. La prueba debe incluir la ejecución de procesos de registro de extractos completos en el entorno de prueba y la verificación de que no hay problemas.
> La configuración de artículos de forma que no sea compatible con la aplicación del PDV, sin realizar una prueba adecuada, puede resultar en un proceso de registro de extractos en que se produce un error en la producción sin una forma sencilla de corregir los problemas. Las personalizaciones del socio o del cliente en la aplicación pueden considerarse opcionalmente para permitir que estos procesos de registro se completen correctamente. Si las personalizaciones no son necesarias, la organización debe garantizar que la configuración de sus productos se haya efectuado de forma que sea compatible con el proceso de registro estándar de la aplicación de PDV, la creación de pedidos o del extracto.

## <a name="purchase-orders"></a>Pedidos de compra

Los pedidos de compra se crean en la oficina central. Si se incluye un almacén comercial en el encabezado del pedido de compra, el pedido se puede recibir en la tienda mediante Modern POS (MPOS) o Cloud POS en Microsoft Dynamics 365 for Retail. Después de especificar las cantidades que se reciben en la tienda, se pueden guardar de manera local para realizar otras modificaciones. Otra opción es que las cantidades se comprometan y se envíen a la oficina central. En la oficina central, las cantidades que se han recibido en la tienda se muestran en Dynamics 365 for Retail, en el campo **Recibir ahora** del pedido de compra.

## <a name="transfer-orders"></a>Pedidos de transferencia

Un pedido de transferencia puede especificar que una tienda concreta es una ubicación desde la que se pueden enviar artículos. En este caso, el pedido de transferencia aparece en la tienda como una solicitud de selección en MPOS o PDV en la nube. Después de seleccionar las cantidades solicitadas, se comprometen y se envían a la oficina central. En la oficina central, las cantidades seleccionadas en la tienda se muestran en Dynamics 365 for Retail, en el campo **Enviar ahora** del pedido de transferencia. Un pedido de transferencia puede especificar que una tienda concreta es una ubicación a la que se pueden enviar artículos. En este caso, el pedido de transferencia aparece en la tienda como una solicitud de recepción en MPOS o PDV en la nube. Después de especificar las cantidades que se reciben en la tienda, se pueden guardar de manera local para realizar otras modificaciones. Otra opción es que las cantidades se comprometan y se envíen a la oficina central. En la oficina central, las cantidades que se han recibido en la tienda se muestran en Dynamics 365 for Retail, en el campo **Recibir ahora** del pedido de transferencia.

## <a name="stock-counts"></a>Recuentos de existencias

Los recuentos de existencias se pueden programar o no. Los recuentos de existencias programados se inician en la oficina central, que especifica los artículos que se deben contar. La oficina central crea un documento que se puede recibir en la tienda, donde se especifican las cantidades de existencias disponibles reales en MPOS o PDV en la nube. Los recuentos de existencias no programados se inician en una tienda y las cantidades de existencias disponibles se actualizan en MPOS o PDV en la nube. A diferencia de los recuentos programados de existencias, los recuentos no programados de existencias no tienen una lista predefinida de artículos. Cuando finaliza un recuento de existencias de cualquier tipo, se compromete y se envía a la oficina central. En la oficina central, se valida y se registra el recuento.

## <a name="inventory-lookup"></a>Búsqueda de inventario

La cantidad de producto disponible actualmente para múltiples tiendas y almacenes se puede ver en la página de consulta de inventario. Además de la cantidad disponible actual, las cantidades futuras de neto no comprometido (NNC) se pueden visualizar para cada tienda. Para ello, seleccione la tienda para la que desea ver el NNC y después para haga clic en **Mostrar disponibilidad en tienda**.
