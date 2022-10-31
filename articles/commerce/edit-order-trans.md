---
title: Editar y auditar transacciones de pedidos de cliente asincrónicas y pedidos en línea
description: En este artículo se describe cómo editar y auditar transacciones de pedidos de cliente asincrónicas y pedidos en línea en Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 10/21/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.industry: Retail
ms.openlocfilehash: dbeeff47446c1617da44f34ae56f333717f577a1
ms.sourcegitcommit: 18b7a02c497709e8d9c7b943d82f1fcc3dafa4cd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2022
ms.locfileid: "9712120"
---
# <a name="edit-and-audit-online-order-and-asynchronous-customer-order-transactions"></a>Editar y auditar transacciones de pedidos de cliente asincrónicas y pedidos en línea

[!include [banner](../includes/banner.md)]

En este artículo se describe cómo editar y auditar transacciones de pedidos de cliente asincrónicas y pedidos en línea en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Información general

Entre las versiones 10.0.5 y 10.0.6 de Commerce, se agregó soporte para editar transacciones de pago al contado sin entrega a domicilio (como ventas y devoluciones) y transacciones de gestión del efectivo (como entrada flotante y suspensión de forma de pago). En la versión 10.0.7 de Commerce, se agregó soporte para editar transacciones de pedidos en línea y transacciones de pedidos de clientes asincrónicas.

## <a name="edit-and-audit-order-transactions"></a>Editar y auditar transacciones de pedidos

Para editar y auditar transacciones de pedidos en Commerce headquarters, siga estos pasos.

1. Instale el [Microsoft Dynamics Office Add-in](https://appsource.microsoft.com/product/office/WA104379629?tab=Overview).
1. En la página **Parámetros de Commerce**, en la pestaña **Pedidos de cliente**, en la ficha desplegable **Pedido**, especifique un código de retención para **Código de retención para errores de sincronización de pedidos**.
2. Pause los demás trabajos de sincronización de pedidos que entren en conflicto con el momento de edición y auditoría de las transacciones.
3. Abra el espacio de trabajo **Operaciones financieras de tienda**. Las ventanas **Errores de sincronización de pedidos en línea** y **Errores de sincronización de pedido de cliente** ofrecen una vista prefiltrada de la página de transacciones minoristas. Cada una muestra los registros de transacciones con error en la sincronización para el tipo de pedido correspondiente.
4. Abra las páginas **Errores de sincronización de pedidos en línea** o **Errores de sincronización de pedidos de cliente**. Seleccione un registro para ver los detalles del error de sincronización. La ficha desplegable **Estado de sincronización** ofrece los siguientes detalles de error:

    - Estado del pedido pendiente
    - Detalles de errores del pedido
    - Fecha y hora de modificación
    - Número de reintentos

1. Si los detalles del error indican que el registro debe corregirse, seleccione **Complemento de Office** y luego elija **Editar transacción seleccionada**. Se abre un archivo de Excel que muestra los detalles de la transacción seleccionada.

    - Si la transacción que se está editando es una transacción de pedido en línea, el archivo de Excel contiene las siguientes hojas de cálculo:

        - **Transacción**: esta hoja de cálculo tiene los detalles de encabezado para la transacción.
        - **Transacción de venta**: esta hoja de cálculo tiene los detalles de línea para la transacción.
        - **Transacciones de pago**: esta hoja de cálculo tiene los detalles de las líneas de pago para la transacción.
        - **Transacciones de descuento**: esta hoja de cálculo tiene los detalles relacionados con descuentos para la transacción.
        - **Transacciones de impuestos**: esta hoja de cálculo tiene los detalles relacionados con impuestos para la transacción.
        - **Transacciones de gastos**: esta hoja de cálculo tiene los detalles relacionados con gastos para la transacción.

    - Si la transacción que se está editando es una transacción de pedido de cliente asincrónica, el archivo de Excel contiene las siguientes hojas de cálculo:

        - **Líneas**: esta hoja de cálculo tiene los detalles de línea y encabezado para la transacción.
        - **Pagos**: esta hoja de cálculo tiene los detalles de las líneas de pago para la transacción.
        - **Descuentos**: esta hoja de cálculo tiene los detalles relacionados con descuentos para la transacción.
        - **Impuestos**: esta hoja de cálculo tiene los detalles relacionados con impuestos para la transacción.
        - **Gastos**: esta hoja de cálculo tiene los detalles relacionados con gastos para la transacción.

1. En el archivo de Excel, en el campo **Estado de pedido pendiente**, introduzca **Edición** y luego publique el cambio. De esta forma, evita que el trabajo **Sincronizar pedido** que se está ejecutando en el modo por lotes omita este registro durante el procesamiento.
1. En el archivo de Excel, modifique los campos adecuados y, a continuación, cargue los datos de nuevo en la sede central de Commerce usando la funcionalidad de publicación del complemento de Excel de Dynamics. Una vez se han publicado los datos, los cambios se reflejarán en el sistema. Durante la publicación, no se realiza ninguna validación para los cambios que hagan los usuarios.
    > [!NOTE]
    > Si no encuentra el campo que quiere editar, siga los pasos que indicamos a continuación para agregar el campo que falta en la hoja de cálculo.
    >   1. Seleccione **Diseño** en el Conector de datos.
    >   1. Seleccione el icono de lápiz que está junto a la tabla en la que desea agregar un campo.
    >   1. Seleccione el campo en la sección **Campos disponibles** y luego seleccione **Agregar**.
    >   1. Agregue tantos campos como necesite y luego seleccione **Actualizar**.
    >   1. Cuando se complete la actualización, es posible que deba seleccionar **Actualizar** para actualizar los valores.

3. Para ver una traza de auditoría completa de los cambios, seleccione **Ver traza de auditoría** en el encabezado **Transacción comercial** para los cambios de nivel de encabezado y en la sección y el registro pertinentes de la página de transacción adecuada. Por ejemplo, todos los cambios relacionados con las líneas de ventas se mostrarán en la página **Transacciones de ventas**, y todos los cambios relacionados con los pagos se mostrarán en la página **Transacciones de pago**. Se mantienen los siguientes detalles de auditoría para los cambios:

    - Fecha y hora de modificación
    - Campo
    - Valor anterior
    - Nuevo valor
    - Modificado por

1. Una vez que haya realizado y publicado sus cambios, seleccione **Sincronizar pedido** para iniciar inmediatamente el proceso de sincronización. También puede esperar a que el proceso de sincronización que se está ejecutando en el modo por lotes procese la transacción.

De forma predeterminada, una vez que los pedidos se sincronizan correctamente, se ponen en estado de retención, según el código de retención que se define en los parámetros de Commerce. La retención en los pedidos debe eliminarse antes de que los pedidos se puedan procesar más para su cumplimiento u otras operaciones.

## <a name="additional-resources"></a>Recursos adicionales

[Editar y auditar transacciones de gestión de efectivo y pago al contado sin entrega a domicilio](edit-cash-trans.md)

[Editar dimensiones financieras para transacciones minoristas](edit-financial-dim.md)

[Crear un libro de trabajo de Excel para editar transacciones minoristas](create-excel-edit.md)

[Agregar campos a un libro de trabajo de Excel para editar transacciones minoristas](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
