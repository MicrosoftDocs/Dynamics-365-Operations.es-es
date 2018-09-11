--- 
title: "Configurar reglas de comisión de ventas"
description: "Este procedimiento muestra cómo configurar y habilitar el seguimiento y el cálculo de las comisiones de ventas."
author: omulvad
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CommissionCustomerGroup, CommissionItemGroup, CommissionSalesGroup, CommissionSalesMember, DirPartyLookup, CommissionCalc, InventPosting, CustTable, EcoResProductDetailsExtended
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 8d81765884f741443d1c0f5b0cb8bc545945e1a1
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-sales-commission-rules"></a>Configurar reglas de comisión de ventas

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo configurar y habilitar el seguimiento y el cálculo de las comisiones de ventas. El procedimiento muestra cómo crear grupos de comisión tanto de clientes como de artículos, y después cómo vincular un producto y cliente seleccionado a los grupos respectivos. A continuación esos grupos se usan en la configuración del cálculo de la comisión para crear una combinación de cliente, artículo y representantes de ventas que se debe conciliar con el pedido de ventas para dar derecho a los vendedores a una comisión. La creación de grupos de comisión de clientes y artículos es opcional, ya que el cálculo de la comisión también se puede realizar para un cliente y/o artículo individual. Puede ejecutar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos.


## <a name="set-up-commission-groups-and-commission-rates"></a>Configurar grupos de comisiones y tasas de comisión
1. Vaya a Ventas y marketing > Comisiones > Grupos de clientes para comisión.
2. Haga clic en Nuevo.
3. En el campo Grupo, escriba un valor.
4. En el campo Nombre, escriba un valor.
5. Haga clic en Guardar.
6. Cierre la página.
7. Vaya a Ventas y marketing > Comisiones > Grupos de artículos.
8. Haga clic en Nuevo.
9. En el campo Grupo, escriba un valor.
10. En el campo Nombre, escriba un valor.
11. Cierre la página.
12. Vaya a Ventas y marketing > Comisiones > Grupos de ventas.
    * Un grupo de ventas de la comisión especifica los empleados de los roles de representante de ventas que son aptos recibir una comisión cuando un cliente asociado al grupo de ventas pertinente compra determinados artículos.  
    * En la empresa de datos de demostración USMF, hay un grupo de ventas denominado “Representantes de ventas EE. UU.”.  
13. En el panel de acciones, haga clic en General.
14. Haga clic en Comercial.
    * La página Representante de ventas muestra una lista de los vendedores asociados a un grupo de comisión específico. Puede asignar múltiples representantes de ventas al mismo grupo y definir su parte respectiva de la cuota de comisión total como valor de porcentaje. La parte de la comisión total entre todos los empleados no debe superar 100.  
15. En la lista, marque la fila seleccionada.
16. Haga clic en Editar.
17. Establezca la proporción de comisión en "50".
18. Haga clic en Nuevo.
19. En el campo Nombre, haga clic en el botón desplegable para abrir la búsqueda.
20. Use el filtro rápido para buscar registros. Por ejemplo, filtrar en el campo Nombre con un valor de “Susan Burk”.
21. Haga clic en Seleccionar.
22. Establezca la proporción de comisión en "50".
23. Haga clic en Guardar.
24. Vaya a Ventas y marketing > Comisiones > Cálculo de comisiones.
    * En la página Cálculo de comisiones defina el índice de comisión que el empleado debe recibir para una transacción de ventas cuando contiene la combinación preestablecida de cliente y producto. Como parte de la configuración de la tasa de comisión, debe especificar la base del cálculo de la comisión y si debe incluir o excluir descuentos. También puede especificar un período de validez para cuándo la tasa de comisión está activa.  
25. Haga clic en Nuevo.
26. En el campo Código de artículo, seleccione "Grupo".
27. En el campo Relación de artículos, haga clic en el botón desplegable para abrir la búsqueda.
28. En la lista, busque y seleccione el grupo que ha creado anteriormente.
29. En la lista, haga clic en el vínculo de la fila seleccionada.
30. Seleccione "Grupo" en el campo Código de cliente.
31. En el campo Relación con clientes, haga clic en el botón desplegable para abrir la búsqueda.
32. En la lista, seleccione el grupo que ha configurado anteriormente.
33. En el campo Relación de comerciales, haga clic en el botón desplegable para abrir la búsqueda.
34. En la lista, busque y seleccione el registro deseado.
    * Mantenga la opción “Antes dto. línea”.  
    * Mantenga la opción "Ingresos" como la base para el cálculo del valor de la comisión.    
35. En el campo Porcentaje de comisión, especifique un número.
36. Haga clic en Guardar.

## <a name="setting-up-commission-posting"></a>Configuración de registro de comisión
1. Vaya a Ventas y marketing > Comisiones > Registro de la comisión.
    * Las cuotas de comisión se deben pagar a los empleados y se deben configurar por tanto para garantizar el registro financiero correcto en las cuentas adecuadas de la Contabilidad general. Esto se realiza en la página Registro de la comisión. Revise la configuración que está disponible para la empresa actual. Normalmente, los importes de comisión se registran en una cuenta de gastos dedicada y se compensan en una cuenta de proveedores dedicada. Si no dispone de la configuración de reglas de registro de comisión, el sistema no podrá completar la facturación de un pedido de ventas que tenga comisiones aptas.  
2. Cierre la página.

## <a name="assign-a-commission-group-to-a-customer-and-a-product"></a>Asignar un grupo de la comisión a un cliente y a un producto
1. Vaya a Ventas y marketing > Clientes > Todos los clientes.
2. En la lista, busque y seleccione el registro deseado.
3. En la lista, haga clic en el vínculo de la fila seleccionada.
4. Haga clic en Editar.
5. Expanda la sección Valores predeterminados del pedido de ventas.
6. En el campo Grupo de comisión, haga clic en el botón desplegable para abrir la búsqueda.
7. En la lista, seleccione el grupo que ha creado anteriormente.
8. En el campo Grupo de ventas, haga clic en el botón desplegable para abrir la búsqueda.
9. En la lista, busque y seleccione el registro deseado.
10. Haga clic en Guardar.
11. Vaya a Gestión de información de productos > Productos > Productos emitidos.
12. Use el filtro rápido para buscar registros. Por ejemplo, filtre por el campo Número de artículo con un valor de "T0020".
13. En la lista, haga clic en el vínculo de la fila seleccionada.
14. Haga clic en Editar.
15. Expanda la sección Vender.
16. En el campo Grupo de comisión, haga clic en el botón desplegable para abrir la búsqueda.
17. En la lista, seleccione el grupo de comisión que ha creado anteriormente.


