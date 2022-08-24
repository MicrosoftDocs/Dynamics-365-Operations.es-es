---
title: Crear pedidos de centro de llamadas
description: Este artículo explica un procedimiento de ejemplo en el que un usuario del centro de llamadas busca un cliente, crea un nuevo pedido, busca un producto y cobra el pago del cliente en Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 08/05/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: MCRCustomerService, SalesTable, MCRSourceIdTargetLookup, MCRSalesQuickQuote, MCRSalesOrderRecap, MCRCustPaymDialog, MCRCustPaymLookup
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 16d483896ce131e9a7bc60ab5ea7b8fa01a3bea8
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2022
ms.locfileid: "9228520"
---
# <a name="create-call-center-orders"></a>Crear pedidos de centro de llamadas

[!include [banner](../includes/banner.md)]

Este artículo explica un procedimiento de ejemplo en el que un usuario del centro de llamadas busca un cliente, crea un nuevo pedido, busca un producto y cobra el pago del cliente en Microsoft Dynamics 365 Commerce. El procedimiento usa la empresa de datos de demostración USRT y está pensado para funcionarios de ventas. 

## <a name="prerequisites"></a>Requisitos previos

El usuario que completa el procedimiento tiene que configurarse como un usuario del centro de llamadas. Opcionalmente, el catálogo semestral de Fabrikam se puede publicar con al menos un código fuente.

### <a name="add-yourself-as-a-call-center-user"></a>Agréguese como usuario del centro de llamadas

Para agregarse como usuario de centro de llamadas, siga estos pasos.

1. En la sede central de Commerce, vaya a **Retail y Commerce \> Canales \> Centros de llamadsa \> Todos los centros de llamadas**.
1. En el campo **Usuarios**, seleccione **Usuarios del canal**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En el campo **Id. de usuario**, especifique su identificador de usuario.
1. Escriba su nombre de usuario en el campo **Nombre**. El nombre de usuario puede ser el mismo que el ID de usuario.
1. En el panel Acciones, seleccione **Guardar**.
1. Regrese a **Venta minorista y comercio \> Canales \> Centros de llamadas \> Todos los centros de llamadas**.
1. Seleccione el ID de canal minorista del centro de llamadas.
1. Confirme que la opción **Habilitar finalización de pedido** está configurada como **Sí**. Si la opción no está visible, puede omitir este paso.

## <a name="complete-the-example-call-center-procedure"></a>Completar el procedimiento del centro de llamadas de ejemplo

Para completar el procedimiento del centro de llamadas de ejemplo, siga estos pasos.

1. Vaya a **Retail y Commerce \> Clientes \> Servicio al cliente**.
1. En la pestaña **Búsqueda de clientes**, especifique los criterios de búsqueda para buscar el cliente. Para este procedimiento de ejemplo, escriba **Karen**.
1. Selección **Buscar**. Aparecerá el cuadro de diálogo **Búsqueda de clientes** y enumerará los resultados de la búsqueda.
1. Seleccione el registro de cliente para **Karen Berg** que tiene número de cuenta de cliente **2001** y luego seleccione **Seleccionar**.
1. En el panel de acciones, seleccione **Nuevo pedido de venta**.
1. A la derecha, seleccione la pestaña **Encabezado**.
1. En la ficha desplegable **Entrega**, en la sección **Modo de entrega**, seleccione **99 estándar**.

    ![Selección de un modo de entrega.](../media/Select_Mode_of_Delivery.png)

1. A la derecha, seleccione la pestaña **Líneas**.
1. En la sección **Líneas de orden de venta**, en la nueva fila para la nueva línea de ventas, en el campo **Número de artículo**, introduzca el número de artículo que desea buscar. Para este procedimiento de ejemplo, introduzca **81327** y luego seleccione el producto en la lista desplegable para agregarlo al pedido de ventas.
1. Introduzca la cantidad de venta en el campo **Cantidad**.
1. En e campo **Código de origen**, seleccione el código de origen del catálogo. Si no hay códigos de origen activos, puede omitir este paso.
1. En el panel de acciones, seleccione **Completar** para capturar el pago del cliente. Esta acción abre el cuadro de diálogo **Resumen de pedidos de venta**, que muestra el importe total adeudado. La acción también activa el cálculo de cualquier cargo, como envío y manejo, y los muestra en el cuadro de diálogo **Resumen de pedidos de venta**.

    ![Botón Completar.](../media/Complete_button.png)

1. En el cuadro de diálogo **Resumen de pedidos de venta**, en la ficha desplegable **Pagos**, seleccione **Agregar** para capturar los pagos.

    ![Cuadro de diálogo de resumen Pedido de ventas.](../media/order_summary.png)

1. En el cuadro de diálogo **Introducir la información de pago del cliente**, en el campo **Método de pago**, seleccione el método de pago. Para este procedimiento de ejemplo, seleccione **Efectivo**.
1. En el campo **Importe de pago**, especifique el importe del pago. Para este ejemplo, introduzca **120,00**, que es igual al saldo del pedido que se muestra en el cuadro de diálogo **Resumen de pedidos de venta**. Al introducir este importe, puede completar el pedido como totalmente pagado.
1. Seleccione **Aceptar**.
1. Seleccione **Enviar**.

## <a name="additional-resources"></a>Recursos adicionales

[Personalizar correos electrónicos transaccionales por modo de entrega](../customize-email-delivery-mode.md)

[Cambiar el modo de entrega en PDV](../pos-change-delivery-mode.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
