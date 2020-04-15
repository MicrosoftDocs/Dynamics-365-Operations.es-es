---
title: Especificar los acuerdos de ventas
description: Este tema explica cómo crear un acuerdo de venta que compromete uno de los clientes a comprar un producto en una cantidad acordada durante un período de tiempo a cambio de descuentos especiales.
author: omulvad
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesAgreementListPage, SalesAgreementCreate, SalesAgreement, InventItemIdLookupSimple, AgreementConfirmRunForm, SrsReportViewerForm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 06d251992c7facca471ac893e5a0fee333e0cbed
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3148662"
---
# <a name="enter-sales-agreements"></a>Especificar los acuerdos de ventas

[!include [banner](../../includes/banner.md)]

Este tema explica cómo crear un acuerdo de venta que compromete uno de los clientes a comprar un producto en una cantidad acordada durante un período de tiempo a cambio de descuentos especiales. Puede ejecutar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos.


## <a name="set-up-sales-agreement-header"></a>Configurar el encabezado del acuerdo de venta
1. En el Panel de exploración, vaya a **Módulos > > Ventas y marketing > Acuerdos de ventas > Acuerdos de ventas**.
2. Seleccione **Nuevo**.
3. En el campo **Cuenta de cliente**, seleccione el registro deseado desde el menú desplegable.
4. En el campo **Clasificación de acuerdos de ventas**, seleccione el registro deseado desde el menú desplegable.
5. Expanda la sección **General**.
6. En el campo **Compromiso predeterminado**, seleccione **Compromiso de valor de producto**. Un tipo de compromiso es un criterio obligatorio que debe asignar el acuerdo para definir cómo se cumplirá el contrato del acuerdo. Los cuatro tipos predefinidos le permiten configurar el destino de compromiso del cliente, expresado como cantidad o valor. El tipo de compromiso de cantidad solo puede aplicarse a un producto específico, pero los tipos basados en valores son aplicables a la venta tanto de productos específicos como no específicos.  
7. En el campo **Fecha de vencimiento**, establezca la fecha en una fecha futura en la que desea que expire el acuerdo.
8. Seleccione **Aceptar**.

## <a name="set-up-product-value-commitment-lines"></a>Configurar líneas de compromiso de valor de producto
1. Seleccione **Agregar línea**.
2. En el campo **Código de artículo**, seleccione en el menú desplegable el registro que desea. El tipo de compromiso que ha elegido para el acuerdo afecta a la clase de información que puede especificar para las líneas del acuerdo. Por ejemplo, para un acuerdo basado en valor debe especificar el importe neto total (en la divisa acordada) para el que el cliente se compromete a comprarle mercancías. En este ejemplo, los campos **Cantidad** y **Unidad** de la línea no están disponibles porque está creando un acuerdo para que el cliente compre un valor específico de un producto.   
3. En el campo **Importe neto**, especifique el importe monetario que el cliente se ha comprometido a comprar.
4. En el campo **Porcentaje de descuento**, especifique un valor de porcentaje que se aplicará a las líneas de pedidos de ventas del cliente que están vinculadas al acuerdo.
5. Expanda la sección **Detalles de línea.**
6. Seleccione **Sí** en el campo **Máximo aplicado**.
    - La selección de **Máximo aplicado** implica que el importe total de todas las líneas de pedidos de ventas que usan los precios especiales del compromiso, los descuentos y las condiciones de pago no deben superar el importe especificado en el compromiso.  
    - Los importes mínimo y máximos parciales especifican un intervalo de valores que se deben vender en cada pedido de ventas que usa el acuerdo seleccionado.   
7. Expanda la sección **Encabezado del acuerdo de venta**. A menos que el estado del acuerdo se establezca en **Vigente**, los pedidos de ventas no se pueden asociar al acuerdo y por tanto no pueden contribuir a su cumplimiento. No puede modificar el estado de forma manual en esta etapa. Sin embargo, el estado se cambiaría normalmente cuando confirma el acuerdo para el cliente.  
8. En el panel de acciones, haga clic en **Acuerdo de venta**.
9. Seleccione **Confirmación**. Asegúrese de que la opción **Marcar acuerdo como vigente** se establece en **Sí**.  
10. Seleccione **Sí** en el campo **Imprimir informe**.
11. Seleccione **Aceptar**.
12. Cierre la página. El acuerdo está ahora en vigor. Puede empezar a vincular los pedidos del cliente al acuerdo, para compensar contra el objetivo comprometido.  

