---
title: Gestión de inventario en tienda
description: En este tema se describen los tipos de documentos que puede usar para gestionar el inventario.
author: rubencdelgado
manager: AnnBe
ms.date: 05/15/2020
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
ms.openlocfilehash: a3e6450c358d12dc62c2ffa20e7ff529be86bbe5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415549"
---
# <a name="store-inventory-management"></a>Gestión de inventario en tienda

[!include [banner](includes/banner.md)]

Cuando trabaja con inventario en Microsoft Dynamics 365 Commerce y usa la aplicación de punto de venta (PDV), es importante que tenga en cuenta que PDV proporciona soporte limitado para algunas dimensiones de inventario y algunos tipos de artículos de inventario. La aplicación PDV no admite la gama completa de capacidades de configuración de artículos que está disponible a través de las opciones de configuración de elementos en Dynamics 365 Supply Chain Management.

La solución POS actualmente no admite las siguientes dimensiones de productos ni configuraciones de artículo:

- Artículos de configuración de elementos de dimensión de producto y de lista de materiales (BOM) (excepto productos de kit de venta minorista, que utilizan algunos componentes del marco de BOM)
- Artículos con peso capturado
- Artículos de versión controlados por dimensiones del producto

La aplicación PDV no admite actualmente las dimensiones de seguimiento siguientes en el PDV:

- Dimensión de seguimiento por lotes
- Dimensión de propietario

PDV ofrece compatibilidad limitada para las dimensiones siguientes. En otras palabras PDV puede introducir automáticamente algunas de estas dimensiones en transacciones de inventario, según la configuración del almacén o la tienda. PDV no admitirá completamente las dimensiones de la manera en que se contemplan si una transacción de ventas se introduce manualmente en la Central de Commerce. 

