---
title: Creación de una programación de entrega
description: En este procedimiento se demuestra cómo crear una programación de entrega para un pedido de ventas.
author: omulvad
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesDeliverySchedule, SalesEditLines,  SrsReportViewerForm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7341ec21a89bf952e2fd21e9bebf7de65a1b2648
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436660"
---
# <a name="create-delivery-schedule"></a>Creación de una programación de entrega

[!include [banner](../../includes/banner.md)]

En este procedimiento se demuestra cómo crear una programación de entrega para un pedido de ventas. Se usa una programación de entrega cuando se solicita que una cantidad de un pedido o un presupuesto se entregue en varios envíos. Puede ejecutar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos.


## <a name="create-delivery-schedule"></a>Creación de una programación de entrega
1. Vaya a Todos los pedidos de ventas.
2. Haga clic en Nuevo.
3. En el campo Cuenta de cliente, especifique o seleccione un valor.
4. Haga clic en Aceptar
5. En el campo Número de artículo, especifique o seleccione un valor.
6. En el campo Cantidad, especifique un número mayor que 1.
7. Haga clic en Línea de pedido de ventas.
8. Haga clic en Programación de entrega.
    * La página Programación de entrega es el lugar en el que puede especificar el número de envíos en los que la cantidad total de la línea de pedido se entregará al cliente.    
    * De forma predeterminada, el sistema copia la cantidad total y otros detalles de entrega de la línea de ventas original en la primera línea de la programación de entrega. En este ejemplo, crearemos una programación para dos envíos, con la fecha del segundo envío una semana después que la del primero.  
9. En el campo Cantidad, especifique un número que forme parte de la cantidad total.
10. Haga clic en Nuevo.
11. En el campo Cantidad, escriba la cantidad restante.
12. En el campo Fecha de envío solicitada, especifique una fecha que sea una semana después de la fecha de la primera línea de entrega.
    * Las dos opciones de la ficha desplegable Conversión de gastos controlan cómo desea que los gastos se distribuyan entre las líneas de la programación de entrega, una vez que se han asignado a la línea de pedido original. Si selecciona Importes brutos de copia, el mismo importe de gasto se copia en cada línea. La opción Asignar a líneas de entrega divide el gasto por igual entre las líneas de entrega.  
    * Solo se pueden dividir los gastos fijos, mientras que los gastos variables se copiarán en las líneas.  
13. Mueva el cursor fuera de la segunda línea de entrega para actualizar la página.
    * Puede realizar un seguimiento de la cantidad total que está asignada a las líneas de la programación de entrega si mira los campos Total y Restante. Cuando la cantidad restante es cero, la cantidad completa de la línea original se ha asignado a la programación.   
14. Haga clic en Aceptar
    * La programación de entrega se ha copiado a las líneas de pedido.   
    * La línea de pedido original, conocida como línea comercial, se ha convertido en una línea de pedido con varias entregas. Se marca con un icono distinto y actúa como encabezado de las líneas de entrega.  
    * Las dos líneas nuevas, designadas líneas de entrega, forman una programación de entrega. El pedido se procesará con dichas líneas y no con la línea original. Si los documentos como resguardos de confirmación, listas de selección, albaranes o facturas se imprimen, solo se muestran las líneas de entrega.   
    * Las líneas de entrega pueden tener diferentes fechas de entrega, cantidades, modos de entrega y dimensiones de almacenamiento como el sitio y el almacén. Sin embargo, las dimensiones del producto deben coincidir siempre con los que se encuentran en la línea comercial y no se pueden modificar.  
15. En el campo Cantidad, especifique un número mayor que el actual.
16. Seleccione la línea comercial para ver el efecto del recálculo de la cantidad.
17. En el panel de acciones, haga clic en Seleccionar y empaquetar.
18. Haga clic en Registrar albarán.
19. Expanda la sección Parámetros.
20. En el campo Cantidad, seleccione 'Todo'.
    * Tenga en cuenta que el albarán se creará para las dos líneas de la programación de entrega y no para la línea de pedido original.  
21. Seleccione Sí en el campo Imprimir albarán.
22. Haga clic en Aceptar
23. Haga clic en Sí.
24. Cierre la página.
