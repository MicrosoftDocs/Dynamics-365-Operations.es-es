---
title: Crear un acuerdo de compra
description: Este tema le guía por el proceso de creación de un acuerdo de compra.
author: RichardLuan
manager: tfehr
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchAgreement, PurchAgreementCreate, InventItemIdLookupSimple, AgreementConfirmRunForm, PurchAgreementHistory
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 92c9b429a05a2c25672cc14a0c9ee7adfef42631
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "5016840"
---
# <a name="create-a-purchase-agreement"></a>Crear un acuerdo de compra

[!include [banner](../../includes/banner.md)]

Este tema le guía por el proceso de creación de un acuerdo de compra. Esto normalmente lo haría el director de compras. Puede utilizar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos. Es necesario haber configurado clasificaciones de acuerdo de compra antes de comenzar. Una vez que haya creado un acuerdo, podrá usarlo cuando cree un pedido de compra; esto copiará las condiciones del acuerdo de compra al encabezado y a cualquier línea del pedido a la que afecte el acuerdo.


## <a name="create-a-new-purchase-agreement"></a>Creación de un acuerdo de compra nuevo
1. Vaya a **Panel de exploración > Módulos > Adquisición y abastecimiento > Acuerdos de compra > Acuerdos de compra**.
2. Haga clic en **Nuevo**.
3. En el campo **Cuenta del proveedor**, seleccione el menú desplegable y la fila del registro deseado.
4. En el campo **Clasificación de acuerdos de compra**, seleccione el menú desplegable y la fila del registro deseado.
5. Expanda la ficha desplegable **General**.
6. En el campo **Fecha de caducidad**, especifique una fecha.

    - Esta fecha de vencimiento será la predeterminada para todas las líneas de compromiso, y determinará cuánto tiempo es válido cada compromiso específico.  

7. En el campo **Título del documento**, escriba un nombre para el acuerdo de compra.

    - Deje el campo **Compromiso predeterminado** en **Compromiso de cantidad de producto** (o cámbielo si no está así establecido).  
    - El valor de compromiso predeterminado determina las opciones en las líneas del acuerdo. Si necesita un nuevo tipo de compromiso al crear las líneas del acuerdo, deberá cambiar el compromiso predeterminado en la cabecera. Hay cuatro tipos de compromiso: **Compromiso de cantidad de producto**: para una cantidad específica de un producto; **Compromiso de valor de producto**: para un importe de divisa específico de un producto; **Compromiso de valor de la categoría de producto**: para un importe de divisa específico en una categoría de compras en la que el importe puede ser para un artículo de catálogo o un artículo no de catálogo; **Compromiso de valor** para un importe de divisa específico que se puede satisfacer con cualquier producto o cualquier categoría de compra.  

8. Seleccione **Aceptar**.

## <a name="add-a-commitment"></a>Adición de un comentario
1. Seleccione **Agregar línea**.
2. En el campo **Código de artículo**, seleccione en el menú desplegable el registro que desea.
3. En el campo **Cantidad**, especifique un número. Esta es la cantidad total que el cliente ha acordado comprar del proveedor.  
4. En el campo **Precio unitario**, escriba un número.
5. Expanda la sección **Detalles de línea.**
6. Defina la opción **Máximo aplicado** en **Sí**. La opción **Máximo aplicado** limita el uso del compromiso. Solo puede comprar hasta la cantidad especificada en el campo **Cantidad** para la línea.  

## <a name="add-header-conditions"></a>Adición de condiciones de encabezado
1. En el panel de acciones, seleccione **Opciones**.
2. Seleccione **Cambiar vista**.
3. Seleccione **Visualización de encabezado**.
4. Expanda la sección **Condiciones**.
5. En el campo **Método de pago**, seleccione en el menú desplegable el registro que desee. Las condiciones de pago de la cuenta del proveedor se muestran aquí de forma predeterminada.  
6. En el campo **Modo de entrega**, seleccione en el menú desplegable el registro que desee.
7. En el campo **Condiciones de entrega**, haga clic en el botón desplegable para abrir la búsqueda.

## <a name="confirm-and-activate-the-agreement"></a>Confirmación y activación del acuerdo
1. En el panel de acciones, haga clic en **Acuerdo de compra**.
2. Seleccione **Confirmación**. Defina la opción **Marcar acuerdo como vigente** en **Sí**.  
3. Seleccione **Aceptar**.
4. En el panel de acciones, haga clic en **Acuerdo de compra**.
5. Seleccione **Confirmaciones del acuerdo de compra**. La opción **Vista previa/Imprimir** le permite generar un documento para el acuerdo de compra que después se puede imprimir o enviar al proveedor. Si se actualiza el acuerdo más adelante y se vuelve a confirmar, aquí se mostrarán las dos versiones.  
6. Cierre la página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]