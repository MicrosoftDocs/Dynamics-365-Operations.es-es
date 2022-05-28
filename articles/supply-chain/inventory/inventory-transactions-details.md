---
title: Detalles de transacción de inventario
description: Este tema proporciona una descripción general de la página de detalles de transacciones que muestra los detalles de una transacción de inventario seleccionada.
author: rachel-profitt
ms.date: 04/25/2022
ms.topic: article
ms.search.form: InventTrans, InventTransDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2022-04-25
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: fd1416f21ce15dc832dd41ea4110c93bf5bb41a2
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2022
ms.locfileid: "8735921"
---
# <a name="inventory-transaction-details"></a>Detalles de transacción de inventario

Utilice la página **Detalles de transacciones** para ver los detalles de cualquier transacción de inventario seleccionada.

## <a name="open-the-transaction-details-page"></a>Abra la página de detalles de transacción

Para abrir la página **Detalles de transacciones**, siga estos pasos:

1. Vaya a **Gestión de inventario \> Consultas e informes \> Transacciones**.
1. Seleccione la transacción que desea inspeccionar.
1. En el panel de acciones, seleccione **Detalles de la transacción**.

## <a name="fasttabs-overview"></a>Información general de fichas desplegables

La página **Detalles de la transacción** se divide en varias fichas desplegables. En la siguiente tabla se describe la finalidad de cada ficha desplegable.

| Ficha desplegable | Description |
|---|---|
| General | Esta ficha desplegable muestra información básica acerca de la transacción de inventario seleccionada. Además de los campos que aparecen en la página **Transacciones de inventario**, incluye los campos adicionales que se describen más adelante en este tema. |
| Actualizaciones | Esta ficha desplegable muestra información relacionada con los aspectos físicos, financieros y de liquidación de la transacción de inventario seleccionada. Según el estado actual de la transacción, algunos campos pueden estar en blanco. Sin embargo, esos campos se establecerán automáticamente cuando se registren las transacciones. Además de los campos que aparecen en la página **Transacciones de inventario**, esta ficha desplegable incluye los campos adicionales que se describen más adelante en este tema. |
| Registros contables | Esta ficha desplegable muestra el tipo de registro y la cuenta contable que se utilizan para la actualización física, la actualización financiera, los ingresos físicos, los cargos físicos, los ingresos financieros y los cargos financieros relacionados con la transacción de inventario seleccionada. |
| Referencias | Esta ficha desplegable muestra información adicional acerca de la transacción de origen que creó la transacción de inventario seleccionada. Por ejemplo, esta información puede incluir detalles del pedido de compra o del pedido de venta. |
| Información relacionada | Esta ficha desplegable muestra información adicional acerca de la transacción de inventario seleccionada. Es posible que estos campos no estén configurados si no está utilizando algunas características, como categorías de compras o proyectos. |
| Dimensiones financieras - físico | Esta ficha desplegable muestra los valores de la dimensión financiera que se usaron cuando se publicó la actualización física. Si la actualización física no se ha publicado, los campos estarán en blanco. |
| Dimensiones financieras - financiero | Esta ficha desplegable muestra los valores de la dimensión financiera que se usaron cuando se publicó la actualización financiera. Si la actualización financiera no se ha publicado, los campos estarán en blanco. |
| Dimensiones de inventario | Esta ficha desplegable muestra los valores de dimensión de inventario que se asignan a la transacción de inventario seleccionada. Estos valores incluyen el sitio, el almacén, el tamaño, el color, la configuración, la ubicación, el número de lote, el número de serie, el estado del inventario, la matrícula de entidad de almacén y el propietario. |

## <a name="fields-on-the-general-fasttab"></a>Campos de la ficha desplegable General

La siguiente tabla describe los campos de la ficha desplegable **General** que no aparecen también en la página **Transacciones de inventario**.

