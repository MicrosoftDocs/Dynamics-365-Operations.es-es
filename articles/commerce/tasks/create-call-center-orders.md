---
title: Crear pedidos de centro de llamadas
description: Este procedimiento le guía por la búsqueda de un cliente, la creación de un nuevo pedido, la búsqueda de un producto y el cobro de pagos del cliente.
author: josaw1
ms.date: 08/29/2018
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
ms.openlocfilehash: 78cccabb206d938b850e70b7e8057e20cc6158e1d154fc4876de7918dbe44d87
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6730668"
---
# <a name="create-call-center-orders"></a>Crear pedidos de centro de llamadas

[!include [banner](../includes/banner.md)]

Este procedimiento le guía por la búsqueda de un cliente, la creación de un nuevo pedido, la búsqueda de un producto y el cobro de pagos del cliente. Este procedimiento usa la empresa de datos de demostración USRT y está pensado para el funcionario de ventas. Requisitos previos: el usuario que complete el procedimiento se configura como usuario del centro de llamadas y el catálogo semestral de Fabrikam se publica con al menos un código fuente en él.

1. Vaya a **Retail y Commerce \> Clientes \> Servicio al cliente**.
2. En **SearchText**, especifique los criterios de búsqueda para buscar el cliente.
    * Para este procedimiento de ejemplo, escriba "Karen" y seleccione **Tabulador**.  
3. Selección Buscar.
    * Dado que solo hay un cliente llamado "Karen" en los datos de demostración, el resultado se seleccionará automáticamente.  
4. Seleccione **Nuevo pedido de ventas**.
5. Expanda o contraiga la sección de encabezado **Pedido de ventas**.
6. Seleccione el código fuente para el catálogo.
    * Si no hay códigos de origen activos, puede omitir este paso.  
7. Seleccione **Agregar línea**.
8. En el campo **Código de artículo**, especifique el término de búsqueda del artículo.
    * Para este procedimiento de ejemplo, escriba el código de artículo parcial "8111 " y presione el tabulador. Esto hará que se muestre la ventana de búsqueda del artículo.  
9. Seleccione el producto que se agregará al pedido de ventas.
10. Especifique la cantidad de ventas.
11. Seleccione **Crear**.
12. Seleccione **Completar** para capturar el pago del cliente.
13. Seleccione **Agregar**.
    * El vínculo "Agregar" se encuentra en la pestaña de pagos. Si está contraída, abra la pestaña de pagos.  
14. Seleccione el método de pago.
    * Para este procedimiento, seleccione el método de pago en efectivo.  
15. Cierre la página.
16. Especifique el importe.
    * Para este procedimiento, especifique un importe igual al saldo del pedido que se puede ver en la página Resumen de pedido de ventas a la izquierda del campo de importe. Esta acción le permitirá que completar el pedido como totalmente pagado.  
17. Seleccione **Aceptar**.
18. Seleccione **Enviar**.

## <a name="additional-resources"></a>Recursos adicionales

[Personalizar correos electrónicos transaccionales por modo de entrega](../customize-email-delivery-mode.md)

[Cambiar el modo de entrega en PDV](../pos-change-delivery-mode.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]