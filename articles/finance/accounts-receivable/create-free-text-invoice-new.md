---
title: Crear una factura de servicio
description: Este artículo explica cómo crear facturas de texto sin formato.
author: abruer
ms.date: 02/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 4298d7114e0237072c242e83e51951a922e34e5a
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780573"
---
# <a name="create-a-free-text-invoice"></a>Crear una factura de servicio

[!include [banner](../includes/banner.md)]

Este artículo explica cómo crear facturas de texto sin formato. Para el procedimiento, utilice la empresa de demostración **USMF**.

## <a name="create-a-free-text-invoice"></a>Crear una factura de servicios

1. Vaya a **Clientes \> Facturas \> Todas las facturas de servicios**.
2. Seleccione **Nuevo**.
3. En el campo **Cuenta de cliente**, seleccione un valor.

    * De forma predeterminada, la cuenta que se selecciona como cuenta de cliente es utilizada como la cuenta de facturación.
    * Si no se registra la factura, el estado de contabilidad comienza con **En proceso**.
    * El número de factura se asignará al registrar la factura.
    * Si está usando las órdenes de SEPA (Zona Única de Pagos en Euros), la orden de débito directo se rellenará automáticamente cuando seleccione la cuenta de cliente.

4. En el campo **Descripción**, especifique un valor.
5. En el campo **Cuenta principal**, especifique un número de cuenta sin dimensiones. Especificará dimensiones más adelante en este artículo.

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
    * Puede seleccionar detener la contabilización de facturas de servicios cuando se produce un error en la pestaña **Actualizaciones** en la página **Parámetros de clientes** (**Clientes > Configuración > Parámetros de clientes**). Seleccione **Sí** para que el parámetro **Detener la publicación de facturas de texto libre en el primer error** detenga la contabilización de facturas de servicios cuando se produce un error. Si realiza la publicación en un lote, un error detendrá el proceso de publicación y el estado del lote se establecerá en **Error**. Si no se selecciona esta opción, el proceso de contabilización omitirá una factura con un error de contabilización y continuará contabilizando facturas adicionales. Si se contabiliza en un lote, un error de contabilización no evitará que se contabilicen otras facturas. El estado del lote será **Terminado**. Un informe detallado del proceso de publicación estará disponible para su revisión en el historial de trabajos por lotes.
    * Para imprimir la factura, establezca la opción en **Sí**.
    * Para registrar la factura, establezca la opción en **Sí**. Puede imprimir la factura sin registrarla.

19. Seleccionar **Aceptar**.

## <a name="copy-lines"></a>Copiar líneas
Para copiar líneas en una factura de servicios, seleccione una o varias líneas y, a continuación, haga clic en **Copiar líneas seleccionadas**. Puede especificar el número de copias que desea realizar y también puede copiar notas y archivos adjuntos. Puede copiar las distribuciones o permitir que se vuelvan a crear al registrarlas.

Una vez que copie las líneas, puede editar la información según sus necesidades.

## <a name="create-a-free-text-invoice-from-a-template"></a>Crear una factura de servicios a partir de una plantilla
Puede crear una factura de servicios a partir de una plantilla. Cuando seleccione **Nueva a partir de plantilla** desde la pestaña **Factura**, puede seleccionar un nombre de plantilla y la cuenta del cliente para la nueva factura de servicios. Los valores predeterminados como las condiciones de pago y el método de pago se pueden rellenar automáticamente a partir del cliente o utilizar los valores que se guardaron en la plantilla.

Se creará una nueva factura de servicios y puede editar los valores según sus necesidades.

## <a name="resetting-the-workflow-status-for-free-text-invoices-from-unrecoverable-to-draft"></a>Restablecimiento del estado del flujo de trabajo para las facturas de servicios de Irrecuperable a Borrador
Una instancia de flujo de trabajo que se ha detenido debido a un error irrecuperable tendrá un estado flujo trabajo **Irrecuperable**. Cuando el estado de un flujo de trabajo de facturas de servicio de clientes es **Irrecuperable**, puede restablecerlo a **Borrador** seleccionando **Recuperar** desde las acciones del flujo de trabajo. A continuación, puede editar la factura de servicios del cliente. Esta característica solo está disponible si el parámetro **Restablecer el estado del flujo de trabajo de facturas de servicios de Irrecuperable a Borrador** de la página **Administración de características** está activado.

Puede usar la página **Historial del flujo de trabajo** para restablecer el estado del flujo de trabajo a **Borrador**. Puede abrir esta página **Factura de servicios** o si navega a **Común > Consultas > Flujo de trabajo**. Para restablecer el estado del flujo de trabajo en **Borrador**, seleccione **Recuperar**. También puede restablecer el estado del flujo de trabajo a **Borrador** seleccionando la acción **Recuperar** en la página **Factura de servicios** o la pagina **Todas las facturas de servicios**. Una vez que el estado de flujo de trabajo se establece a **Borrador**, quedará disponible para editar en la página **Factura de servicios**.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
