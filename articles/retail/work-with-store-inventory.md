---
title: Gestión de inventario en tienda
description: En este tema se describen los tipos de documentos que puede usar para gestionar el inventario.
author: rubencdelgado
manager: AnnBe
ms.date: 04/23/2019
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
ms.openlocfilehash: c5da94e02b2381bbd058221567172cd428931c45
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2019
ms.locfileid: "2024692"
---
# <a name="store-inventory-management"></a>Gestión de inventario en tienda

[!include [banner](includes/banner.md)]

Al trabajar con el inventario en Dynamics 365 Retail y con la aplicación de PDV, es importante tener en cuenta que PDV ofrece compatibilidad limitada para las dimensiones de inventario y algunos tipos de artículos de inventario.

La solución de PDV no admite configuraciones del artículo siguiente:

- Elementos de MAT (excepto los productos de kit, que se usan algunos componentes del marco de MAT)
- Artículos con peso capturado
- Artículos controlados por lote

La aplicación de PDV no admite actualmente las dimensiones de seguimiento siguientes en el PDV:

- Dimensión de seguimiento por lotes
- Dimensión de propietario

La solución de PDV ofrece compatibilidad limitada para las dimensiones siguientes. La compatibilidad limitada indica que el PDV puede establecer como valor predeterminado algunas de estas dimensiones en transacciones de inventario basadas automáticamente en la configuración del almacén o la tienda. PDV no será totalmente compatible con las dimensiones de la manera en que se admiten si una transacción de ventas se introduce manualmente en el ERP. 

- **Ubicación de almacén** - Los usuarios no tendrán la capacidad de administrar la ubicación del almacén de recepción de los artículos recibidos en un almacén cuando la tienda no haya sido configurada para usar el proceso de gestión de almacenes. Una ubicación de recepción predeterminada definida en el almacén de tienda se usará para estos artículos. Si el proceso de gestión de almacenes se ha habilitado para el almacén, la compatibilidad limitada que solicita al usuario seleccionar una ubicación de recepción de la recepción completo se activará. Los artículos vendidos del almacén siempre se venderán fuera de la ubicación minorista predeterminada como se definió en la configuración del almacén de tienda. La ubicación para gestionar la devolución de inventario se puede controlar con la definición de la ubicación de devolución predeterminada en el almacén de tienda o basarse en códigos de motivo de devolución como se define en la directiva de devolución de la ubicación.
- **Matrícula de entidad de almacén** - Las matrículas de entidad de almacén solo se aplican cuando se ha habilitado **Usar proceso de gestión de almacenes** en el artículo y el almacén de la tienda. En PDV, si el inventario se recibe en un almacén de tienda donde se ha habilitado el proceso de gestión de almacenes y la ubicación elegida para recibir el artículo está vinculada a un perfil de ubicación que requiere el control de la matrícula de entidad de almacén, la aplicación de PDV aplicará sistemáticamente una matrícula de entidad de almacén a la línea de recepción. Los usuarios de PDV no tendrán la capacidad de cambiar o de administrar estos datos del número de matrícula de entidad de almacén. Si la administración completa de matrícula de entidad de almacén es necesaria, se sugiere el uso de la tienda la aplicación móvil de WMS o el área de operaciones del cliente de ERP para administrar la recepción de estos elementos.
- **Número de serie** - La aplicación de PDV tiene compatibilidad limitada para que solo un número de serie se registre en una línea de ventas de transacción para los pedidos creadas en el sistema PDV con los artículos serializados. Este número de serie no se valida contra los números de serie ya registrados en el inventario. Si un pedido de ventas se crea en el canal de centro de asistencia telefónica o satisfecho a través de ERP y varios números de serie se registran a una sola línea de ventas durante el proceso de cumplimiento en el ERP, estos números de serie no se podrán aplicar o validarse si una devolución se procesa en el sistema PDV para estos pedidos.
- **Estado de inventario** - Para artículos que usan el proceso de la gestión de almacenes y requieren un estado de inventario, este campo de estado no se puede establecer o modificarse con la aplicación de PDV. Utilizará el estado de inventario predeterminado que se define en la configuración del almacén de tienda cuando los artículos se reciben en inventario.

