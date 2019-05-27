---
title: Cumplimiento de acuerdos de venta
description: Este procedimiento le muestra cómo satisfacer un acuerdo de venta asociando pedidos de ventas a él.
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesAgreementListPage, SalesAgreement, SalesAgreementGenerateReleaseOrder, SalesTableListPage, SalesTable, AgreementLine, SalesCreateOrder,  SalesEditLines
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f03f05b85b8d242db1c85d0e84667949e241f1f7
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1563957"
---
# <a name="fulfill-sales-agreements"></a>Cumplimiento de acuerdos de venta

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento le muestra cómo satisfacer un acuerdo de venta asociando pedidos de ventas a él. Puede ejecutar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos. Antes de comenzar este guía, asegúrese de que tiene un acuerdo de venta vigente del tipo "Compromiso de valor de producto". Como alternativa, puede ejecutar la guía de tareas llamada "Crear o acuerdos de venta".  




## <a name="release-a-sales-order-from-the-agreement"></a>Liberar un pedido de ventas del acuerdo
1. Vaya a Ventas y marketing > Acuerdos de venta > Acuerdos de venta.
2. En la lista, abra el acuerdo con el que desea liberar el pedido.
3. En el panel de acciones, haga clic en Acuerdo de venta
4. Haga clic en Pedido parcial.
    * A medida que se muestra el texto de la parte superior de la página Crear pedido parcial, los detalles necesarios para las líneas de pedidos de ventas serán diferentes en función de si el contrato se basa en una cantidad o en un valor.  
    * El acuerdo de esta guía es de tipo “Compromiso de valor de producto”. Este es el motivo por el que la sección Líneas de esta página está en blanco. Si el compromiso se basa en la cantidad, se copiará del acuerdo la información de la línea.  
5. Haga clic en Crear.
    * El mensaje informa de que se ha creado un pedido de ventas. Dado que el pedido no contiene ninguna línea, debe agregar los detalles de la línea de pedido para completar el proceso de lanzamiento.   
6. Cierre la página.
7. Cierre la página.
8. Vaya a Ventas y marketing > Pedidos de ventas > Todos los pedidos de ventas.
9. En la lista, busque y abra el pedido creado como resultado de la emisión de pedido de la tarea anterior.
10. Haga clic en Agregar línea.
11. En el campo Código de artículo, haga clic en el botón desplegable para abrir la búsqueda.
12. En el campo Código de artículo, escriba o seleccione el artículo que se especifica en el acuerdo de venta asociado.
13. En el campo Cantidad, especifique un número.
    * Asegúrese de especificar una cantidad que lleve el Importe neto bajo el valor del acuerdo de venta asociado.  
    * Observe que dado que el pedido de ventas está vinculado al acuerdo, el porcentaje de descuento negociado se aplica a la línea de pedido.  
14. Haga clic en Actualizar línea.
15. Haga clic en Adjunto.
    * La página Acuerdo adjunto muestra el id. y las condiciones del acuerdo desde el que se libera la línea.  
16. Cierre la página.
17. En el panel de acciones, haga clic en General.
18. Haga clic en Acuerdo de venta adjunto.
19. Expanda la sección Detalles de línea.
20. Haga clic en la pestaña Suministro.
    * La etiqueta Suministro muestra un resumen de todas las líneas de pedidos de ventas asociadas a este compromiso, y su estado de cumplimiento, junto con el importe o la cantidad que aún no se han liberado.   
21. Cierre la página.
22. Cierre la página.
23. Cierre la página.

## <a name="apply-sales-agreement-in-the-order-process"></a>Aplicar el acuerdo de ventas en el proceso de pedidos
1. Vaya a Ventas y marketing > Pedidos de ventas > Todos los pedidos de ventas.
2. Haga clic en Nuevo.
3. En el campo Cuenta de cliente, haga clic en el botón desplegable para abrir la búsqueda.
4. En la lista, busque y seleccione el cliente especificado en el acuerdo de venta.
5. En la lista, haga clic en el vínculo de la fila seleccionada.
6. Expanda la sección General.
7. En el campo Id. del acuerdo de venta, haga clic en el botón desplegable para abrir la búsqueda.
8. En la lista, haga clic en el vínculo de la fila seleccionada.
9. Haga clic en Sí.
10. Haga clic en Aceptar
11. En la lista, marque la fila seleccionada.
12. En el campo Código de artículo, haga clic en el botón desplegable para abrir la búsqueda.
13. En el campo Código de artículo, escriba o seleccione el artículo que se especifica en el acuerdo de venta asociado.
14. En la lista, haga clic en el vínculo de la fila seleccionada.
15. Haga clic en Guardar.
16. En el panel de acciones, haga clic en Seleccionar y empaquetar.
17. Haga clic en Registrar albarán.
18. Expanda la sección Parámetros.
19. Seleccione Sí en el campo Registro.
20. Haga clic en Aceptar
21. Haga clic en Aceptar
22. En el panel de acciones, haga clic en General.
23. Haga clic en Acuerdo de venta adjunto.
24. Haga clic en la pestaña Suministro.

