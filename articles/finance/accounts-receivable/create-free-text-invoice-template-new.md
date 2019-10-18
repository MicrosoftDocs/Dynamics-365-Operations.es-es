---
title: Crear una plantilla de factura de servicios
description: Este procedimiento demuestra cómo crear una plantilla de la factura de servicios.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/29/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8281de3cb336d9392a6a97f98e51a2a139a384c5
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2189140"
---
# <a name="create-a-free-text-invoice-template"></a>Crear una plantilla de factura de servicios

[!include [banner](../includes/banner.md)]

Para este tutorial, utilice la empresa de demostración USMF. Este procedimiento se va a utilizar para el usuario responsable de gestionar y de procesar facturas de cuentas por cobrar.

## <a name="create-a-template"></a>Crear una plantilla

1. Vaya a Clientes > Facturas > Facturas periódicas > Plantillas de factura de texto libre.
    * Use este formulario para crear plantillas de factura de texto sin formato que pueden incluir líneas de facturas, gastos, una plantilla de distribución contable e información de cuenta contable.  
2. Haga clic en Nuevo para crear una plantilla de texto libre nueva.
3. En el campo Nombre de plantilla, escriba un valor.
    * Nombre de plantilla identifica de forma exclusiva una plantilla de factura de texto libre. Dos plantillas no pueden tener el mismo nombre de plantilla.  
4. En el campo Descripción, escriba una descripción de la plantilla.
5. Expanda la ficha Líneas de factura.
6. En el campo Descripción, escriba una descripción de la línea de factura.
7. En el campo Cuenta principal, seleccione una cuenta de ingresos.
    * Puede seleccionar la cuenta de transacción de compensación de un crédito de cliente por el importe total de la factura en la página Perfiles de contabilización del cliente.  
8. En el campo Grupo de impuestos, haga clic en el botón desplegable para abrir la búsqueda.
    * El grupo de impuestos para la línea de factura actual es el grupo de impuestos predeterminado para la cuenta del cliente.  
9. En la lista, haga clic en el vínculo de la fila seleccionada.
10. En el campo Grupo de impuestos del artículo, seleccione el grupo de impuestos de artículo para la línea de factura actual.
11. En la lista, haga clic en el vínculo de la fila seleccionada.
12. En el campo Precio unitario, escriba o vea el precio por unidad para la línea de factura.
    * Este importe se multiplica por el valor del campo Cantidad para determinar el importe de la línea de factura.  
13. Agregue una línea nueva a la plantilla de factura de texto libre.
14. En el campo Descripción, escriba una descripción de la línea de factura.
15. En el campo Cuenta principal, seleccione una cuenta de ingresos.
    * Puede seleccionar la cuenta de transacción de compensación de un crédito de cliente por el importe total de la factura en la página Perfiles de contabilización del cliente.  
16. En el campo Grupo de impuestos, haga clic en el botón desplegable para abrir la búsqueda.
    * El grupo de impuestos para la línea de factura actual es el grupo de impuestos predeterminado para la cuenta del cliente.  
17. En la lista, haga clic en el vínculo de la fila seleccionada.
18. En el campo Grupo de impuestos de artículos, haga clic en el botón desplegable para abrir la búsqueda.
    * El grupo de impuestos de artículo para la línea de factura actual.  
19. En la lista, haga clic en el vínculo de la fila seleccionada.
20. Especificación o visualización del número unidades para la línea de factura
    * Este número se multiplica por el valor del campo Precio unitario para determinar el importe de la línea de factura.  
21. Permite especificar o ver el precio unitario para la línea de factura. 
    * Este importe se multiplica por el valor del campo Cantidad para determinar el importe de la línea de factura.  
22. Vea y modifique las distribuciones contables para una línea individual y cualquier línea secundaria.
    * Las distribuciones contables definen cómo se contabilizará un importe; por ejemplo, cómo se contabilizarán los ingresos, impuestos o gastos en una factura de texto libre.  
23. Actualice las distribuciones contables para la línea de factura seleccionada.
24. Haga clic en Cerrar.

## <a name="save-a-free-text-invoice-as-a-template"></a>Guardar una factura de servicios como una plantilla
También puede guardar una factura de servicios existente como una plantilla. Al seleccionar Guardar en plantilla desde la pestaña Factura, especifique un nombre y una descripción para la plantilla. Si ya existe una plantilla con el nombre, verá una notificación de que ya existe una plantilla con ese nombre. Todavía puede hacer clic en Aceptar para reemplazarla. 
