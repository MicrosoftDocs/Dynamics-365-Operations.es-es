---
title: Crear una solicitud de presupuesto
description: Este procedimiento le muestra cómo crear una solicitud de presupuesto.
author: Henrikan
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchRFQCaseTableListPage, PurchCreateRFQCase, InventLocationIdLookup, PurchRFQCaseTable, InventItemIdLookupSimple, EcoResCategorySingleLookup, UnitOfMeasureLookup, PurchRFQEditLines, PurchRFQEditLinesPrintOptions, VendRFQJournal, SrsReportViewerForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b0e9e4d7c31b1e6905abeac03e462ac185f3f489
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7565384"
---
# <a name="create-a-request-for-quotation"></a>Crear una solicitud de presupuesto

[!include [banner](../../includes/banner.md)]

Este procedimiento le muestra cómo crear una solicitud de presupuesto. Esto normalmente lo haría el agente de compras. Puede utilizar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos. Es necesario haber configurado tipos de solicitud antes de comenzar. Una vez que haya completado esta tarea y haya creado y enviado una solicitud de presupuesto, podrá escribir las respuestas por proveedor, compararlas y conceder el contrato.


## <a name="prepare-a-new-rfq"></a>Preparar una nueva solicitud de presupuesto
1. Vaya a **Panel de exploración > Módulos > Adquisición y abastecimiento > Solicitudes de presupuestos > Todas las solicitudes de presupuesto**.
2. Haga clic en **Nuevo**.
    Están disponibles los siguientes tipos de compra: Pedido de compra (este es el predeterminado): un documento que confirma la oferta para comprar productos o la aceptación de una oferta para vender productos a cambio de un pago. Solicitud de compra: este tipo se selecciona automáticamente si se crea una solicitud de presupuesto directamente desde una solicitud de compra. Si selecciona esta opción manualmente, obtendrá un mensaje de error. Acuerdo de compra: un contrato para comprar una cantidad o valor de producto específicos en el tiempo. Si selecciona esta opción, debe seleccionar el intervalo de fechas que se aplica al acuerdo de compra.  
3. En el campo **Título del documento**, escriba un valor.
4. En el campo **Tipo de solicitud**, especifique o seleccione un valor.
    + Si se asocia un método de puntuación al tipo de solicitud, este será el método de puntuación predeterminado para la solicitud de presupuesto que está creando. Es posible cambiar el método de puntuación más adelante.  
    + En el campo **Fecha de entrega**, especifique una fecha.  
    + Seleccione la fecha en que desea recibir los artículos.  
    + En el campo **Fecha y hora de vencimiento**, especifique una fecha y una hora.  
    + Especifique la fecha y la hora en los que los proveedores deben responder a la solicitud de presupuesto.  
5. En el campo **Almacén**, especifique o seleccione un valor. La dirección de entrega tomará como predeterminada la dirección del almacén.  
6. Haga clic en **Aceptar**.

## <a name="add-lines"></a>Agregar líneas

Una vez que haya especificado la información básica acerca de la solicitud de presupuesto, especifica los bienes o servicios de los que desea que los proveedores realicen una oferta. El artículo es el tipo de línea predeterminado.

1. En el campo **Número de artículo**, especifique o seleccione un valor. Si está usando USMF, puede seleccionar T0020.  
2. En el campo **Cantidad**, especifique un número.
3. Haga clic en **Agregar línea.**
4. En el campo **Tipo de línea**, seleccione "Categoría". Puede usar el tipo Línea de categoría para crear solicitudes de presupuesto para las mercancías o servicios que no son del inventario. A continuación debe seleccionar el tipo de bienes o servicios en una jerarquía de categorías de compras.  
5. En el campo **Categoría de compras**, especifique o seleccione un valor.
6. En el campo **Nombre de producto**, escriba un valor.
7. En el campo **Cantidad**, especifique un número.
8. En el campo **Unidad**, especifique o seleccione un valor.

## <a name="add-vendors"></a>Agregar proveedores
1. Haga clic en **Encabezado** para cambiar de la vista Línea a la vista Encabezado. 
2. Expanda la sección **Proveedor**.
3. Haga clic en **Agregar proveedores automáticamente**. Puede agregar proveedores a la solicitud de presupuesto automáticamente, en función de la categoría de compra de los artículos pedidos. Si no hay ningún proveedor aprobado para las categorías incluidas en las líneas puede agregar proveedores manualmente.  
4. Haga clic en **Agregar**.
5. En el campo **Cuenta de proveedor**, especifique o seleccione un valor.
6. Haga clic en **Agregar**.
7. En el campo **Cuenta de proveedor**, especifique o seleccione un valor. Una vez que haya seleccionado un proveedor, el estado es Creado. Esto significa que la información del proveedor se ha guardado en la solicitud de presupuesto, pero que no ha enviado la solicitud de presupuesto al proveedor. Puede agregar un proveedor a una solicitud de presupuesto independientemente del estado de proveedor.  

## <a name="send-the-rfq-to-vendors"></a>Enviar solicitud de presupuesto a los proveedores
1. En el **Panel Acciones**, haga clic en **Enviar**. En la página Enviando solicitud de presupuesto, compruebe que los proveedores de la lista son los que desea que reciban la solicitud de presupuesto.  
2. Haga clic en **Imprimir**. Este cuadro de diálogo permite imprimir la solicitud de presupuesto. Si elige imprimir una hoja de respuesta, el contenido de esta se define en Parámetros de adquisición y abastecimiento. Para elegir cómo imprimir hojas de respuestas, una vez que haya abierto el cuadro de diálogo Imprimir, haga clic en Opciones de impresión avanzadas. Una solicitud de presupuesto se imprimirá para cada proveedor que contenga las líneas con el estado de Creado o Enviado. No se imprimirán las líneas canceladas ni las líneas con respuestas registradas.   
3. Haga clic en **Cancelar**.
4. Haga clic en **Aceptar**.
5. Cierre la página.
6. Cierre la página.

## <a name="view-the-rfq-journal"></a>Ver el diario de solicitudes de presupuesto
1. Vaya a **Adquisición y abastecimiento > Solicitudes de presupuestos > Seguimiento de solicitud de presupuesto > Diarios de solicitud de presupuesto**.
2. Haga clic en **Vista previa/Imprimir**.
3. Haga clic en **Vista previa de original**.
4. Cierre la página.
5. Cierre la página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]