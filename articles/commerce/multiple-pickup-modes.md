---
title: Habilitar varios modos de recogida de la entrega para pedidos de clientes
description: Este artículo explica la funcionalidad de Microsoft Dynamics 365 Commerce que le permite crear pedidos de clientes para recoger en una tienda.
author: hhainesms
ms.date: 12/06/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: e4d8883b3dc1c4a0e12bcb00b6441f76d73da92e
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2022
ms.locfileid: "9831594"
---
# <a name="enable-multiple-pickup-delivery-modes-for-customer-orders"></a>Habilitar varios modos de recogida de la entrega para pedidos de clientes

[!include [banner](includes/banner.md)]


En Microsoft Dynamics 365 Commerce, las organizaciones pueden definir múltiples modos de entrega entre los que los compradores o asociados de ventas pueden elegir cuando crean un pedido que se recogerá en una tienda. De esta manera, las organizaciones pueden brindar múltiples opciones de recolección a sus compradores. Por ejemplo, muchos minoristas ahora ofrecen a los compradores la opción de recoger sus pedidos en la tienda o en un punto de entrega. Commerce admite la configuración de estos diferentes modos de recogida de la entrega. Los usuarios pueden aprovecharlos cuando crean pedidos de clientes en cualquier canal de Commerce compatible (comercio electrónico, centro de llamadas o tienda).

## <a name="enable-and-configure-pickup-delivery-modes"></a>Habilitar y configurar varios modos de recogida de la entrega

La característica **Compatibilidad para múltiples modos de recogida de la entrega** en el espacio de trabajo **Administración de características** en Commerce Headquarters se ha convertido en obligatoria y se debe habilitar en el entorno.

Si definió anteriormente un modo de entrega con retiro en la página **Parámetros de comercio**, ese modo aparece en la configuración actual para los modos de entrega con retiro.

![Modos de recogida de la entrega en la página de parámetros de Commerce.](media/multiplepickupparameter.png)

Puede definir varios modos de entrega de recogida en la cuadrícula **Modo de entrega de recogida** en **Parámetros de Commerce** >  pestaña **Pedidos de clientes** > ficha desplegable **Modos de entrega**.  

Los campos **Modo de realización de la entrega** y **Modo electrónico de entrega** y la opción **Mostrar solo opciones con transportista para pedidos de envío**, se han reubicado en esta ficha desplegable.

Antes de configurara modos de recogida de la entrega adicionales, debe definir los modos de entrega. En la página **Modos de entrega** en la sede central de Comercio, agregue los modos de entrega que deben considerarse modos de recogida de la entrega. Asegúrese de que toda la configuración esté completada. Por ejemplo, si ofrece la recogida en un punto de entrega como una opción de entrega para sus compradores en línea en determinadas tiendas, debe crear un nuevo modo de entrega para este fin. Puede crear este modo de entrega utilizando "recogida en punto de entrega" como descripción. Luego, asegúrese de que el modo de entrega de "recogida en punto de entrega" se asigne a todos los canales de Commerce que pueden ofrecerlo, incluidas las tiendas en línea que pueden ofrecer esta opción y los canales de la tienda individual que ofrecerán este método de entrega. Los modos de entrega también deben estar vinculados a los productos. En este ejemplo, si hay ciertos productos que no se pueden entregar con la "recogida en punto de entrega", debe asegurarse de que esos artículos estén excluidos. Cuando haya terminado de añadir los nuevos modos de entrega, ejecute el trabajo **Procesar modos de entrega** para crear las relaciones entre el modo de entrega, los canales y los artículos. Cuando haya terminado el trabajo, abra la página **Programa de distribución** en la sede central de Commerce y ejecute el trabajo de distribución **1120** para garantizar que las bases de datos relevantes del canal de Commerce se actualicen con su nueva configuración de modo de entrega.

![Ejemplo de configuración de modo de entrega para recogida en un punto de entrega.](media/pickupmodes.png)

Después de definir los modos de recogida de la entrega adicionales, agréguelos a la cuadrícula **Modo de recogida de la entrega** en la página **Parámetros de Commerce**. Luego, ejecute los trabajos de distribución adecuados para actualizar las bases de datos del canal de Commerce relevantes con el cambio de configuración.

