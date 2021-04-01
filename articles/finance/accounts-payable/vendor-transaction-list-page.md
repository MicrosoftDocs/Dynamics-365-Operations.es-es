---
title: Página de lista de transacciones de proveedor
description: En el siguiente tema se proporciona información acerca de la página de lista de transacciones de proveedor para Microsoft Dynamics 365 Finance.
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTrans
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 41a8506989add6c7c4a5596892bde442c7c7dff2
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5248192"
---
# <a name="vendor-transactions-list-page"></a>Página de lista de transacciones de proveedor

[!include [banner](../includes/banner.md)]

## <a name="view-settlements"></a>Ver liquidaciones

El botón **Ver liquidaciones** en el panel de acciones proporciona un acceso rápido al historial de liquidaciones e información detallada acerca de la transacción de liquidación completa. También puede mostrar transacciones adicionales relacionadas con la transacción seleccionada, ya sea porque formaban parte de la misma liquidación o porque son los pagos que se crearon en el mismo diario de pagos.

1. Seleccione **Proveedores \> Todos los proveedores**.
2. Seleccione un proveedor que tenga transacciones y, a continuación, en el panel de acciones, en la ficha **Proveedor**, seleccione **Transacciones**.
3. Seleccione una transacción para investigar y, a continuación, en el panel de acciones, seleccione **Ver liquidaciones**.

    El cuadro de diálogo **Ver liquidaciones** aparece y muestra la transacción seleccionada y todos los documentos que se han liquidado con ella. Este cuadro de diálogo es similar a la vista de historial de liquidaciones, pero incluye todos los documentos relacionados.

4. En el cuadro de diálogo, puede realizar varias tareas. Seleccione uno o más asientos y luego seleccione uno de los botones siguientes:

    - **Ver relacionadas**: muestra todas las transacciones del diario de pagos y transacciones del diario general para el proveedor que se crearon en los diarios en los que los documentos mostrados en la lista fueron creados. Por ejemplo, si se muestra un pago, todas los pagos del diario de pagos en el que se creó también se mostrarán. Si se muestra una factura o pago y se creó en un diario general, después todos los documentos en el diario general en el que se creó se mostrarán. También se muestran todas las liquidaciones relacionadas con la lista de documentos. Mientras mira los pagos relacionados, la etiqueta de este botón cambia a **Ver liquidaciones**. Seleccione **Ver liquidaciones** para mostrar solo las transacciones que se mostraron cuando abrió por primera vez el cuadro de diálogo **Ver liquidaciones**.
    - **Ver el historial** Muestra el historial de liquidaciones de los asientos. Haga clic en **Cerrar** para cerrar el cuadro de diálogo.
    - **Ver contabilidad** - Muestra todos los asientos que están relacionados con los documentos seleccionados. Haga clic en **Cerrar** para cerrar el cuadro de diálogo.
    - **Exportar**: exporte los asientos seleccionados a Microsoft Excel.
    - **Liquidar transacciones** Este botón aparece solo si el documento original seleccionado no se ha liquidado por completo. Al seleccionar este botón, el cuadro de diálogo **Liquidar transacciones** aparece, donde puede seleccionar las transacciones que quiere liquidar.
    - **Deshacer liquidación** Este botón aparece solo si el documento original seleccionado se liquidó por completo. Al seleccionar este botón, el cuadro de diálogo **Deshacer liquidación** aparece, donde puede deshacer liquidaciones que se realizaron para dicho documento.

## <a name="global-transactions"></a>Transacciones globales

El botón **Transacciones globales** también se muestra en la página de lista **Transacciones de proveedor**. Este botón le permite ver todas las transacciones de un proveedodr en todas las entidades jurídicas. La página de lista **Transacciones de proveedor** muestra las transacciones solo para aquellas entidades jurídicas a las que el usuario tenga acceso, en función de su configuración de seguridad.

La página de lista mostrará todas las transacciones de los proveedores con el mismo ID de parte que el proveedor con el que comenzó. Por ejemplo, si el proveedor US-001 en una entidad jurídica tiene el mismo id de parte que el proveedor DE-001 en otra entidad jurídica, se muestran todas las transacciones de ambos Id. de proveedor.

Los menús de la página de lista **Transacciones de proveedor** varían en función de la entidad jurídica de la transacción. Por ejemplo, si una característica solo está disponible para las entidades jurídicas suizas, las opciones de menú para dicha función solo aparecen cuando se selecciona una transacción suiza.

Para acceder a la característica, siga los pasos siguientes.

1. Seleccione **Proveedores** \> **Todos los proveedores**.
2. Seleccione un proveedor y, a continuación, en el panel de acciones, en la ficha **Proveedor**, en el grupo **Transacciones**, seleccione **Transacciones globales**.