| Campo | Description |
|---|---|
| Parte | El nombre de la parte relevante para la transacción de inventario seleccionada. Por ejemplo, una transacción de pedido de compra muestra el nombre del proveedor en el pedido de compra y una transacción de pedido de venta muestra el nombre del cliente. Este campo no está disponible para todos los tipos de transacciones de inventario. |
| Referencia de inventario | Si otra transacción de inventario está relacionada con la transacción de inventario seleccionada, el tipo de esa otra transacción. Por ejemplo, si un pedido de compra se marca frente a un pedido de ventas, el campo **Referencia de inventario** de la transacción del pedido de compra se establecerá en *Pedido de ventas*. El marcado se produce automáticamente para pedidos de entrega directa y pedidos de empresas vinculadas. Cuando utiliza el marcado con métodos de gestión de costes que no sean *coste estándar* y *media móvil*, el sistema creará liquidaciones y ajustes a las transacciones exactas que están marcadas. De esta manera, puede lograr una gestión de costes "real" que invalide la lógica de primero en entrar, primero en salir (FIFO); último en entrar, primero en salir (LIFO); o media ponderada. |
| Número de inventario | La transacción específica que está relacionada con la transacción de inventario seleccionada. Por ejemplo, si un pedido de compra se marca frente a un pedido de ventas, el campo **Número de inventario** de la transacción del pedido de compra se establecerá en el número de pedido de ventas. |
| Id. de proyecto | Si la transacción de inventario seleccionada está relacionada con un proyecto, este campo se establece en el número de proyecto. |
| Id. de lote interno | El id. de lote único que el sistema ha asignado a la transacción de inventario seleccionada. |
| Lote de referencia | Si otra transacción de inventario está relacionada con la transacción de inventario seleccionada, el id. de lote de esa otra transacción. Por ejemplo, si un pedido de compra se marca frente a un pedido de ventas, el campo **Lote de referencia** de la transacción del pedido de compra se establecerá en el valor **Id. de lote** del inventario de la línea de pedido de ventas. |
| Número de dimensión | Un id. exclusivo que representa la combinación de todos los valores de dimensión de inventario que se asignan a la transacción de inventario seleccionada. |
| Valor abierto | Un valor que indica si la transacción de inventario seleccionada ha sido liquidada por el proceso de cierre de inventario. Si este campo se establece en *Sí*, la transacción no se ha liquidado. |
| Fecha prevista | Para transacciones de recibo, la fecha en que se espera que ocurra el recibo de inventario. Por ejemplo, este campo puede mostrar la fecha de recepción prevista en un pedido de bloqueos de inventario o la fecha de entrega en una línea de pedido de compra. |
| Fecha de inventario | Este campo se establece cuando se realizó una transacción de registro en el pedido de recibo antes de que se publicara un recibo físico. |
| Transferencia no financiera | Un valor que indica si la transacción de inventario seleccionada es una transferencia no financiera. Una transferencia no financiera se produce cuando no se realiza un seguimiento financiero de un cambio en las dimensiones del inventario en la página **Grupo de modelos de artículo**. |
| Id. de lote de transferencia | Si la transacción de inventario seleccionada es una transferencia no financiera, este campo se establece en el valor **Id. de lote** de la otra transacción de inventario con la que se liquida la transacción seleccionada. |

## <a name="fields-on-the-updates-fasttab"></a>Campos de la ficha desplegable Actualizaciones

La siguiente tabla describe los campos de la ficha desplegable **Actualizaciones** que no aparecen también en la página **Transacciones de inventario**.

| Campo | Description |
|---|---|
| Asiento del Inventario físico | El número de comprobante de la contabilidad general donde se generó el registro físico de la transacción de inventario seleccionada. |
| Ruta | La ruta que está relacionada con la transacción de inventario seleccionada. Este campo se establece solo para transacciones de lista de selección de producción donde la lista de materiales (L. MAT) o la línea de fórmula están relacionadas con un artículo específico. |
| Albarán | El número de albarán que se especificó para una transacción de recepción de producto de pedido de compra. |
| Importe de coste físico | El importe que se registró en la contabilidad general para la actualización física. Para un producto de coste estándar, este importe representa el coste estándar. Para otros métodos de gestión de costes, representa la media ponderada del producto en el momento del registro. |
| Ingresos previstos por venta | El importe de los ingresos aplazados que se registraron en la contabilidad general para la actualización física. |
| Id. de la carga | Si la transacción actual está relacionada con una carga en la Gestión del transporte, este campo muestra el número único de la carga que incluyó el artículo. |
| Registrado físicamente | Un valor que indica si la transacción de inventario seleccionada se ha registrado físicamente. Si la transacción actual se registra en la contabilidad general, también habrá un asiento físico. |
| Registrado financieramente | Un valor que indica si la transacción de inventario seleccionada se ha registrado financieramente. Si la transacción actual se registra en la contabilidad general, también habrá un asiento financiero. |
| Cargo físico registrado | Un valor que indica si se han contabilizado los cargos físicos relacionados con la transacción de inventario seleccionada. |
| Cargo financiero registrado | Un valor que indica si se han contabilizado los cargos financieros relacionados con la transacción de inventario seleccionada. |
| Asiento del Inventario financiero | El número de comprobante en la contabilidad general donde se generó la contabilización financiera. |
| Factura | El número de factura que se generó, por ejemplo, para un pedido de compra o un pedido de ventas. |
| Ajuste | El importe que se ajustó en la transacción de inventario seleccionada del proceso de ajuste y cierre de inventario. |
| Importe registrado de pérdidas y ganancias | El importe de la transacción de inventario seleccionada que se registró en el estado de pérdidas y ganancias. |
| Factura sin registrar | El número de factura de un pedido de compra relacionado que aparece en la página **Factura de proveedor pendiente**. |
| Financieramente cerrado | La fecha en la que se liquidó totalmente la transacción. |
| Cantidad de PC cubierta | La cantidad de peso capturado cubierta por la liquidación. |
| Cantidad liquidada | La cantidad que se ha liquidado para la transacción de inventario seleccionada. |
| Importe liquidado | El valor que se ha liquidado para la transacción de inventario seleccionada. |
