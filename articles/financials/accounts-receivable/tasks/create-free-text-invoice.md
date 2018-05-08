--- 
title: Crear una factura de servicios
description: "Esta guía de la tarea demuestra la creación de una factura de servicios."
author: mikefalkner
manager: AnnBe
ms.date: 10/26/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ef3cad6538d9efbd1c1881f4b7d771382d9b1ba8
ms.openlocfilehash: 87e293008fd748aa0dcc6b3caa94a4889bed35de
ms.contentlocale: es-es
ms.lasthandoff: 10/26/2017

---
# <a name="create-a-free-text-invoice"></a>Crear una factura de servicios

[!include [task guide banner](../../includes/task-guide-banner.md)]

Esta guía de la tarea demuestra la creación de una factura de servicios. Esta tarea usa la empresa de demostración USMF.

1. Vaya a Clientes > Facturas > Todas las facturas de servicios.
2. Haga clic en Nuevo.
3. En el campo Cuenta de cliente, seleccione un valor.
    * La cuenta de facturación cambiará de forma predeterminada a la misma cuenta utilizada para la cuenta de cliente.   
    * El estado de la contabilidad comienza en proceso si la factura no se registra.   
    * El número de factura se asignará al registrar la factura.  
    * Si está usando las órdenes de SEPA, la orden de débito directo se rellenará automáticamente con una orden cuando seleccione la cuenta de cliente.  
4. En el campo Descripción, escriba un valor.
5. En el campo Cuenta principal, especifique un número de cuenta sin dimensiones.
    * También puede especificar uno o varios caracteres para la cuenta principal y usar la búsqueda para encontrar su cuenta. Especificará las dimensiones más tarde en esta guía.  
6. Expanda la ficha desplegable Detalles de línea para poder agregar dimensiones en su cuenta principal.
7. Haga clic en la pestaña Línea de dimensiones financieras.
    * Las dimensiones solo son para la línea seleccionada.    
    * Se rellena el grupo de impuestos del cliente. Si el cliente no tiene un grupo de impuestos, se usará el grupo de impuestos de la cuenta principal.  
    * El grupo de impuestos de artículos se rellena desde la cuenta principal. Si la cuenta principal no tiene un grupo de impuestos de artículos, se usa el grupo de impuestos de artículos de los parámetros de impuestos de contabilidad general.    
8. En el campo Cantidad, especifique un número.
    * La cantidad es opcional.  
9. En el campo Precio unitario, escriba un número.
    * El precio unitario es opcional.  
    * El importe se calcula como cantidad por el precio unitario. Sin embargo, puede reemplazar dicho cálculo y especificar un importe.  
10. Haga clic en Impuestos para ver los impuestos calculados para la factura.
    * Vea los importes de impuestos en esta página o reemplace los importes en la ficha Ajuste.  
11. Haga clic en Aceptar
12. Haga clic en los gastos para agregar un gasto a la factura. 
13. En el campo Código de gastos, escriba un valor.
14. En el campo Valor de gastos, escriba un número.
15. Cierre la página.
16. Haga clic en Totales para ver los detalles y los totales resumidos de la factura.
17. Haga clic en Cerrar.
18. Haga clic en Registrar para registrar la factura. Podrá cancelar antes de registrar.
    * Para cambiar la hora de la impresión de facturas: seleccione Actual para imprimir cada factura cuando se actualiza o seleccione Posterior para imprimir una vez que se hayan actualizado todas las facturas.  
    * Si desea cambiar la manera en que se comprueba el límite de crédito del cliente antes de registrar, cambie el tipo de límite de crédito.  
    * Si desea imprimir la factura, seleccione Sí.  
    * Si desea registrar la factura, seleccione Sí. Puede imprimir la factura sin registrarla.  
19. Haga clic en Aceptar