> [!NOTE]
> Aparte del modo de entrega de recogida existente que se copia en la cuadrícula **Modo de recogida de la entrega** cuando activa la característica **Compatibilidad para múltiples modos de recogida de la entrega**, para cada configuración de modo de entrega de recogida adicional que cree, debe configurar nuevos modos de entrega. Cuando agrega modos de entrega a la cuadrícula **Modo de recogida de la entrega**, Commerce valida si alguna línea de ventas abierta activa ya los usa. Si se encuentran líneas de venta abiertas, recibirá un mensaje de error. Los modos de entrega no se consideran modos de recogida de la entrega hasta que se hayan cerrado todas las líneas de venta abiertas que los utilizan (ya sea facturadas o canceladas).


### <a name="e-commerce-site-configurations"></a>Configuraciones del sitio de comercio electrónico

Cuando la característica **Soporte para múltiples modos de recogida de la entrega** está activada, los siguientes módulos en las páginas de comercio electrónico muestran los nuevos modos de recogida de la entrega tal como están configurados:

- Cuadro de compra
- Selector de tienda
- Carro
- Información de recogida
- Confirmación de pedido
- Detalles del pedido

No se requieren pasos adicionales en las páginas de comercio electrónico para que los modos de recogida de la entrega estén disponibles.

## <a name="work-with-multiple-pickup-delivery-modes"></a>Trabajar con varios modos de recogida de la entrega

Cuando hay varios modos de recogida de la entrega disponibles para un canal, se proporciona una experiencia mejorada a los clientes cuando compran productos que se recogerán. 

- En los canales de comercio electrónico, los compradores pueden seleccionar cualquier modo de entrega de recogida válido que esté disponible. Por ejemplo, un minorista define dos modos de recogida de la entrega (recogida en la tienda y recogida en un punto de entrega), ambos están configurados en la cuadrícula **Modo de recogida de la entrega** y ambos son válidos para el canal de cumplimiento de pedidos y el producto que un comprador está comprando actualmente. En este caso, el comprador puede seleccionar su modo de recogida de la entrega preferido. El modo de recogida de la entrega seleccionado se convierte en el modo de entrega que está vinculado a la línea de orden de venta cuando se crea la orden en la sede de Commerce.

    ![Seleccionar una opción de recogida en el comercio electrónico.](media/pickupecommerce.png)

- En los canales de la tienda, si se crea un pedido de recogida de un cliente a través de la aplicación de punto de venta (POS), se solicita al asociado de ventas que elija entre los modos de entrega de recogida disponibles, si se ha configurado alguno. Si solo hay disponible un modo de recogida de la entrega válido para el canal y el artículo, no se le solicita al asociado de ventas que lo seleccione. En cambio, el modo de recogida de la entrega disponible se aplica automáticamente a las líneas de pedido.

    ![Seleccionar una opción de recogida en la aplicación del PDV.](media/pickuppos.png)

- En los canales del centro de llamadas, cuando los usuarios crean pedidos de recogida, pueden seleccionar manualmente cualquier modo de recogida de la entrega definido que esté vinculado al canal del centro de llamadas. Luego, el sistema valida que el modo de recogida de la entrega seleccionado se puede usar cuando se pide el artículo que se está vinculando a él. Cuando se selecciona un modo de recogida de la entrega en los canales del centro de llamadas, las líneas del pedido ventas deben estar vinculadas a un almacén de tienda válido. Si se define un almacén fuera de la tienda en una línea de ventas del centro de llamadas, no se puede establecer un modo de recogida de la entrega en esa línea de ventas.
- Los asociados de ventas pueden utilizar la opción **Recuperación de pedidos** o **Cumplimiento de pedido** en la aplicación del PDV para recuperar una lista de pedidos o líneas de pedido para recoger. Si un asociado de ventas utiliza un filtro de búsqueda predefinido para mostrar todos los pedidos que se recogerán en la tienda actual, las consultas se modifican para garantizar que los resultados de la búsqueda incluyan todos los pedidos elegibles que utilicen cualquier modo de recogida de la entrega. Los usuarios de PDV también pueden usar los filtros existentes para reducir la lista de pedidos a un modo de recogida de la entrega específico. Por ejemplo, solo pueden mostrar pedidos para recoger en un punto de entrega.

    ![Filtro para modos de recogida de la entrega aplicados a una lista de pedidos recuperados.](media/pickuprecallorder.png)

## <a name="considerations-for-distributed-order-management"></a>Consideraciones para la gestión de pedidos distribuida

La característica [gestión de pedidos distribuida (DOM)](./dom.md) de Commerce ignoran las líneas de venta que están marcadas para la recogida en tienda. Estas características se han actualizado para garantizar que las líneas de ventas que están vinculadas a los modos de recogida de la entrega configurados omitan la lógica DOM y no se reasignen a un nuevo almacén de cumplimiento.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
