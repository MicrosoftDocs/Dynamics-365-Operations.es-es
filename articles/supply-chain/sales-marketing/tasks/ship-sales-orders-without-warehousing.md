---
title: Enviar pedidos de ventas sin almacenamiento
description: Esta guía muestra cómo actualizar un pedido de ventas cuando los productos se envían al cliente.
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesTable, SalesEditLines,  SrsReportViewerForm, SalesTableLineQuantity, CustPackingSlipJournal
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ae70e09dbc4da90b7d1802d076384eae2d00da0e
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1555802"
---
# <a name="ship-sales-orders-without-warehousing"></a>Enviar pedidos de ventas sin almacenamiento

[!include [task guide banner](../../includes/task-guide-banner.md)]

Esta guía muestra cómo actualizar un pedido de ventas cuando los productos se envían al cliente. La guía es aplicable al flujo de cumplimiento que no se ha configurado para la gestión de almacenes (ni el almacenamiento básico o avanzado) y, por tanto. no requiere que se registre la selección del producto antes del envío. Puede ejecutar este procedimiento en sus propios datos o en la empresa de demostración USMF. En ambos casos, antes de comenzar esta tarea, cree un pedido de ventas para un producto del inventario con una cantidad de mayor de 1. Para evitar un error de registro, necesita comprobar que la cantidad de producto disponible en el sitio y el almacén que ha seleccionado para pedir cubre la cantidad de pedido.


## <a name="post-packing-slip-for-an-order"></a>Registrar albarán para un pedido
1. Vaya a Ventas y marketing > Pedidos de ventas > Todos los pedidos de ventas.
2. En la lista, busque y seleccione el pedido que ha creado para esta tarea.
3. En la lista, haga clic en el vínculo de la fila seleccionada.
4. En el panel de acciones, haga clic en Seleccionar y empaquetar.
5. Haga clic en Registrar albarán.
6. Expanda o contraiga la sección Parámetros.
7. En el campo Cantidad, seleccione 'Todo'.
    * Otras opciones incluyen Entregar ahora y Seleccionado. Si la línea de pedido se va a enviar parcialmente y el campo Entregar ahora de la línea de pedido contiene una cantidad, seleccionaría Entregar ahora. Si el flujo de cumplimiento de la organización incluye la selección como un proceso independiente que se administra por una lista de selección y se registra con ella, seleccionaría Seleccionado.  
    * Compruebe que la opción Registro está establecida en Sí.  
8. Establezca la opción Imprimir albarán en Sí.
    * La ficha Visión general contiene una lista de albaranes que se generarán en este registro. Si va a enviar un pedido individual, habrá normalmente un albarán. Sin embargo, si las líneas del pedido se van a enviar desde distintos sitios, el registro se dividirá automáticamente en el número adecuado de documentos. Esta es una condición obligatoria que no puede modificarse. Del mismo modo, el registro también se dividirá en varios documentos si las líneas del pedido se van a enviar a diferentes direcciones de entrega y la directiva de envío se configura para requerir una división.  
9. En la pestaña Líneas, seleccione la fila para la línea de pedido que se va enviar.
10. En el campo Actualizar, escriba un número menor que la cantidad original.
11. Haga clic en Aceptar
12. Haga clic en Sí.
13. Cierre la página.
14. En el panel de acciones, haga clic en Opciones.
15. Haga clic en Cambiar vista.
16. Haga clic en Visualización de encabezado.
    * Si todas las líneas del pedido se han enviado completamente, el estado del pedido cambia de Abierto a Entregado.  
    * En este ejemplo, la línea de pedido se ha enviado parcialmente. Este es el motivo por el cual el estado del pedido permanece abierto.     
    * El campo Estado del documento se establece en Albarán porque se ha enviado al menos una de las líneas del pedido.  
17. En el panel de acciones, haga clic en General.
18. Haga clic en Cantidad de línea.
19. Cierre la página.
20. En el panel de acciones, haga clic en Seleccionar y empaquetar.
21. Haga clic en Albarán.
    * La página Diario del albarán contiene todos los documentos de albaranes generados para el pedido. Puede revisar los detalles de cada documento e imprimirlos, si lo desea.  