## <a name="more-transaction-filters"></a>Más filtros de transacciones

El filtro para mostrar transacciones abiertas se ha sustituido con un nuevo filtro que permite ver más combinaciones de transacciones. Las opciones siguientes están disponibles en el campo **Mostrar**:

- **Todos** Permite mostrar todas las transacciones de los proveedores seleccionados (abiertas y cerradas).
- **Cerradas** Permite mostrar únicamente las transacciones que se han liquidado y cerrado completamente.
- **Abiertas** Permite mostrar únicamente las transacciones que no se han liquidado completamente.
- **Abrir incluyendo las cerradas en la fecha o después de ella** Permite mostrar solo las transacciones que no se han liquidado por completo o después de una fecha que ha especificado. Al seleccionar esta opción, puede cambiar la fecha que aparece junto al filtro. Las transacciones que tengan un valor del tipo **fecha de última liquidación** durante o después de la fecha que especifique se muestran en la lista, incluso si dichas transacciones se liquidan completamente en la fecha actual. Sin embargo, el saldo representa los saldos en la fecha actual, no en la fecha seleccionada.

Seleccione la casilla de verificación **Ocultar revalorizaciones de divisa** para ocultar transacciones de conversión de la divisa.

## <a name="modify-due-dates-and-discount-dates"></a>Modificar fechas de vencimiento y fechas de descuento

Puede actualizar las fechas de vencimiento y las fechas de descuento para las transacciones de cliente abiertas. En la versión 8.1 ahora puede agregar fechas de vencimiento a la página de lista **Transacciones de proveedor**. Al hacer clic en la fecha de vencimiento en la página de lista **Transacciones de proveedor**, también puede cambiar las fechas de vencimiento, las fechas de descuento, las condiciones de pago, y las condiciones de descuento por pronto pago en el cuadro de diálogo **Actualizar las fechas de vencimiento y de descuento por pronto pago**.

### <a name="activate-the-feature"></a>Activar la característica

Para agregar fechas de vencimiento a la página de lista **Transacciones de proveedor** y cambiar la configuración de pago de una transacción mediante el cuadro de diálogo **Actualizar las fechas de vencimiento y de descuento por pronto pago**, siga estos pasos.

1. Seleccione **Proveedores \> Configuración \> Parámetros de proveedores**.
2. En la pestaña **Liquidaciones**, establezca la opción **Mostrar la fecha de vencimiento y permitir su edición** en **Sí**.
3. Para habilitar esta función, se han agregado campos nuevos a las transacciones de proveedor. Estos campos se rellenarán cuando una nueva transacción sea completada. También se rellenará al abrir el cuadro de diálogo **Actualizar las fechas de vencimiento y de descuento por pronto pago**. Cuando establezca la opción **Mostrar la fecha de vencimiento y permitir su edición** en **Sí**, verá el cuadro de diálogo **Actualizar la información de pago**.  Para actualizar transacciones existentes inmediatamente, seleccione **Actualizar todas las transacciones existentes**. Como alternativa, para rellenar los campos únicamente para las transacciones nuevas, seleccione **Continuar sin actualizar**.

La fecha de vencimiento ahora se agregará a la página de lista **Transacciones de proveedor** para que pueda modificar con mayor facilidad la fecha de vencimiento y las fechas de descuento por pronto pago para las transacciones.

### <a name="modify-the-payment-settings"></a>Modificar los valores de pago

La página de lista **Transacciones de proveedor** muestra todas las transacciones de un proveedor. Al seleccionar la fecha de vencimiento para una transacción, aparece un cuadro de diálogo. Este cuadro de diálogo muestra la fecha base para los cálculos de la fecha de vencimiento y el descuento, la fecha de vencimiento, las condiciones de pago, las condiciones de descuento por pronto pago y las fechas de descuento por pronto pago.

Cada campo tiene un efecto diferente en la transacción cuando lo edita:

- **Editar la fecha de base**: la fecha de vencimiento y las fechas de descuento se cambian si la fecha de base es la fecha del documento.
- **Editar la fecha de vencimiento:** solo se cambia la fecha de vencimiento.
- **Editar las fechas de descuento:** solo se cambian las fechas de descuento.
- **Editar las condiciones de pago** La fecha de vencimiento se cambia en función de la fecha de base y las condiciones de pago.
- **Editar las condiciones de descuento por pronto pago:** los descuentos por pronto pago cambian en función de la fecha de base y de las condiciones de descuento por pronto pago.

Cuando haya terminado de editar los valores de pago, seleccione **Cerrar** para guardar los cambios.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]