--- 
title: Crear un acuerdo de compra
description: "Este procedimiento le guía por el proceso de creación de un acuerdo de compra."
author: mkirknel
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 0d0cc6508071bea3f622bc21f06aa55d2b757b6f
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-purchase-agreement"></a>Crear un acuerdo de compra

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento le guía por el proceso de creación de un acuerdo de compra. Esto normalmente lo haría el director de compras. Puede utilizar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos. Es necesario haber configurado clasificaciones de acuerdo de compra antes de comenzar. Una vez que haya creado un acuerdo, podrá usarlo cuando cree un pedido de compra; esto copiará las condiciones del acuerdo de compra al encabezado y a cualquier línea del pedido a la que afecte el acuerdo.


## <a name="create-a-new-purchase-agreement"></a>Creación de un acuerdo de compra nuevo
1. Vaya a Adquisición y abastecimiento > Acuerdos de compra > Acuerdos de compra.
2. Haga clic en Nuevo.
3. En el campo Cuenta de proveedor, haga clic en el botón desplegable para abrir la búsqueda.
4. En la lista, busque y seleccione el registro deseado.
5. En la lista, haga clic en el vínculo de la fila seleccionada.
6. En el campo Clasificación del acuerdo de compra, haga clic en el botón desplegable para abrir la búsqueda.
7. En la lista, busque y seleccione el registro deseado.
8. En la lista, haga clic en el vínculo de la fila seleccionada.
9. Expanda la sección General.
10. En el campo Fecha de caducidad, especifique una fecha.
    * Esta fecha de vencimiento será la predeterminada para todas las líneas de compromiso, y determinará cuánto tiempo es válido cada compromiso específico.  
11. En el campo Título del documento, escriba un nombre para el acuerdo de compra.
    * Deje el campo Compromiso predeterminado en Compromiso de cantidad de producto (o cámbielo si no está así establecido).  
    * El valor de compromiso predeterminado determina las opciones en las líneas del acuerdo. Si necesita un nuevo tipo de compromiso al crear las líneas del acuerdo, deberá cambiar el compromiso predeterminado en la cabecera.  Hay cuatro tipos de compromiso: Compromiso de cantidad de producto: para una cantidad específica de un producto; Compromiso de valor de producto: para un importe de divisa específico de un producto; Compromiso de valor de la categoría de producto: para un importe de divisa específico en una categoría de compras en la que el importe puede ser para un artículo de catálogo o un artículo no de catálogo; Compromiso de valor para un importe de divisa específico que se puede satisfacer con cualquier producto o cualquier categoría de compra.  
12. Haga clic en Aceptar

## <a name="add-a-commitment"></a>Adición de un comentario
1. Haga clic en Agregar línea.
2. En la lista, marque la fila seleccionada.
3. En el campo Código de artículo, haga clic en el botón desplegable para abrir la búsqueda.
4. Seleccione el producto para el que desee agregar un compromiso.
5. En la lista, haga clic en el vínculo de la fila seleccionada.
6. En el campo Cantidad, especifique un número.
    * Esta es la cantidad total que el cliente ha acordado comprar del proveedor.  
7. En el campo Precio unitario, escriba un número.
8. Expanda la sección Detalles de línea.
9. Defina la opción Máximo aplicado en Sí.
    * La opción Máximo aplicado limita el uso del compromiso. Solo puede comprar hasta la cantidad especificada en el campo Cantidad para la línea.  
10. Contraiga la sección Detalles de línea.

## <a name="add-header-conditions"></a>Adición de condiciones de encabezado
1. En el panel de acciones, haga clic en Opciones.
2. Haga clic en Cambiar vista.
3. Haga clic en Visualización de encabezado.
4. Expanda la sección Condiciones.
5. En el campo Forma de pago, haga clic en el botón desplegable para abrir la búsqueda.
    * Las condiciones de pago de la cuenta del proveedor se muestran aquí de forma predeterminada.       
6. En la lista, busque y seleccione el registro deseado.
7. En la lista, haga clic en el vínculo de la fila seleccionada.
8. En el campo Modo de entrega, haga clic en el botón desplegable para abrir la búsqueda.
9. En la lista, haga clic en el vínculo de la fila seleccionada.
10. En el campo Condiciones de entrega, haga clic en el botón desplegable para abrir la búsqueda.
11. En la lista, haga clic en el vínculo de la fila seleccionada.

## <a name="confirm-and-activate-the-agreement"></a>Confirmación y activación del acuerdo
1. En el panel de acciones, haga clic en Acuerdo de compra.
2. Haga clic en Confirmación.
    * Defina la opción Marcar acuerdo como vigente en Sí.  
3. Haga clic en Aceptar
4. En el panel de acciones, haga clic en Acuerdo de compra.
5. Haga clic en Confirmaciones del acuerdo de compra.
    * La opción Vista previa/Imprimir le permite generar un documento para el acuerdo de compra que después se puede imprimir o enviar al proveedor. Si se actualiza el acuerdo más adelante y se vuelve a confirmar, aquí se mostrarán las dos versiones.  
6. Cierre la página.


