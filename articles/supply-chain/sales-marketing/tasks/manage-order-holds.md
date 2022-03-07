---
title: Gestionar retenciones de pedidos
description: Este procedimiento demuestra cómo poner en espera los pedidos de ventas del cliente, cómo trabajar con retenciones de pedidos desprotegidas y cómo quitar retenciones de pedido.
author: omulvad
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MCRHoldCodeTable, SalesTableListPage, SalesCreateOrder, SalesTable, MCRHoldCodeTrans, MCRHoldCheckOutOverride, MCRHoldCodeTable, MCRItemListCopying, MCRItemListTable, MCROMHoldList
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4e9c91061b82b8e172d8b93e9b255d0c9f400b5b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254998"
---
# <a name="manage-order-holds"></a>Gestionar retenciones de pedidos

[!include [banner](../../includes/banner.md)]

Este procedimiento demuestra cómo poner en espera los pedidos de ventas del cliente, cómo trabajar con retenciones de pedidos desprotegidas y cómo quitar retenciones de pedido. Un pedido se puede retener por una variedad de motivos. Por ejemplo, puede retener un pedido hasta que la dirección o el método de pago de un cliente se pueda comprobar o hasta que un director pueda revisar el límite de crédito del cliente. Mientras el pedido se encuentra en espera, el almacén no se puede procesar para su envío. 

Puede ejecutar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos.


## <a name="set-up-order-holds"></a>Configuración de retenciones de pedidos
1. Vaya a **Panel de navegación > Módulos > Ventas y marketing > Configuración > Pedidos de ventas > Códigos de retención de pedidos**.
2. Haga clic en **Nuevo**.
3. En el campo **Código de retención**, escriba un valor. Por ejemplo, tipo "Volver a llamar".  
4. En el campo **Descripción**, escriba un valor.
    - Por ejemplo, el Pedido se encuentra retenido en espera de devolución de llamada del cliente.  
    - De manera opcional, seleccione la casilla **Quitar reservas** para eliminar las reservas físicas del pedido cuando se agrega este código de retención.  
5. Haga clic en **Guardar**.

## <a name="place-order-on-hold"></a>Retenga el pedido
1. Vaya a **Panel de navegación > Módulos > Ventas y marketing > Pedidos de ventas > Todos los pedidos de ventas**.
2. Haga clic en **Nuevo**.
3. En el campo **Cuenta de cliente**, especifique o seleccione un valor.
4. Haga clic en **Aceptar**.
5. En el campo **Número de artículo**, especifique o seleccione un valor.
6. En el campo **Cantidad**, especifique un número.
7. En el **panel de acciones**, haga clic en **Pedido de ventas**.
8. Haga clic en **Retenciones de pedido**.
9. Haga clic en **Nuevo**.
10. En el campo **Código de retención**, seleccione el código que ha creado en la subtarea anterior.
11. Haga clic en **Guardar**.
12. Cierre la página.
13. Vaya a **Ventas y marketing > Pedidos de ventas > Todos los pedidos de ventas**.
14. En la lista, marque la fila seleccionada. Los pedidos que están actualmente en espera tienen marcados los campos "No procesar" y "En espera".
15. En el panel de acciones, haga clic en **Seleccionar y empaquetar**.

## <a name="manage-order-holds"></a>Gestionar retenciones de pedidos
1. Vaya a **Ventas y marketing > Pedidos de ventas > Pedidos abiertos > Retenciones de pedido**. La página de **retenciones de pedido** funciona como un área de trabajo que le proporciona una visión general de todas las retenciones (en curso y procesadas), donde podrá gestionarlas junto con los pedidos de ventas relacionados.     
2. En la lista, marque la fila seleccionada.
3. En el **Panel de acciones**, haga clic en **Retener finalización de la compra**.
4. Haga clic en **Registro de salida del conductor**.
5. En la lista, desmarque la fila seleccionada. El campo **Desprotegido para** ahora muestra su Id. de usuario.   
6. Haga clic en **Liberar desprotección**.
7. En el **Panel de acciones**, haga clic en **Liberar retención**.
    - Cuando esté listo para quitar la retención y permitir que el pedido pase a la siguiente fase de la entrega, deberá desactivar la retención. Si el pedido no requiere ninguna modificación, puede ejecutar la acción Liberar retenciones. Sin embargo, puede usar la acción Liberar y modificar si el pedido necesita actualizarse en el momento de liberar la retención.      
    - La acción **Borrar y Enviar** solo es aplicable cuando utilice la funcionalidad del Centro de llamadas.  
8. Haga clic en **Liberar retenciones**. La retención se ha liberado del pedido y se ha quitado de la lista de retenciones activas. Para ver todas las retenciones o su subconjunto en función de un estado específico, cambie el valor del campo Mostrar.     



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]