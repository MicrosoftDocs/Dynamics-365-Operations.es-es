---
title: Crear una factura de servicios
description: Este tema explica cómo crear facturas de texto sin formato.
author: mikefalkner
manager: AnnBe
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 7ccc652a407e9ed09c2ffffd3c86ff5070d6399b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5217515"
---
# <a name="create-a-free-text-invoice"></a>Crear una factura de servicios

[!include [banner](../includes/banner.md)]

Este tema explica cómo crear facturas de texto sin formato. Para el procedimiento, utilice la empresa de demostración **USMF**.

## <a name="create-a-free-text-invoice"></a>Crear una factura de servicio

1. Vaya a **Clientes (o libro mayor de ventas) \> Facturas \> Todas las facturas de servicios**.
2. Seleccione **Nuevo**.
3. En el campo **Cuenta de cliente**, seleccione un valor.

    * De forma predeterminada, la cuenta que se selecciona como cuenta de cliente es utilizada como la cuenta de facturación.
    * Si no se registra la factura, el estado de contabilidad comienza con **En proceso**.
    * El número de factura se asignará al registrar la factura.
    * Si está usando las órdenes de SEPA (Zona Única de Pagos en Euros), la orden de débito directo se rellenará automáticamente cuando seleccione la cuenta de cliente.

4. En el campo **Descripción**, especifique un valor.
5. En el campo **Cuenta principal**, especifique un número de cuenta sin dimensiones. Especificará dimensiones más adelante en este tema.

    También puede especificar uno o varios caracteres para la cuenta principal y usar la búsqueda para encontrar la cuenta.

6. Seleccione la ficha desplegable **Detalles de línea** para agregar dimensiones a la cuenta principal.
7. Seleccione la pestaña **Línea de dimensiones financieras**.

    * Las dimensiones solo son para la línea seleccionada.
    * El grupo de impuestos se obtiene del cliente. Si el cliente no tiene un grupo de impuestos, se usará el grupo de impuestos de la cuenta principal.
    * El grupo de impuestos de artículos se rellena desde la cuenta principal. Si la cuenta principal no tiene un grupo de impuestos de artículos, se usa el grupo de impuestos de artículos que se especifica en los parámetros de impuestos de contabilidad general.

8. Opcional: en el campo **Cantidad**, especifique un número.
9. Opcional: en el campo **Precio unitario**, escriba un número.

    El importe se calcula como cantidad por el precio unitario. Sin embargo, puede reemplazar dicho cálculo especificando un importe.

10. Seleccione **Impuestos** para ver los impuestos calculados para la factura.

    Puede ver los importes de los impuestos en esta página o reemplazar los importes en la ficha **Ajuste**.

11. Seleccionar **Aceptar**.
12. Seleccione **Gastos** para añadir un gasto a la factura.
13. En el campo **Código de gastos**, escriba un valor.
14. En el campo **Valor de gastos**, escriba un número.
15. Cierre la página.
16. Seleccione **Totales** para ver los detalles y los totales resumidos de la factura.
17. Seleccione **Cerrar**.
18. Seleccione **Registrar** para registrar la factura. Todavía tendrá una oportunidad de cancelar antes de registrar realmente.

    * Puede cambiar el control de tiempo de la impresión de facturas. Seleccionar **Actual** para imprimir cada factura según se actualiza. Seleccione **Posterior** para imprimir cuando todas las facturas estén actualizadas.
    * Para cambiar cómo se comprueba el límite de crédito del cliente antes de registrar la factura, cambie el valor en el campo **Tipo de límite de crédito**.
    * Para imprimir la factura, establezca la opción en **Sí**.
    * Para registrar la factura, establezca la opción en **Sí**. Puede imprimir la factura sin registrarla.

19. Seleccionar **Aceptar**.

## <a name="copy-lines"></a>Copiar líneas
Para copiar líneas en una factura de servicios, seleccione una o varias líneas y, a continuación, haga clic en **Copiar líneas seleccionadas**. Puede especificar el número de copias que desea realizar y también puede copiar notas y archivos adjuntos. Puede copiar las distribuciones o permitir que se vuelvan a crear al registrarlas.

Una vez que copie las líneas, puede editar la información según sus necesidades.

## <a name="create-a-free-text-invoice-from-a-template"></a>Crear una factura de servicios a partir de una plantilla
Puede crear una factura de servicios a partir de una plantilla. Cuando seleccione **Nueva a partir de plantilla** desde la pestaña **Factura**, puede seleccionar un nombre de plantilla y la cuenta del cliente para la nueva factura de servicios. Los valores predeterminados como las condiciones de pago y el método de pago se pueden rellenar automáticamente a partir del cliente o utilizar los valores que se guardaron en la plantilla.

Se creará una nueva factura de servicios y puede editar los valores según sus necesidades.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]