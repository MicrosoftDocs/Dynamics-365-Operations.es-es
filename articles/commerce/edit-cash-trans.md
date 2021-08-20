---
title: Editar y auditar transacciones de gestión de efectivo y pago al contado sin entrega a domicilio
description: En este tema se describe cómo editar y auditar transacciones de gestión de efectivo y pago al contado sin entrega a domicilio en Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 85c4bd4c03b6ac09f2226d1767deabde1879f869e4b7c4d45e4d4c2a1d8effb3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6765347"
---
# <a name="edit-and-audit-cash-and-carry-and-cash-management-transactions"></a>Editar y auditar transacciones de gestión de efectivo y pago al contado sin entrega a domicilio

[!include [banner](../includes/banner.md)]

En este tema se describe cómo editar y auditar transacciones de gestión de efectivo y pago al contado sin entrega a domicilio en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Información general

Los clientes de Dynamics 365 Commerce usan tanto una aplicación de punto de venta (PDV) de primera entidad como aplicaciones de PDV de terceros. En el caso de la aplicación de primera entidad, las transacciones de tienda se incluyen en la sede central desde los canales a través de un proceso por lotes. En el caso de aplicaciones de terceros, las transacciones se incluyen en la sede central de Commerce mediante la integración. En ambos casos, después de que las transacciones se incluyan en la sede central de Commerce, se debe realizar un proceso de comprobación de coherencia. Este proceso ejecuta varias validaciones en las transacciones, y solo las transacciones que se validan correctamente se incluyen en el extracto para que se puedan registrar en la sede central de Commerce.

Las transacciones de Commerce pueden producir un error en la validación por varios motivos. Un error en el código de integración o en la aplicación de PDV puede causar datos incoherentes. También, un error de usuario puede causar datos incoherentes. Por ejemplo, un usuario elimina un producto después de sincronizarlo con el canal, o un usuario cierra un período fiscal sin registrar transacciones para ese período. Aunque estas transacciones se marcan y excluyen de los extractos, pueden interrumpir el proceso diario de un cliente de registrar las ventas diarias en las operaciones financieras. En Commerce, podrá editar las transacciones específicas que causaron un error en la validación a la vez que mantiene también una auditoría de todos los cambios.

## <a name="edit-transactions"></a>Editar transacciones

En Commerce versión 10.0.5, las únicas transacciones que se pueden editar son transacciones al contado sin entrega al domicilio, como ventas y devoluciones. Los pedidos de clientes y los pedidos en línea no se pueden editar. En Commerce versión 10.0.6 y posteriores, también se pueden editar las transacciones de gestión de efectivo.

Para editar transacciones en la sede central de Commerce, siga estos pasos.

