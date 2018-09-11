--- 
title: Transferir transacciones a intrastat
description: "Este procedimiento le guía por cómo configurar parámetros de intrastat y transferir transacciones a intrastat."
author: Anasyash
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResCategoryHierarchyListPage, EcoResCategory, UnitOfMeasureLookup, ProcCategoryAddCommodityCode, EcoResProductDetailsExtended, IntrastatCommodityLookup, IntrastatTransactionCode, IntrastatParameters, DeliveryMode, MarkupTable, SalesTableListPage, SalesCreateOrder, SalesTable, MarkupTrans, SalesEditLines,  Intrastat, SysQueryForm
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: anasyash
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: cc21497a6905cdb57bd687b7bff0d9dc810ba9eb
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="transfer-transactions-to-the-intrastat"></a>Transferir transacciones a intrastat

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento le guía por cómo configurar parámetros de intrastat y transferir transacciones a intrastat. Este procedimiento se creó con los datos de demostración de la empresa DEMF.


## <a name="create-new-and-update-existing-commodity-code"></a>Crear código de mercancía nuevo y actualizar el existente
1. Vaya a Gestión de información de productos > Configuración > Categorías y atributos > Jerarquías de categorías.
2. En la lista, busque o seleccione el registro "Códigos de mercancías intrastat".
3. En la lista, haga clic en el vínculo de la fila seleccionada.
4. En el árbol, seleccione "un registro".
    * Por ejemplo, seleccione "Intrastat\Altavoz".  
5. Haga clic en Editar.
6. Expanda la sección Comercio exterior.
7. En el campo Unidades adicionales, especifique o seleccione un valor.
    * Por ejemplo, elija "uds".  
8. Seleccione Sí en el campo Peso no aplicable.
9. En el árbol, seleccione "Intrastat".
10. Haga clic en Nodo de categoría nueva.
11. En el campo Nombre, introduzca el nombre de la mercancía.
    * Por ejemplo, escriba "Otra mercancía".  
12. En el campo Código, especifique el código de la mercancía.
    * Por ejemplo, escriba "995 00 00".  
13. En el campo Nombre descriptivo, escriba un valor.
    * Por ejemplo, escriba "Otros".  
14. Haga clic en Guardar.
15. Cierre la página.

## <a name="assign-commodity-code-to-product-hierarchy-and-released-product"></a>Asignar el código de mercancía a la jerarquía de productos y al producto liberado
1. Use el filtro rápido para buscar registros. Por ejemplo, filtre el campo Nombre según el valor "ventas".
2. En la lista, haga clic en el vínculo de la fila seleccionada.
3. En el árbol, expanda "un nodo de categoría".
    * Por ejemplo, expanda “Jerarquía de artículos\Audio en casa”.  
4. En el árbol, seleccione "la categoría que se debe asignar al código de la mercancía".
    * Por ejemplo, seleccione “Jerarquía de artículos\Altavoces”.  
5. Expanda la sección Códigos de mercancías.
6. Haga clic en Agregar.
7. En el campo Seleccionar jerarquía, seleccione "Intrastat".
8. En la lista, busque y seleccione el código de la mercancía.
    * Por ejemplo, seleccione "920 20 34 Altavoz".  
9. Haga clic en Seleccionar códigos.
10. Haga clic en Aceptar
11. Vaya a Gestión de información de productos > Productos > Productos emitidos.
12. En la lista, elija el producto liberado que asignará al código de la mercancía.
    * Por ejemplo, elija "D0001".  
13. Haga clic en Editar.
14. Expanda la sección Comercio exterior.
15. En el campo Código intrastat de la mercancía, especifique el código de la mercancía
    * Por ejemplo, seleccione el valor "920 20 34 Altavoz".    
16. En el campo Porcentaje de gastos, especifique un número.
    * Por ejemplo, escriba "3".  
17. En el campo País o región, escriba o seleccione un país o una región de origen
    * Por ejemplo, seleccione "AUT".  
18. Expanda la sección Administrar inventario.
19. En el campo Peso neto, escriba un peso en kg.
    * Por ejemplo, escribe "2,5".  
20. Haga clic en Guardar.

## <a name="set-up-intrastat-transaction-codes-and-foreign-trade-parameters"></a>Configurar los códigos de transacción intrastat y los parámetros de comercio exterior
1. Vaya a Impuesto > Configurar > Comercio exterior > Códigos de transacción
2. Haga clic en Nuevo.
3. En el campo Código de transacción, escriba un valor.
    * Por ejemplo, especifique “21" para el código de transacción que se usa como devolución.  
4. En el campo Nombre, escriba el nombre del código de la transacción.
    * Por ejemplo, especifique "Devolución".  
5. En el campo Importe estadístico, seleccione una opción.
    * Por ejemplo, seleccione “Vacía” que indica que el valor estadístico que se notificará para las transacciones con el código de transacción de “21 "será siempre cero.  
6. Vaya a Impuestos > Configuración > Comercio exterior > Parámetros de comercio exterior.
7. En el campo Código de transacción, especifique o seleccione un valor.
    * Por ejemplo, seleccione "'11".  
8. En el campo Nota de abono, especifique o seleccione un valor.
    * Este valor también identifica la devolución física. La nota de abono para la devolución física se transferirá en el diario de Intrastat con la dirección opuesta. Por ejemplo, la devolución de llegada se transfiere como distribución.   De lo contrario, la nota de abono se considera una corrección y se transfiere con la misma dirección y signo opuesto. Por ejemplo, la corrección de llegada se transfiere como llegada con importe negativo y el indicador activa se establece en “Corrección”.  