- **Ubicación del almacén**: cuando usan las nuevas operaciones de PDV [Operación entrante](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) y [Operación saliente](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation), los usuarios pueden seleccionar una ubicación de inventario de almacén para recibir artículos o enviar artículos de pedido de transferencia al exterior. Si usan la operación obsoleta **Recogida y recepción**, el soporte de gestión de ubicación limitada está disponible para recibir y enviar transferencias salientes. Este soporte solo está disponible si la opción **Usar el proceso de gestión de almacén** se ha activado para el artículo y el almacén de la tienda. Actualmente no se puede usar una ubicación de inventario con la operación **Recuento de existencias** ni con la operación **Búsqueda de inventario**.
- **Matrícula**: las matrículas solo se aplican cuando se ha habilitado la opción **Usar proceso de gestión de almacén** para el artículo y el almacén de la tienda. En PDV, si el inventario se recibe en el almacén de una tienda utilizando la operación **Operación entrante** o la operación **Recoger y recibir** donde se ha activado el proceso de gestión de almacén, y si la ubicación que se ha seleccionado para recibir el artículo está vinculada a un perfil de ubicación que requiere control de matrícula, la aplicación POS aplica sistemáticamente una matrícula a la línea de recepción. Los usuarios de PDV no pueden cambiar ni administrar estos datos de matrícula. Si es necesaria la administración completa de matrículas, se recomienda que la tienda use la [aplicación de almacenameinto](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/install-configure-warehousing-app) o el cliente administrativo para administrar la recepción de estos elementos.
- **Número de serie**: la aplicación PDV ofrece compatibilidad limitada para el registro de un único número de serie en una línea de transacción para los pedidos creados en PDV que incluyan artículos serializados. Este número de serie no se valida frente a los números de serie registrados que ya están en el inventario. Si un pedido de ventas se crea en el canal de centro de asistencia telefónica o se cumplimenta a través de planificación de recursos de empresa (ERP) y varios números de serie se registran en una sola línea de ventas durante el proceso de cumplimentación en ERP, dichos números de serie no se pueden aplicar ni validarse si una devolución se procesa para el pedido en PDV. Cuando se recibe inventario utilizando la operación **Operación entrante**, los usuarios pueden [registrarse o confirmar los números de serie recibidos](https://docs.microsoft.com/dynamics365/commerce/pos-serialized-items).
- **Estado de inventario**: para artículos que usan el proceso de la gestión de almacén y requieren un estado de inventario, este campo de estado no se puede establecer ni modificar con la aplicación PDV. Se usa el estado de inventario predeterminado que se define en la configuración del almacén de tienda cuando los artículos se reciben en inventario.

> [!NOTE]
> Todas las organizaciones deben probar las configuraciones de artículos a través de PDV en entornos de desarrollo o de prueba antes de implementar dichas configuraciones de artículos en entornos de producción. Pruebe los artículos usándolos para realizar transacciones de ventas al contado y crear pedidos de cliente (si procede) través de PDV. También debe probar el cumplimiento de PDV y los procesos de inventario (como la recepción de inventario y las operaciones de cumplimentación de pedidos) antes de implementar cualquier nueva configuración de artículos, para asegurarse de que la aplicación PDV pueda admitirlos. Las pruebas deben incluir la ejecución de un proceso completo de contabilización de entradas en su entorno de prueba y verificar que no ocurran problemas cuando se crean y publican pedidos de estos artículos en la Central de Commerce.
>
> Si los elementos se configuran de una manera que la aplicación PDV no admite, y no se realizan las pruebas adecuadas, pueden ocurrir errores en los datos que no se corrigen fácilmente o que no se cubren a través del soporte estándar del producto durante el proceso de creación de pedidos.

## <a name="purchase-orders"></a>Pedidos de compra

Los pedidos de compra se crean en la Central de Commerce. Si se incluye un almacén comercial en el encabezado del pedido de compra o en las líneas del pedido de compra, las líneas pueden recibirse en la tienda usando la operación [Operación entrante](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) en PDV. 

## <a name="transfer-orders"></a>Pedidos de transferencia

Los pedidos de transferencia se pueden crear en la Central deCommerce o a través de [Operación entrante](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) u [Operación saliente](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation) en PDV. Utilice la operación PDV **Operación entrante** para crear una solicitud de pedido de transferencia para que se envíe el inventario a la tienda desde otro almacén o ubicación de la tienda. Utilice la operación PDV **Operación saliente** para crear una solicitud de pedido de transferencia para que se envíe el inventario desde la tienda desde otra ubicación de almacén o tienda. Después de crear una orden de transferencia para una tienda, esa tienda puede gestionar la recepción del inventario para la orden de transferencia a través de la operación **Operación entrante** en PDV. Si la tienda está enviando inventario a otra ubicación, la operación **Operación saliente** en PDV se utiliza para administrar el proceso de envío saliente de esa tienda.

## <a name="stock-counts"></a>Recuentos de existencias

Los recuentos de existencias se pueden programar o no. Los recuentos de existencias programados se crean a través de la Sede de Commerce al crear un documento de diario de conteo que está vinculado al almacén de la tienda. Este diario especifica los elementos que deben contarse. Luego, la tienda puede acceder a estos diarios de cuentas predefinidos y actuar sobre ellos utilizando la operación **Recuento de existencias** en PDV. Los usuarios de la tienda inician un recuento de existencias no programado, ya que es necesario cuando utilizan la operación **Recuento de existencias** en PDV. A diferencia de los recuentos programados de existencias, los recuentos no programados de existencias no tienen una lista predefinida de artículos. Cuando finaliza un recuento de existencias de cualquier tipo en PDV, se compromete y se envía a la oficina central. En la oficina central, el recuento debe validarse y publicarse en la Central de Commerce como paso separado.

## <a name="inventory-lookup"></a>Búsqueda de inventario

La cantidad de producto disponible actualmente para múltiples tiendas y almacenes se puede ver en la página **Consulta de inventario**. Además de la cantidad disponible actual, las cantidades futuras de neto no comprometido (NNC) se pueden visualizar para cada tienda. Seleccione la tienda para ver las cantidades NNC y, a continuación, seleccione **Mostrar disponibilidad en tienda**. Para obtener información sobre las opciones de configuración disponibles, consulte [Calcular la disponibilidad de inventario para canales minoristas](https://docs.microsoft.com/dynamics365/commerce/calculated-inventory-retail-channels).


[!INCLUDE[footer-include](../includes/footer-banner.md)]