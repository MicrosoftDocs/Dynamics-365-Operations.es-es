--- 
title: Registrar comisiones de ventas
description: "Este procedimiento le muestra cómo se calculan y registran las comisiones de ventas."
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  CustInvoiceJournal, CommissionTrans, LedgerTransVoucher
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 5535f1627526b97ddc9ca2c210db4e332782d656
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="register-sales-commissions"></a>Registrar comisiones de ventas

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento le muestra cómo se calculan y registran las comisiones de ventas. Puede ejecutar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos. Antes de comenzar este guía, ejecute la guía llamada "Configurar reglas de comisión de ventas" para asegurarse de que tiene toda la configuración necesaria del cálculo de comisiones.

Anote los códigos de artículo y de cliente que ha elegido para el proceso de la comisión y úselos cuando se le solicite que crea un pedido de ventas en esta guía.


## <a name="invoice-a-sales-order-that-qualifies-a-salesperson-for-a-commission"></a>Facturar un pedido de ventas que califica a un vendedor para una comisión
1. Vaya a Ventas y marketing > Pedidos de ventas > Todos los pedidos de ventas.
2. Haga clic en Nuevo.
3. En el campo Cuenta de cliente, haga clic en el botón desplegable para abrir la búsqueda.
4. En la lista, busque y seleccione el registro deseado.
5. En la lista, haga clic en el vínculo de la fila seleccionada.
6. Haga clic en Aceptar
7. En el panel de acciones, haga clic en Opciones.
8. Haga clic en Cambiar vista.
9. Haga clic en Visualización de encabezado.
10. Expanda la sección Configuración.
    * El valor del campo Grupo de ventas representa un grupo con uno o varios representantes de ventas asignados. Las personas del grupo son las que recibirán comisiones cuando se facture el pedido, según las cuotas y distribución predefinidas.   El valor se copia de la Tarjeta de cliente, pero puede cambiarlo si lo desea.  El grupo de ventas también se copia en la línea de pedido de ventas. Puede cambiarlo de modo que pueda ser diferente del que se encuentra en el encabezado y/o entre las líneas.  
    * El valor del campo Grupo de comisión representa un grupo que ha creado para uno o más clientes con el propósito de realizar el seguimiento de las comisiones.   El valor se copia de la Tarjeta de cliente, pero puede cambiarlo si lo desea.   
11. En el panel de acciones, haga clic en Opciones.
12. Haga clic en Cambiar vista.
13. Haga clic en Vista de líneas.
14. En el campo Código de artículo, haga clic en el botón desplegable para abrir la búsqueda.
15. En la lista, seleccione el artículo que se ha configurado para las comisiones. 
16. En el campo Cantidad, especifique un número.
    * Anote el importe neto de la línea. Representa el ingreso de ventas, que en este ejemplo es la base para el cálculo de la comisión.  
17. Haga clic en Guardar.
18. En el panel de acciones, haga clic en Factura.
19. Haga clic en Factura.
20. Expanda la sección Parámetros.
21. En el campo Cantidad, seleccione 'Todo'.
22. Seleccione Sí en el campo Registro.
23. Haga clic en Aceptar
24. Haga clic en Aceptar
    * Se puede tardar un minuto aproximadamente en registrar la transacción. Deje que se complete el procesamiento y no cierre la página.  

## <a name="review-the-registered-sales-commissions"></a>Revise las comisiones de ventas registradas
1. En el panel de acciones, haga clic en Factura.
2. Haga clic en Factura.
3. En el panel de acciones, haga clic en Factura.
4. Haga clic en Transacciones de comisión.
    * La ficha Visión general muestra líneas que representan los importes de la comisión que se deben pagar a los representantes de ventas asociados al pedido de ventas facturado. Revisemos la información.     
    * Si ha usado la guía "Configurar reglas de comisión de ventas" para configurar el Grupo de ventas de la comisión, hay dos vendedores que recibirán una comisión de ventas y la comisión se dividirá de manera igualitaria entre ellos.  
    * En este ejemplo, se calcula el importe total de la comisión como porcentaje de los ingresos de ventas (el importe neto de la línea de pedido).   
5. Cierre la página.
6. Haga clic en Asiento.
    * Puede revisar las transacciones de asiento para los importes de comisión que se han registrado en el gasto de la comisión predefinido y las cuentas de proveedores de la comisión.  