9. Expanda la sección Transferir.
10. Seleccione Sí en el campo Artículos con código de mercancía.
    * Seleccione esta opción para transferir solo las transacciones con un código de mercancía asignado. Las transacciones sin un código de mercancía no se transferirán a intrastat.  
11. En el campo Transferir cuando se cumpla el criterio para, seleccione una opción.
    * Por ejemplo, seleccione "Uno de los seleccionados”.  
12. Expanda la sección Jerarquía de códigos de mercancías.
13. Haga clic en la ficha Propiedades de país/región.
14. Haga clic en Nuevo.
15. En el campo País o región, especifique o seleccione un valor.
    * Por ejemplo: seleccione el valor "FRA".  
16. En el campo Código intrastat, especifique el código ISO para el país.
    * Por ejemplo, escriba "FR".  
17. En el campo Tipo de país/región, seleccione "UE".
18. Haga clic en la ficha Secuencias numéricas.

## <a name="set-up-modes-of-delivery-and-rules-for-including-charges-in-intrastat"></a>Configurar los modos de entrega y las reglas para incluir gastos en intrastat
1. Vaya a Ventas y marketing > Configurar > Distribución > Modos de entrega
2. En la lista, busque y seleccione el registro deseado.
    * Por ejemplo, seleccione "20 Air".  
3. Expanda la sección Comercio exterior.
4. Haga clic en Editar.
5. En el campo Transporte, especifique o seleccione un valor.
    * Por ejemplo, seleccione "'02".  
6. Vaya a Clientes > Configuración de cargos > Código de gastos.
7. Use el filtro rápido para buscar registros. Por ejemplo, filtre el campo Código de gastos según el valor "flete".
8. Expanda la sección Comercio exterior.
9. Haga clic en Editar.
10. Seleccione Sí en el campo Valor de la factura de intrastat.
    * El importe se transferirá al campo Gastos de factura y se resumirá con el importe transferido en el campo Importe de la factura.    Seleccione Sí en el campo Valor estadístico de intrastat si el importe de los cambios se tiene que transferir al campo Gastos estadísticos y resumirse con el Importe estadístico.  

## <a name="sell-products-for-eu-customers"></a>Vender productos para los clientes de la UE
1. Vaya a Clientes > Pedidos > Todos los pedidos de venta.
2. Haga clic en Nuevo.
3. En el campo Cuenta de cliente, seleccione un cliente de UE.
    * Por ejemplo, seleccione "DE-012 Litware Retail".  
4. Expanda la sección Entrega.
5. En el campo Entrega, especifique o seleccione un valor.
    * Por ejemplo, seleccione "20 Air".  
6. Haga clic en Aceptar
7. Coloque el cursor en la primera fila de las líneas de pedido de venta.
8. En el campo Número de artículo, especifique o seleccione un valor.
    * Por ejemplo, seleccione "D001".  
9. Expanda la sección Detalles de línea.
10. Haga clic en la ficha Comercio exterior.
    * El transporte se rellena automáticamente desde el modo de entrega elegido.  
11. En el campo Puerto, especifique o seleccione un valor.
12. Haga clic en Operaciones financieras.
    * Según la configuración, este importe se incluirá en el Valor de la factura de intrastat.  
13. Haga clic en Mantener gastos.
14. En el campo Código de gastos, especifique o seleccione un valor.
    * Por ejemplo, seleccione "FLETE".  
15. Active la casilla Conservar.
16. En el campo Valor de gastos, escriba un número.
    * Por ejemplo, escribe "10".  
17. Haga clic en Guardar.
18. Cierre la página.
19. En el panel de acciones, haga clic en Factura.
20. Haga clic en Factura.
21. Expanda la sección Parámetros.
22. En el campo Cantidad, seleccione 'Todo'.
23. Expanda la sección Configuración.
24. En el campo Fecha de la factura, especifique una fecha.
    * Por ejemplo, escriba "31-01-2015".  
25. Haga clic en Aceptar
26. Haga clic en Aceptar
27. Cierre la página.
28. Haga clic en Nuevo.
29. En el campo Cuenta de cliente, seleccione un cliente de UE.
    * Por ejemplo, seleccione "DE-013 Trey Wholesales"  
30. Haga clic en Aceptar
31. En el campo Número de artículo, especifique o seleccione un valor.
    * Por ejemplo, seleccione "D0001".  
32. Haga clic en Guardar.
33. Haga clic en Factura.
34. En el campo Fecha de la factura, especifique una fecha.
    * Por ejemplo, especifique la fecha "31-01-2015".  
35. Haga clic en Aceptar
36. Haga clic en Aceptar

## <a name="transfer-transactions-to-the-intrastat"></a>Transferir transacciones a intrastat
1. Vaya a Impuestos > Declaraciones > Comercio exterior > Intrastat.
2. Haga clic en Transferir.
3. Seleccione Sí en el campo Factura del cliente.
4. Haga clic en Filtro.
5. En la lista, marque la fila con Fecha
6. En el campo Criterios, escriba un valor.
    * Por ejemplo, escriba el filtro para el período de enero de 2015 (el valor exacto depende del formato de fecha): 1/1/2015..31/1/2015  
7. Haga clic en Aceptar
8. Haga clic en Aceptar
9. En la lista, busque y seleccione el registro transferido.
10. Haga clic en la pestaña General.
    * Revise los datos transferidos, incluidos el país o la región de destino/envío, el país de origen, el peso, la cantidad, la cantidad en unidades adicionales, la mercancía, el código de transacción, los importes de factura y los importes estadísticos.   Puede modificar los datos, si procede.  


