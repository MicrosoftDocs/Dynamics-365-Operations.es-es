---
title: Enviar pedidos de ventas sin almacenamiento
description: En este tema se explica cómo actualizar un pedido de ventas cuando los productos se envían al cliente.
author: omulvad
manager: tfehr
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesTable, SalesEditLines,  SrsReportViewerForm, SalesTableLineQuantity, CustPackingSlipJournal
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 45884bd5ff70b31c62a7e0affafb6c5ddb457be3
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974869"
---
# <a name="ship-sales-orders-without-warehousing"></a>Enviar pedidos de ventas sin almacenamiento

[!include [banner](../../includes/banner.md)]

En este tema se explica cómo actualizar un pedido de ventas cuando los productos se envían al cliente. La guía es aplicable al flujo de cumplimiento que no se ha configurado para la gestión de almacenes (ni el almacenamiento básico o avanzado) y, por tanto. no requiere que se registre la selección del producto antes del envío. Puede ejecutar este procedimiento en sus propios datos o en la empresa de demostración USMF. En ambos casos, antes de comenzar esta tarea, cree un pedido de ventas para un producto del inventario con una cantidad de mayor de 1. Para evitar un error de registro, necesita comprobar que la cantidad de producto disponible en el sitio y el almacén que ha seleccionado para pedir cubre la cantidad de pedido.

## <a name="post-packing-slip-for-an-order"></a>Registrar albarán para un pedido
1. En el panel de navegación, vaya a **Módulos > > Ventas y marketing > Pedidos de ventas > Todos los pedidos de ventas**.
2. En la lista, busque y seleccione el pedido que ha creado para esta tarea.
3. En el panel de acciones, seleccione **Seleccionar y empaquetar**.
4. Seleccione **Registrar albarán**.
5. Expanda o contraiga la sección **Parámetros**.
6. En el campo **Cantidad**, seleccione **Todo**.
    - Otras opciones incluyen **Entregar ahora** y **Seleccionado**. Si la línea de pedido se va a enviar parcialmente y el campo **Entregar ahora** de la línea de pedido contiene una cantidad, seleccionaría **Entregar ahora**. Si el flujo de cumplimiento de la organización incluye la selección como un proceso independiente que se administra por una lista de selección y se registra con ella, seleccionaría **Seleccionado**.  
    - Compruebe que la opción **Registro** está establecida en **Sí**.  
7. Establezca la opción **Imprimir albarán** en **Sí**. La pestaña **Visión general** contiene una lista de albaranes que se generarán en este registro. Si va a enviar un pedido individual, habrá normalmente un albarán. Sin embargo, si las líneas del pedido se van a enviar desde distintos sitios, el registro se dividirá automáticamente en el número adecuado de documentos. Esta es una condición obligatoria que no puede modificarse. Del mismo modo, el registro también se dividirá en varios documentos si las líneas del pedido se van a enviar a diferentes direcciones de entrega y la directiva de envío se configura para requerir una división.  
8. En la pestaña **Líneas**, seleccione la fila para la línea de pedido que se va enviar.
9. En el campo **Actualizar**, escriba un número menor que la cantidad original.
10. Seleccione **Aceptar**.
11. Seleccione **Sí**.
12. Cierre la página.
13. En el panel de acciones, seleccione **Opciones**.
14. Seleccione **Cambiar vista**.
15. Seleccione **Visualización de encabezado**.
    - Si todas las líneas del pedido se han enviado completamente, el estado del pedido cambia de Abierto a Entregado.  
    - En este ejemplo, la línea de pedido se ha enviado parcialmente. Este es el motivo por el cual el estado del pedido permanece abierto.     
    - El campo **Estado del documento** se establece en Albarán porque se ha enviado al menos una de las líneas del pedido.  
16. En el panel de acciones, seleccione **Gneral**.
17. Seleccione **Cantidad de línea**.
18. Cierre la página.
19. En el panel de acciones, seleccione **Seleccionar y empaquetar**.
20. Seleccione **Albarán**. La página **Diario del albarán** contiene todos los documentos de albaranes generados para el pedido. Puede revisar los detalles de cada documento e imprimirlos, si lo desea.  

