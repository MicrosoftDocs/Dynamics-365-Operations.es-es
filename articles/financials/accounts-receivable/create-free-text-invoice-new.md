--- 
title: Crear una factura de servicios
description: "Este artículo demuestra cómo crear una factura de servicios."
author: mikefalkner
manager: AnnBe
ms.date: 05/29/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f69505f0c6137121cae92d42d052b244326c8436
ms.openlocfilehash: 2a611bdd4dd97109709ed355eb80471e27413744
ms.contentlocale: es-es
ms.lasthandoff: 06/28/2018

---

# <a name="create-a-free-text-invoice"></a>Crear una factura de servicios

[!include [banner](../includes/banner.md)]

Este artículo demuestra cómo crear una factura de servicios. Para este procedimiento, utilice la empresa de demostración USMF.

## <a name="create-a-free-text-invoice"></a>Crear una factura de servicios

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

## <a name="copy-lines"></a>Copiar líneas
Para copiar líneas en la factura de servicios, seleccione una o varias líneas y, a continuación, haga clic en Copiar líneas seleccionadas. Puede especificar el número de copias que desea realizar y también puede copiar notas y archivos adjuntos. Puede copiar las distribuciones o permitir que se vuelvan a crear al registrarlas. Una vez que copie las líneas, puede editar la información si es necesario. 

## <a name="create-a-free-text-invoice-from-a-template"></a>Crear una factura de servicios a partir de una plantilla
Puede crear una factura de servicios a partir de una plantilla. Cuando seleccione Nueva a partir de plantilla desde la pestaña Factura, puede seleccionar un nombre de plantilla y la cuenta del cliente para la nueva factura de servicios. También puede elegir valores predeterminados como las condiciones de pago y el método de pago del cliente o utilizar los valores que se guardaron con la plantilla. Se creará una nueva plantilla de servicios y puede editar los valores en esa factura. 


