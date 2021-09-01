---
title: Confirmar pedidos de ventas
description: Este procedimiento muestra cómo confirmar pedidos de ventas.
author: omulvad
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesTable, SalesEditLines,  SrsReportViewerForm, CustConfirmJournal, SysQueryForm, SysQueryFieldLookUp, SysLookup, SalesParmIdLookup, SalesUnconfirmedOrdersPart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ac5217ecd74e3a8d4dd6a82112788a7aaba4698857cd5854eed1f8c91aa97e73
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6779167"
---
# <a name="confirm-sales-orders"></a>Confirmar pedidos de ventas

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo confirmar pedidos de ventas. Se le mostrará cómo confirmar un solo pedido y cómo confirmar varios pedidos de una vez. Estas tareas las realizará normalmente la persona encargada de procesar los pedidos de ventas. Puede utilizar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos. Antes de empezar, asegúrese de que haya varios pedidos de ventas abiertos para el mismo cliente. Si está usando USMF, puede usar el cliente US-027.


## <a name="confirm-a-single-sales-order"></a>Confirmación de un solo pedido de ventas
1. Vaya a **Panel de navegación > Módulos > Ventas y marketing > Pedidos de ventas > Todos los pedidos de ventas**.
2. En la lista, busque y seleccione el pedido que desee confirmar.
3. Haga clic en el vínculo en el número de pedido de ventas para abrir el pedido seleccionado.
4. En **Panel de acciones**, haga clic en **Vender**.
5. Haga clic en **Confirmar pedido de ventas**.
6. Expanda la sección **Parámetros**. Compruebe que la opción **Registro** está establecida en Sí.  
7. Establezca la opción **Imprimir confirmación** en Sí. El campo **Comprobar límite de crédito** especifica el método que se usa para calcular el crédito que le queda a un cliente. De forma predeterminada, se copia desde la página Parámetros de clientes. Si desea omitir la comprobación del límite de crédito al confirmar un pedido de ventas específico, defina **Comprobar límite de crédito** en Ninguno. No obstante, debe tener presente que, incluso si este campo está establecido en Ninguno, la comprobación del límite de crédito se seguirá realizando si la opción **Límite de crédito obligatorio** está seleccionada en los datos maestros del cliente. 
8. Haga clic en **Aceptar**.
9. Haga clic en **Sí**.
10. Cierre la página.
11. En el **panel de acciones**, haga clic en **Opciones**.
12. Haga clic en **Cambiar vista**.
13. Haga clic en **Visualización de encabezado**. Cuando se confirma un pedido, el **estado del documento** se establece en Confirmación. 
14. En **Panel de acciones**, haga clic en **Vender**.
15. Haga clic en **Confirmación del pedido de ventas**.
16. Cierre la página.

## <a name="confirm-multiple-sales-orders-at-once"></a>Confirmación de varios pedidos de ventas a la vez
1. Vaya a **Ventas y marketing > Pedidos de ventas > Confirmación de pedido > Confirmar pedido de ventas**.
2. Haga clic en **Seleccionar**.
3. En la lista de la ficha **Rango**, localice y seleccione el registro que hace referencia al campo **Cuenta de cliente**.
4. En el campo **Criterios**, haga clic en el botón desplegable para abrir la búsqueda.
5. En la lista, busque y seleccione la cuenta de cliente con los varios pedidos que desea confirmar en masa. Si está usando USMF, puede seleccionar la cuenta US-027.  
6. Haga clic en **Aceptar**.
    - La ficha **Visión general** muestra una lista de los pedidos que coinciden con los criterios de la consulta. Estos se incluirán en la confirmación.  
    - El campo **Actualización conjunta para** de la sección **Parámetros** especifica el parámetro por el cual se reunirán varios pedidos en un documento de confirmación. De forma predeterminada, la opción se copia de los **valores predeterminados del ajuste de actualización conjunta** en la página **Parámetros de clientes**.  
7. En el campo **Actualización conjunta para**, seleccione Pedido. Los parámetros mínimos requeridos para crear actualizaciones conjuntas son la **Cuenta de facturación** y la **Divisa**. Esto significa que no se permiten actualizaciones conjuntas con diferentes cuentas de facturación y divisas. Se pueden configurar parámetros adicionales en la página **Parámetros de actualización conjunta**, disponible desde la página **Parámetros de clientes**. 
8. En el campo **Pedido de ventas**, haga clic en el botón desplegable para abrir la búsqueda.
9. En la lista, seleccione el número del pedido que desea que sea el pedido de resumen.
10. Haga clic en **Organizar**.
11. Haga clic en **Aceptar**.
12. Haga clic en **Aceptar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]