1. Instale el [Microsoft Dynamics Office Add-in](https://appsource.microsoft.com/product/office/WA104379629?tab=Overview).
1. En la sede central de Commerce, abra el espacio de trabajo **Operaciones financieras de tienda**. La ventana **Errores de validación de transacciones** ofrece una vista previamente filtrada de la página de transacción que generó un error en una o más de las reglas de validación.
1. Abra la página de transacción, seleccione el registro que generó un error en la validación, elija **Complemento de Office** y luego seleccione **Editar transacción seleccionada**. Se abre un archivo de Excel que muestra los detalles de la transacción seleccionada. Este archivo contiene las siguientes hojas de cálculo:

    - **Líneas**: esta hoja de cálculo tiene las líneas de productos y encabezado para la transacción, así como los datos relacionados para la transacción.
    - **Pagos**: esta hoja de cálculo tiene los detalles de las líneas de pago para la transacción.
    - **Descuentos**: esta hoja de cálculo tiene los detalles relacionados con descuentos para la transacción.
    - **Impuestos**: esta hoja de cálculo tiene los detalles relacionados con impuestos para la transacción.
    - **Gastos**: esta hoja de cálculo tiene los detalles relacionados con gastos para la transacción.

1. En el archivo de Excel, modifique los campos adecuados y, a continuación, cargue los datos de nuevo en la sede central de Commerce usando la funcionalidad de publicación del complemento de Excel de Dynamics. Una vez se han publicado los datos, los cambios se reflejarán en el sistema. Durante la publicación, no se realiza ninguna validación para los cambios que hagan los usuarios.
1. Para ver una traza de auditoría completa de los cambios, seleccione **Ver traza de auditoría** en el encabezado **Transacción comercial** para los cambios de nivel de encabezado y en la sección y el registro pertinentes de la página de transacción adecuada. Por ejemplo, todos los cambios relacionados con las líneas de ventas se mostrarán en la página **Transacciones de ventas**, y todos los cambios relacionados con los pagos se mostrarán en la página **Transacciones de pago**. Se mantienen los siguientes detalles de auditoría para los cambios:

    - Fecha y hora de modificación
    - Campo
    - Valor anterior
    - Nuevo valor
    - Modificado por

1. Después de que se realicen y se publiquen los cambios, ejecute **Validar transacciones de la tienda** para validar que los cambios realizados son coherentes y válidos.

> [!NOTE]
> Solo puede editar las transacciones que generaron un error de validación. Si desea editar una transacción que pasó la validación, cambie el estado de la validación de la transacción a **Error** o **Ninguno** y, a continuación, publique el cambio. Luego, puede editar los datos en el encabezado o en cualquier otro registro secundario de la transacción y publicar el encabezado o los registros.

## <a name="bulk-edit-transactions-that-are-linked-to-a-statement"></a>Transacciones de edición en masa que están vinculadas a un extracto

La versión 10.0.6 y posteriores de Commerce admiten la opción de edición en masa de transacciones en el nivel de extracto.

Para editar en masa transacciones que están vinculadas a un extracto en la sede central de Commerce, siga estos pasos.

1. Abra la página **Extractos** y seleccione el extracto que contiene las transacciones que deben editarse.
1. Seleccione el botón **Abrir en Microsoft Office**.
1. Según lo que deba editarse, seleccione una de las siguientes opciones:

    - **Editar transacciones de pago al contado sin entrega a domicilio**: esta opción le permite editar todas las transacciones de pago al contado sin entrega a domicilio que se incluyen en el extracto. Tiene a su disposición las siguientes hojas de cálculo Excel:

        - **Transacción**: esta hoja de cálculo tiene toda la información de nivel de encabezado para las transacciones de ventas.
        - **Transacción de venta**: esta hoja de cálculo tiene toda la información de nivel de línea para las transacciones de ventas.
        - **Transacciones de pago**: esta hoja de cálculo tiene toda la información de línea de pago para las transacciones de ventas.
        - **Transacciones de descuento**: esta hoja de cálculo tiene toda la información de línea de descuento para las transacciones de ventas.
        - **Transacciones de impuestos**: esta hoja de cálculo tiene toda la información de línea de impuestos para las transacciones de ventas.
        - **Transacciones de gastos**: esta hoja de cálculo tiene toda la información de línea de cargo para las transacciones de ventas.

    - **Editar transacciones de gestión de efectivo**: esta opción le permite editar todas las transacciones de gestión de efectivo que se incluyen en el extracto. Tiene a su disposición las siguientes hojas de cálculo Excel:

        - **Transacción**: esta hoja de cálculo tiene toda la información de nivel de encabezado para las transacciones de gestión de efectivo.
        - **Transacciones bancarias de forma de pago realizadas**: esta hoja de cálculo tiene todos los detalles de transacción de ingreso bancario.
        - **Transacciones de forma de pago en caja fuerte**: esta hoja de cálculo tiene todos los detalles de transacción de ingreso seguro.
        - **Declaración por forma de pago**: esta hoja de cálculo tiene todos los detalles de declaración por forma de pago.
        - **Transacción de ingresos y gastos**: esta hoja de cálculo tiene todos los detalles de línea de transacción de ingresos y gastos.
        - **Transacciones de pago**: esta hoja de cálculo tiene toda la información relacionada con pagos para la operación **Pagar factura** y la transacción de ingresos y gastos.

1. Edite las transacciones requeridas.

    > [!NOTE]
    > Las validaciones no se realizan al publicar transacciones editadas en masa. Debe asegurarse de que todas las ediciones son precisas y de que se mantiene la fidelidad de los datos en todas las hojas de cálculo. Por ejemplo, si desea cambiar la fecha de transacción para administrar los escenarios donde el período fiscal o de inventario para las transacciones abiertas está cerrado, debe cambiar la fecha en todas las hojas de cálculo de Excel que tienen la columna **Fecha de negocio**. Para validar transacciones después de que se hayan editado, puede seleccionar la página **Revalidar transacciones** en la página **Extractos**. Espere a que termine de ejecutarse el trabajo de validación antes de registrar el extracto.

1. Si la agregación ya se ha generado, abra la página **Transacciones agregadas** y seleccione **Regenerar xml de pedido de ventas**.

## <a name="bulk-edit-transactions-that-arent-linked-to-a-statement"></a>Transacciones de edición en masa que no están vinculadas a un extracto

Commerce versión 10.0.10 y posteriores admiten la opción de editar en masa transacciones que no superan la validación pero que no están vinculadas a un extracto.

Para editar en masa transacciones que no están vinculadas a un extracto en la sede central de Commerce, siga estos pasos.

1. Abra la página **Todas las tiendas** y seleccione la tienda para la que se deben editar las transacciones.
1. Seleccione el botón **Abrir en Microsoft Office** y luego seleccione **Editar transacciones de pago al contado sin entrega a domicilio**.
1. Edite las transacciones necesarias y luego publíquelas.

## <a name="additional-resources"></a>Recursos adicionales

[Editar y auditar transacciones de pedidos de cliente asincrónicas y pedidos en línea](edit-order-trans.md)

[Editar dimensiones financieras para transacciones minoristas](edit-financial-dim.md)

[Crear un libro de trabajo de Excel para editar transacciones minoristas](create-excel-edit.md)

[Agregar campos a un libro de trabajo de Excel para editar transacciones minoristas](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]