> [!NOTE]
> Todas las organizaciones deben probar las configuraciones de artículo con PDV en entornos de desarrollo o de prueba antes de implementarlos para la producción. Pruebe los artículos realizando transacciones de ventas al contacto habituales de tiendas y creando pedidos de cliente (si procede) con PDV con sus artículos. La prueba debe incluir la ejecución de procesos de registro de extractos completos en el entorno de prueba y la verificación de que no hay problemas.
>
> La configuración de artículos de forma que no sea compatible con la aplicación del PDV, sin realizar una prueba adecuada, puede resultar en un proceso de registro de extractos en que se produce un error en la producción sin una forma sencilla de corregir los problemas. Las personalizaciones del socio o del cliente en la aplicación pueden considerarse opcionalmente para permitir que estos procesos de registro se completen correctamente. Si las personalizaciones no son necesarias, la organización debe garantizar que la configuración de sus productos se haya efectuado de forma que sea compatible con el proceso de registro estándar de la aplicación de PDV, la creación de pedidos o del extracto.

## <a name="purchase-orders"></a>Pedidos de compra

Los pedidos de compra se crean en la oficina central. Si se incluye un almacén comercial en el encabezado del pedido de compra, el pedido se puede recibir en la tienda mediante Modern POS (MPOS) o Cloud POS a través de la operación **Recogida/Recepción**. Después de las cantidades que se reciban en el almacén se introduzcan en el campo **Recibir ahora** en el PDV para el documento de pedido de compra, éstos se puede guardar o localmente se compromete. Guardar estos datos localmente no tiene ningún efecto en inventario en existencias. El guardado solo se debe hacer si el usuario no está listo para enviar la recepción a la Sede y necesita una forma de almacenar los datos temporalmente especificados anteriormente **Recibir ahora** . Esto guarda los datos de recibido ahora localmente en la base de datos de canal del usuario. Una vez que el documento se procese mediante la opción **Confirmación**, los datos **Recibir ahora** se envían a la Sede y la recepción de pedido de compra se registrará. 

## <a name="transfer-orders"></a>Pedidos de transferencia

Un pedido de transferencia puede especificar que un almacén específico es la ubicación a la que los artículos se pueden enviar o la ubicación donde se recibirá el inventario. Si el usuario PDV es el almacén de envío para un pedido de transferencia, podrán especificar las cantidades **Enviar ahora** de PDV. Los datos que especifique el almacén de envío pueden guardarse localmente o confirmarse. Cuando se guardan localmente, no se realizan actualizaciones del documento de pedido de transferencia en la Sede. El guardado solo se debe hacer si el usuario no está listo para enviar el envío a la Sede y necesita una forma de almacenar los datos temporalmente especificados anteriormente en **Enviar ahora** . Una vez que el almacén esté listo para confirmar el envío, la opción **Confirmación** debe seleccionarse. Esto envía la entrega del pedido de transferencia en la Sede de modo que el almacén de recepción pueda recibirlo contra él. 

Si el usuario PDV es el almacén receptor para un pedido de transferencia, podrán especificar las cantidades **Recibir ahora** de PDV. Los datos que especifique el almacén de recepción pueden guardarse localmente o confirmarse. El guardado solo se debe hacer si el usuario no está listo para enviar la recepción a la Sede y necesita una forma de almacenar los datos temporalmente especificados anteriormente **Recibir ahora** . Esto guarda los datos de recibido ahora localmente en la base de datos de canal del usuario. Una vez que el documento se procese mediante la opción **Confirmación**, los datos **Recibir ahora** se envían a la Sede y la transferencia de pedido de compra se registrará. Es importante tener en cuenta que la tienda receptora sólo se limita a poder confirmar si recibe las cantidades iguales o menores a las enviadas. Intentar recibir las cantidades en un pedido de transferencia que no se han registrado previamente generará errores y la recepción no será confirmado en la Sede.

## <a name="stock-counts"></a>Recuentos de existencias

Los recuentos de existencias se pueden programar o no. Los recuentos de existencias programados se inician en la oficina central, que especifica los artículos que se deben contar. La oficina central crea un documento que se puede recibir en la tienda, donde se especifican las cantidades de existencias disponibles reales en MPOS o PDV en la nube. Los recuentos de existencias no programados se inician en una tienda y las cantidades de existencias disponibles se actualizan en MPOS o PDV en la nube. A diferencia de los recuentos programados de existencias, los recuentos no programados de existencias no tienen una lista predefinida de artículos. Cuando finaliza un recuento de existencias de cualquier tipo, se compromete y se envía a la oficina central. En la oficina central, se valida y se registra el recuento como un paso aparte.

## <a name="inventory-lookup"></a>Búsqueda de inventario

La cantidad de producto disponible actualmente para múltiples tiendas y almacenes se puede ver en la página de **Consulta de inventario**. Además de la cantidad disponible actual, las cantidades futuras de neto no comprometido (NNC) se pueden visualizar para cada tienda. Para ello, seleccione la tienda para la que desea ver el NNC y después para haga clic en **Mostrar disponibilidad en tienda**.
