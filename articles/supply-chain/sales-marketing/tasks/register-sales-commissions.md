---
title: Registrar comisiones de ventas
description: En este tema se explica cómo se calculan y registran las comisiones de ventas.
author: omulvad
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  CustInvoiceJournal, CommissionTrans, LedgerTransVoucher
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: db27255c74c55b10680594ad23424253e4c3f79e
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867062"
---
# <a name="register-sales-commissions"></a>Registrar comisiones de ventas

[!include [task guide banner](../../includes/task-guide-banner.md)]

En este tema se explica cómo se calculan y registran las comisiones de ventas. Puede ejecutar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos. Antes de comenzar este guía, ejecute la guía llamada "Configurar reglas de comisión de ventas" para asegurarse de que tiene toda la configuración necesaria del cálculo de comisiones.

Anote los códigos de artículo y de cliente que ha elegido para el proceso de la comisión y úselos cuando se le solicite que crea un pedido de ventas en esta guía.


## <a name="invoice-a-sales-order-that-qualifies-a-salesperson-for-a-commission"></a>Facturar un pedido de ventas que califica a un vendedor para una comisión
1. En el panel de navegación, vaya a **Módulos > > Ventas y marketing > Pedidos de ventas > Todos los pedidos de ventas**.
2. Seleccione **Nuevo**.
3. En el campo **Cuenta de cliente**, seleccione el registro deseado desde el menú desplegable.
4. Seleccione **Aceptar**.
5. En el panel de acciones, seleccione **Opciones**.
6. Seleccione **Cambiar vista**.
7. Seleccione **Visualización de encabezado**.
8. Expanda la sección **Configuración**.

    - El valor del campo **Grupo de ventas** representa un grupo con uno o varios representantes de ventas asignados. Las personas del grupo son las que recibirán comisiones cuando se facture el pedido, según las cuotas y distribución predefinidas.   
    - El valor se copia de la Tarjeta de cliente, pero puede cambiarlo si lo desea.  
    - El grupo de ventas también se copia en la línea de pedido de ventas. Puede cambiarlo de modo que pueda ser diferente del que se encuentra en el encabezado y/o entre las líneas.  
    - El valor del campo **Grupo de comisión** representa un grupo que ha creado para uno o más clientes con el propósito de realizar el seguimiento de las comisiones.   
    - El valor se copia de la Tarjeta de cliente, pero puede cambiarlo si lo desea.   

9. En el panel de acciones, seleccione **Opciones**.
10. Seleccione **Cambiar vista**.
11. Seleccione **Vista de líneas**.
12. En el menú desplegable del campo **Código de artículo**, seleccione el artículo que haya configurado para las comisiones. 
13. En el campo **Cantidad**, especifique un número. Anote el importe neto de la línea. Representa el ingreso de ventas, que en este ejemplo es la base para el cálculo de la comisión.  
14. Seleccione **Guardar**.
15. En el Panel de acciones, seleccione **Factura**.
16. Seleccionar **Facturas**.
17. Expanda la sección **Parámetros**.
18. En el campo **Cantidad**, seleccione **Todo**.
19. Seleccione **Sí** en el campo **Registro**.
20. Seleccione **Aceptar** y, a continuación, seleccione **Aceptar** en el panel siguiente. Se puede tardar un minuto aproximadamente en registrar la transacción. Deje que se complete el procesamiento y no cierre la página.  

## <a name="review-the-registered-sales-commissions"></a>Revise las comisiones de ventas registradas
1. En el panel de acciones, seleccione **Factura** y, a continuación, vuelva a seleccionar **Factura**.
2. En el panel de acciones, seleccione **Factura** y, a continuación, seleccione **Transacciones de comisión**.

    - La pestaña **Visión general** muestra líneas que representan los importes de la comisión que se deben pagar a los representantes de ventas asociados al pedido de ventas facturado. Revisemos la información.  
    - Si ha usado la guía "Configurar reglas de comisión de ventas" para configurar el Grupo de **ventas de la comisión**, hay dos vendedores que recibirán una comisión de ventas y la comisión se dividirá de manera igualitaria entre ellos.  
    - En este ejemplo, se calcula el importe total de la comisión como porcentaje de los ingresos de ventas (el importe neto de la línea de pedido).  
3. Cierre la página.
4. Seleccione **Asiento**. Puede revisar las transacciones de asiento para los importes de comisión que se han registrado en el gasto de la comisión predefinido y las cuentas de proveedores de la comisión.  

